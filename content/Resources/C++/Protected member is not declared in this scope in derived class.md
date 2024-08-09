---
tags: [C++,template]
aliases: []
---

>Reference :https://stackoverflow.com/questions/12032345/protected-member-is-not-declared-in-this-scope-in-derived-class

```cpp
template<typename T>
class B {
public:
  void f() { }  // Member of class B<T>
};
template<typename T>
class D : public B<T> {
public:
  void g()
  {
    f();  
    // Bad (even though some compilers erroneously (temporarily?) accept it)
  }
};
```
- Within D\<T\>::g(), the name f does not depend on template parameter T, so f is known as a nondependent name. On the other hand, B\<T\> is dependent on template parameter T so B\<T\> is called a dependent name.
- Here’s the rule: the compiler does not look in dependent base classes (like `B<T>`) when looking up nondependent names (like `f`).

Solution:
- Change the call from `f()` to `this->f()`. Since `this` is always implicitly dependent in a template, `this->f` is dependent and the lookup is therefore deferred until the template is actually instantiated, at which point all base classes are considered.
	- By default, all names that depend on template parameters are implicitly dependent in a template. This is because the compiler cannot determine the meaning of these names until the template is instantiated with specific template arguments.
- Insert `using B<T>::f;` just prior to calling `f()`

```cpp
template<typename T> 
class D : public B<T> { 
public: 
    using B<T>::f; // Add this line
    void g() { 
        f(); // Now valid
    } 
};
```

- change the call from f() to B\<T\>::f(). Note however that this might not give you what you want if f() is virtual, since it inhibits the virtual dispatch mechanism.

```cpp
template<typename T> 
class B { 
public: 
    virtual void f() { 
        std::cout << "B<T>::f()\n"; 
    } 
};

template<typename T> 
class D : public B<T> { 
public: 
    void g() { 
        B<T>::f(); // Call the base class version of f()
    } 
    void f() { 
        std::cout << "D<T>::f()\n"; 
    } 
};

int main() {
    D<int> d;
    d.g(); // Output: B<int>::f()
    d.f(); // Output: D<int>::f()
    return 0;
}
```

- In this example, `B<T>::f()` is called explicitly in `D::g()`, so the base class version of `f()` is called instead of the derived class version. As a result, the output of `d.g()` is `B<int>::f()` instead of `D<int>::f()`.
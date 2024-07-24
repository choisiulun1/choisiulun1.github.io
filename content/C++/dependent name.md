---
tags: [C++,template]
aliases: []
---
- In a template, names that depend on template parameters are called dependent names. These names are not resolved by the compiler until the template is instantiated with specific template arguments.

- In a template class or function, the names of member functions, member variables, and base classes that depend on template parameters are dependent names. These names are implicitly dependent, meaning that the compiler assumes that they depend on the template parameters unless they are explicitly qualified with the `typename` or `template` keywords.

```cpp
template<typename T>
class MyClass {
public:
    void foo() {
        T::bar(); // Implicitly dependent
        typename T::baz qux; // Explicitly dependent
    }
};

```
---
tags: [C++]
aliases: []
---

```cpp
struct S
{
    int n;
 
    S(int);       // constructor declaration
 
    S() : n(7) {} // constructor definition:
                  // ": n(7)" is the initializer list
                  // ": n(7) {}" is the function body
};
 
S::S(int x) : n{x} {} // constructor definition: ": n{x}" is the initializer list
 
int main()
{
    S s;      // calls S::S()
    S s2(10); // calls S::S(int)
}

```

- Before the compound statement that forms the function body of the [[Constructor type of C++|constructor]] begins executing, initialization of all direct bases, virtual bases, and non-static data members is finished. ^880c70

## Situations that Initialization list is necessary
- const / reference
	- They can only be initialized but not assignment
- 
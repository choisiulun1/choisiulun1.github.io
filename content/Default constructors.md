---
tags: []
aliases: []
---
## When will the default constructors be synthesized?

The C++ Annotated Reference Manual (ARM) [ELLIS90] (Section 12.1) tells us that "default constructors...are generated (by the compiler) where needed...." 
- The crucial word here is **needed**

```cpp
class Foo { public: int val; Foo *pnext; };

void foo_bar()

{
   // Oops:  program needs bar's members zeroed out
   Foo bar;
   if ( bar.val || bar.pnext )

      // ... do something
   // ...

}
```

- In this example, correct program semantics requires of Foo a default constructor that initializes its two members to zero. 
- Does this fragment, then, fulfill the requirement of needed as stated in the ARM? 
	- The short answer is no.
- The distinction is that between the needs of the program and the needs of the implementation.
	- A program's need for a default constructor is the responsibility of the programmer; in this case, the individual who designed class Foo. [^1] A default constructor is not synthesized for this code fragment.

The Standard has refined the discussion in the ARM, although the behavior, in practice, remains the same. The Standard states [ISOC++95] (also Section 12.1) the following:

><mark style="background: #FFF3A3A6;">If there is no user-declared constructor for class X</mark>, a default constructor is implicitly declared.... A constructor is trivial [^2] if it is an implicitly declared default constructor....

A nontrivial default constructor is one that in the ARM's terminology is needed by the implementation and, if necessary, is synthesized by the compiler.

The standard then goes on to iterate the conditions under which the implicit default constructor is considered trivial. A [[Nontrivial synthesized default constructor|nontrivial default constructor]] is one that in the ARM's terminology is needed by the implementation and, if necessary, is synthesized by the compiler.


[^1]: Global objects are guaranteed to have their associated memory "zeroed out" at program start-up. Local objects allocated on the program stack and heap objects allocated on the free-store do not have their associated memory zeroed out; rather, the memory retains the arbitrary bit pattern of its previous use.

[^2]: Trivial : No use
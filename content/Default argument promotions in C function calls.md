---
tags: [stackoverflow , Argument promotion]
aliases: []
---

## Function prototype
- The term _prototype_ does not mean a declaration of a function preceding its definition. It means a declaration of a function that declares the types of its parameters (C 2018 6.2.1 2). ^a32450
	- `int add(int a, int b);` (prototype) (declaration)
	- `int add(int a, int b)<-(header){...}` (definition)
	- `test_no_prototype` has a prototype because `void test_no_prototype(const struct test_arg a){ }` declares the type of its parameter, `const struct test_arg`.
	- An example of a declaration without a prototype is `void test_no_prototype();`. It is an old style of declaration that should not be used in new code.

>Generally, a function should be declared the same way it is defined, although parameter names can be omitted in a declaration that is not a definition.

- For those of you who are wondering _why_ things are this way: in the dark ages before 1988, there was no such thing as a function prototype in classic "K&R" C, and the default argument promotions were instituted because (a) there were essentially "free", as it costs no more to put a byte in a register than to put a word in a register, and (b) to cut down on potential errors in parameter passing. That second reason never quite cut it, which was why the introduction of function prototypes in ANSI C was the single most important change ever in the C language.
  
- As to when default promotions kick in: <mark style="background: #ABF7F7A6;">default argument promotions are used exactly when the expected type of the argument is _unknown_, which is to say when there's no prototype or when the argument is variadic.</mark>

>https://stackoverflow.com/questions/1255775/default-argument-promotions-in-c-function-calls

Reference Reading : https://blogs.fau.de/wittmann/2013/11/c-default-argument-promotions/
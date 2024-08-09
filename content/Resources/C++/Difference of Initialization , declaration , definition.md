---
tags: [C++]
aliases: []
---
```cpp
int var; /* declare */ 

var=10; /* initialize */ 

int var=10; /* define */
```

```cpp
int var; // is declared but not defined 

var=7; // var is initialized and defined 

int var2=6; // var2 is declared, initialized, and defined.
```

## Declaration
- Declaration, generally, refers to the introduction of a new name in the program.
	- For example, you can _declare_ a new function by describing it's "signature"

```cpp
void xyz();
```

```cpp
class klass;
struct ztruct;
```


## Initialization
nitialization refers to the "assignment" of a value, at construction time[^1]. For a generic object of type `T`, it's often in the form:
```java
T x = i;
```

but in C++ it can be:

```cpp
T x(i);
```

or even:

```cpp
T x{i};
```

with C++11.

[^1]: ![[Initialization List of C++#^880c70]]

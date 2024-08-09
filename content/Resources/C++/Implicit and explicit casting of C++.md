---
tags: [C++,Quora]
aliases: []
---
- Implicit type casting is performed by the compiler on its own when it encounters a mixed data type expression in the program.
	- It is also known as automatic conversion as it is done by compiler without programmer’s assistance.
	- Implicit casting doesn’t require a casting operator.

```C++
int a=42; 
float b=a;
```

- Explicit type casting is performed by the programmer. 
- In this type casting programmer tells compiler to type cast one data type to another data type using type casting operator. 
- But there is some risk of information loss is there, so one needs to be careful while doing it.

```C++
float a=42.12;  
int b=(int)a; 
```

>https://www.quora.com/What-is-the-difference-between-the-implicit-type-casting-and-explicit-type-casting-in-C++
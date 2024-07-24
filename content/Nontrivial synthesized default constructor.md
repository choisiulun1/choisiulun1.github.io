---
tags: [C++]
aliases: [nontrivial default constructor]
---
## Member Class Object with Default Constructor

- If a class without any constructors contains a member object of a class with a default constructor, the implicit default constructor of the class is nontrivial and the compiler needs to synthesize a default constructor for the containing class. 
- This synthesis, however, takes place only if the constructor actually needs to be invoked.

```cpp
class Foo { public: Foo(), Foo( int ) ... };

class Bar { public: Foo foo; char *str; };

void foo_bar() {
   Bar bar; // Bar::foo must be initialized here
      if ( str ) { } ...
}
```

- The synthesized default constructor contains the code necessary to invoke the class Foo default constructor on the member object `Bar::foo`
-  but it does not generate any code to initialize `Bar::str`. Initialization of `Bar::foo` is the compiler's responsibility; initialization of `Bar::str` is the programmer's. The synthesized default constructor might look as follows: ^7db825

```cpp
// possible synthesis of Bar default constructor
// invoke Foo default constructor for member foo
inline
Bar::Bar()

{
   // Pseudo C++ Code

   foo.Foo::Foo();
}
```

- Again, note that the synthesized default constructor meets only the needs of the implementation, not the needs of the program. For the program fragment to execute correctly, the character pointer str also needs to be initialized. 
- Let's assume the programmer provides for the initialization of str via the following default constructor:

```cpp
// programmer defined default constructor
Bar::Bar() { str = 0; }
```

- Now the program need is fulfilled, but the implementation need to initialize the member object `foo` still remains. 
	- Because the default constructor is explicitly defined the compiler cannot synthesize a second instance to do its work.
- What's an implementation to do?

Consider the case of each constructor defined for a class containing one or more member class objects for which a default constructor must be invoked.
- In this case, the compiler augments the existing constructors, inserting code that invokes the necessary default constructors prior to the execution of the user code.

In the previous example, the resulting augmented constructor might look as follows:

```cpp
// Augmented default constructor
// Pseudo C++ Code
Bar::Bar()
{

   foo.Foo::Foo(); // augmented compiler code

   str = 0;        // explicit user code
}
```

### Conclusion

#### No explicit default constructor
- The compiler synthesize a implicit trivial one
- The memeber data in the class will not be initialized in the synthesized one because this is not necessary for implementation

#### Class Memeber initialization in default constructor 
- When A class contains a class member and there is no default constructor in it , a default constructor will be synthesized to initialize the class member.
- If their is explicit default constructor in it , the explicit default constructor will be augmented. The initialization statement of member class will be inserted before the explicit statement.


## Base Class with Default Constructor
Similarly, if a class without any constructors is derived from a base class containing a default constructor, the default constructor for the derived class is considered nontrivial and so needs to be synthesized.
- The synthesized default constructor of the derived class invokes the default constructor of each of its immediate base classes in the order of their declaration.
- To a subsequently derived class, the synthesized constructor appears no different than that of an explicitly provided default constructor.

What if the designer provides multiple constructors but no default constructor?
- The compiler augments each constructor with the code necessary to invoke all required default constructors. However, it does not synthesize a default constructor because of the presence of the other user-supplied constructors.
- If member class objects with default constructors are also present, these default constructors are also invoked—after the invocation of all base class constructors.

>Base class->class member->explicit statement

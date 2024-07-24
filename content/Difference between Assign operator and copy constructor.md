---
tags: [C++,constructor]
aliases: []
---
A **_copy constructor_** is used to initialize a **_previously uninitialized_** object from some other object's data.

```cpp
A(const A& rhs) : data_(rhs.data_) {}
```

For example:

```cpp
A aa;
A a = aa;  //copy constructor
```

An **_assignment operator_** is used to replace the data of a **_previously initialized_** object with some other object's data.

```cpp
A& operator=(const A& rhs) {data_ = rhs.data_; return *this;}
```

For example:

```cpp
A aa;
A a;
a = aa;  // assignment operator
```

```cpp
Swiss::Swiss(const int numRounds, const PlayerList& list){

    this->numRounds=numRounds;
    this->list = list;
    this->list.sort();
    this->curRound=0;

}
```

Here `this->list = list` will call the assign operator because `this->list` is initialized. 
![[Nontrivial synthesized default constructor#^7db825]]

>https://stackoverflow.com/questions/11706040/whats-the-difference-between-assignment-operator-and-copy-constructor

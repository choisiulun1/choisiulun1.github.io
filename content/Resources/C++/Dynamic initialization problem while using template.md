---
tags: [C++,template]
aliases: []
---

```cpp
class Vector:public Array<T>{
    public:
        Vector():Array<T>(2){};
        void push(T x){
            if(num+1>this->getSize()){
                extendArray();
            }
            (*this)[num++]=x;
        }
    private:
        int num;
        void extendArray() {
    int newSize = this->getSize() * 2;
    T* temp = new T[newSize];
    for (int i = 0; i < newSize; i++) {
        if (i < this->getSize()) {
            temp[i] = (*this)[i];
        } else {
            temp[i] = T();
        }
    }
    delete[] this->array;
    this->array = temp;
    this->setSize(newSize);
}

};
```

- if we don't write `else { temp[i] = T(); }` , it will cause memory error
	- when we are using `new` keyword in normal situation , the dynamic array will be initialized automatically by compiler
	- However since T is not resolved , the compiler can't implicitly help us to initialize it because it doesn't know the type of the array

>When you use a dynamic array with templates, the elements in the array will not be automatically initialized. You will need to initialize them yourself, either by explicitly assigning values to each element or by using a default constructor for the element type.

`MyArray<MyClass> arr(10);

- In this case, the default constructor of the `MyClass` class will be called for each element in the `array`, initializing the `value` member of each `MyClass` object to 0.
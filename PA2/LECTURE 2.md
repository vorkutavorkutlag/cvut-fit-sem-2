
First we have to finish this lecture, then we start OOP.

`auto` is a nice keyword that substitutes the type of declared variable. It exists to reduce typing. We cannot initialize it without assigning a value.
Little caveat, `"hi"` is a C string, `"hi"s` is a string literal.
Another: `auto y1 = arr` will be a C array pointer, whereas `auto & y1 = arr` will be a direct reference to the array.

In range iteration, `for (const auto & i : data)` . Synonymous with "for each `i` in `data`, ...".

Templates are our form of generics in C++. 
```cpp
`template <typename T>`
struct array {
	T *data;
	size_t size, cap;
}

...
`template <typename T>`
void append(array<T>& a, T x) {
	...
	a.data[a.size++] = x;
}
```


STL, standard templates, uses templates everywhere; vectors, sorting, etc.
We may check for errors with exceptions now. `if(error)`...
It is a loop of try, catching, with a default `catch(...)` at the end. Some known exceptions include `std::out_of_range& e`

Enums are data types with options. Usually the data type that holds the names are integers. Multiple enums can collide the same names.
Enum classes are similar to enum, however we need to write the namespace before accessing the option.

C's casts only had a single option, `(Type)x`
Casts may differ in how unsafe they are.
- `static_cast<Type>` performs almost any builtin or user defined conversion except const removal
- `const_cast<Type>` adds (mostly useless) or removes (very dangerous) const or volatile
- `dynamic_cast<Type>` a safe cast to a subclass
- `reinterpret_cast<Type>` treats x as a value of a type Type. Dangerous. It does not touch the bytes in the memory, it simply treats those bytes as if they were of a different type.

Later on we will discuss anonymous lambda functions.
Classes, inheritance...

We will not discuss functions with trailing return types `auto foo() -> int`
`decltype`, Modules (C++ 20), Concepts, Ranges, Coroutines, ...


## ... Programming Styles
Procedural style divides the problem into smaller sub-tasks, including different functions and structures in order to split up the problem into more manageable pieces. Use abstraction to describe the sub-problem.
Redundant code is eliminated.

OOP means only messaging local retention and protection and hiding of state process, and extreme late binding of all things. 
Object-Oriented pertaining to a technique or a programming language that supports objects, classes, and inheritance 
Analyze the problem and identify the participating entities.
Analyze the interactions between the entities.
Implement the entities as classes and objects. The interactions will result in the interfaces (methods) of the classes.

The object holds some information ( a state). The state is determined by the content of its data fields (attributes).
The interface of an object defines its behavior. The interface is the set of operations (methods) available for the object.
The class of an object defines the interface and the data fields of an object. Programs usually create many objects of the same class.
More of the data is implicit, compared to procedural.

Attributes are split mostly into public and private,  the latter ones being modifiable only inside of the class' internal data. There is also protected, which can only be accessed by the class and those who inherit it.
When you introduced an object, it is constructed, i.e. initialized. We have guarantee of no garbage memory.

Sometimes when the overhead isn't worth it for simple functions, we would rather just macro the function in-line with the rest of the code. Keyword `inline` 

Encapsulation includes the public protected private keywords.
The visibility is private for class by default, and public for struct by default.
Constant methods do not modify the state of the object.
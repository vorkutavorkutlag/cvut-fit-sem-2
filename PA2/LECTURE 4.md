Still overload operators...

Implementation of `==` using `<=>` is not recommended due to performance issues.
The return type denotes the ordering class. strong, weak, partial...
Expected implementation needs `<compare>` lib.

Indexing operator `[]` can be of any type, not just `size_t`,
Maps, tables use this as well.
There should be two overloads, constant and non-constant.

For pointers/iterators, we can also overload dereferencing and arrows. 
Function call operators meaning object can be used as a function.

Copying objects.
Copy constructor and copy assignment operator.
Shallow and deep copy.
`rvalue` reference and `unique_ptr`
Move constructor and move assignment operator.
Shallow copy and `shared_ptr`
etc.

Dangerous of copying of, for example arrays, are double frees with the destructors and eventual segmentation fault.

Moving can only be done if we know that the object we are using as a source is to be destroyed. These are `rvalue` references.

A simplified terminology, originally from C.
`lvalue` can be on the LHS of assignment, it is not temporary. `rvalue` is the temporary.
It is denoted by `&&` instead of `&` as in common `lvalue`
Non-const `lvalue` references are never bound to `rvalue`.
`std::move()` does not actually move the variable, it just marks it as moveable.
Equivalent to casting it to an `rvalue`. i.e. `std::static_cast<T&&>`

Either rule of five or rule of zero (leave it all for the compiler).

A unique pointer is a class representing an exclusive ownership of a dynamically allocated object and it can be implemented using moving semantics.
The objects of this class cannot be copied, just moved. If the class is destroyed, it also frees the owned object.
Thanks to operator overloading, it has the same interface as a regular pointer.
Implemented using `std::unique_ptr`

Use `std::shared_ptr` for reference counting.


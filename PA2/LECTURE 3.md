
Constructor implementation would be adding a method in a struct/class by the name of that struct/class. There may be different constructors for different parameters.

It is possible to suppress the generation of a method by applying `= delete` to it inside of the declaration inside the struct/class.
By applying `= default` you force the compiler to generate the annotated method even if the compiler would not do so otherwise.

`inline`, as described before, will get rid of the functions overhead and macro it into the code in the compiler. 
It does not have a direct impact on optimization, but it enables other optimizations on the inlined code. Nice!

`static` class and `instance` member variables.
An instance variable is declared without any special keyword, every instance has its own set of instance variable.
Statics are declared using the `static` keyword, static variables are shared among all class instances, static variables must have memory reserved - we either define them outside class declaration or we use inline, the access to static variables follows the standard encapsulation rules (`public`/`protected`/`private`).
Effectively a global variable in our code.
Useful for singleton usage, maybe for cashing.

Overloading operators was touched again...
Friend functions are a thing. access is granted by `friend` keyword.
Access must be granted inside declaration. Friends violate encapsulate to some level, and the technique should be used rarely.
Friend functions are useful for operator overloading, namely operator `<<`

Encapsulation is a way to make code safer by allowing the only interactions between objects that are really necessary. Enforceable, high level public interface.

Existence of spaceship operator `<=>` mentioned.


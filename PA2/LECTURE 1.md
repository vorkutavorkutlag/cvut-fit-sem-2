
From C to C++
New features, more messy, bigger standard library.
Namespaces are packages/directory structure, travel between them using `::`.  Good for separating/organisation code.
`cout` replaces the C output file `stdout`. We use overload op. `<<`
`endl` internally calls method `cout.flush()`, flushing any buffers.
No need for struct keyword (already "typedeffed")

References! Use pointers behind the scene. No need for address, can just reference/borrow the variable directly by using `&` before the parameter name.

C++ adds default parameters.

Can use function pointers with specified interface (parameters) to specify overloading functions. 
Function overloading chooses the "best" type match. 
Exact match -> Promotion -> Standard Conversion > User Conversion
Must be one winner, very strict.

Dynamic memory allocation in C++ is done with `new` and `delete`. You can use C's memalloc methods, but destruct them with C. Do not mix.
There are smart pointers, mainly unique_ptr, shared_ptr. useful for ownership and lifetime. Going out of scope, the destructor deallocates.

adding also nullptr and auto keywords.

Must clear cin/cout flags before operations, even such as `ignore`! (flush equivalent).
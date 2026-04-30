
# constexpr

Compile time evaluation. Can be used in functions, class methods.
Powerful tool for optimization.

May use `requires`  sometimes to make sure some things hold.
We can check whether something is valid.
```cpp
template <typename T>
constexpr bool has_plus() {
	return requires (T a) {a + a; };
}

...

template <typename T> requires (has_plus<T>())
void foo (T t)

```

`if-constexpr-else` statements are also powerful, as we know whether the else branch will run or not.

Should personally look into.
- Type traits
- Deduction guides
- SFINAE (substitution failure is not an error)
- more uses of requires (rust-like?)
- `consteval` and `constinit`
- concepts.

...

Solve RMQ (Range Minimum Query) by precomputing minimum of blocks of some size.
If range adheres exactly to block, return the precomputed minimum.
If range starts at one block and ends at some other, return the minimum of those.

...

Operation signature is a formal description of the operation.
A signature defines the number of operands, arity, and their data types.
Somewhat like a format definition of a mapping in mathematics.
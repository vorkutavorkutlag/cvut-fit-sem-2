
Deduce types for template functions:
`auto foo(T x) -> deducetype`

Template interchangeable with `auto`.

variadic template example.

```cpp
template <typename ... Args>
auto my_max(const Args &... args) {
	auto members = {args ...};
	auto max = *members.begin();
	for (const auto& mem : members) {
		max = std::max(max, mem);
	}
	
	return max;
}
```


...Could also be `const Args &&...`

Could also use it with first, and variadic.
Then make an override function with a single argument.
That will help us use different types.
Or...

```cpp
template <typename T, typename ... Args>
auto my_max(T const & first, Args const & ... args) {
	if constexpr (!sizeof ... (args)) return first;
	else {
		auto max_rest = our_max(args ...)
		return first < max_rest ? first : max_rest;
	}
}
```

`constexpr` is really important here, as we need the condition to be evaluated in compile time.

Even if we do `consteval`, then we still need to write `constexpr` at the if condition.
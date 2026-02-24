
Next homework in 11 days will include vectors.
Neat use-case for vectors is, for example, for storing pairs. 
```cpp
std::vector<std::pair<std::string, char>> m_courses;
```

The following is the class for the student we made:
```cpp
class Student {
	public:
		Student(std::string name, unsigned id);
		~Student() = default;
		double get_average_grade() const;
		bool add_grade(course, grades);
		std::string get_name() const;
		unsigned get_id() const;
		void print(std::ostream & os) const;
		
	private:
		unsigned m_id;
		std::string m_name;
		std::vector<std::pair<std::string, char>> m_graded courses;
}
```

If we have a const method, the `this` pointer will be a const pointer.
Otherwise, we will have a `this` pointer, being a non-const pointer.
Both point to the student object.

When the original object goes out of spoke, the reference to it will also be deleted. So, be careful in loops!

We can use structure binding to destruct a structure (say, pair) into parts.
Instead of:
```cpp
for (auto const & p : v) {
	p.first = ...
	p.second = ...
}
```

We can write
```cpp
for (auto const &[f, s] : v) {
	f = ...
	s = ...
}
```

We may use abstract streams by passing them as reference.
```cpp
void some_print(std::osstream & os) {
	os << something!"" << std::endl;
}
```


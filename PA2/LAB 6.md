
Set elements should be comparable, unlike vectors.

An iterator is an abstraction of a pointer.

A functor is a class or an object with overridden operator `[]`.

To accumulate over an iterator, we could use `std::accumulate`
For example,
```cpp
auto add_time = [](unsigned sum, Task const & task) {
	return sum _ task.m_expected_time;
}

std::accumulate(tasks.begin(), tasks.end(), 0U, add_time);
```

You can erase from an array while you iterate, as long as you iterate using the iterators. Erase using `tasks.erase(it)`
Using invalidated iterator is undefined behavior.
Erase returns an iterator, being the next element.

```cpp
unsigned remove_low_pri_tasks(std::vector<Task> & tasks, unsigned l){
	for (auto it = tasks.begin(); it != tasks.end();) {
		if (...) {
			it = erase(it);
		} else ++ it;
	}
}
```

We can also use remove if.
```cpp
auto predicate = [l] (Tasks const & task) {return tasks.m_pri < l};
auto new_end = std::remove_if(tasks.begin(), tasks.end(), prediacte);
unsigned rmv = tasks.end() - new_end;
tasks.erase(new_end, tasks.end());
```

In C++ 20 we have `std::erase` and `std::erase_if`
```cpp
auto predicate = [l] (Tasks const & task) {return tasks.m_pri < l};
return std::erase_if(tasks, predicate);
```

Sometimes, we should use priority queue. 
```cpp
auto comparator = [](Tasks const & lhs, Task const & rhs) { return lhs.m_p < lhs.m_p }
std::priority_queue<Task, std::vector<Task>, decltype(comparator)> pq (tasks.begin(), tasks.end());
```

The capture close of the lambda function is used to be able to capture anything by value, reference, etc. Sometimes when we want to have a state inside of the lambda we use the capture.
Taking the declare type of the lambda, we do not lose any information.

```cpp
while (!pq.empty()) {
	auto task = pq.top();
	pq.pop();
	tasks.print();
}
```


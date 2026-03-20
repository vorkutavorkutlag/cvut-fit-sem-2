
Shallow copying a struct containing a vector won't really be shallow as the vector implements the copy already, so it will actually do a deep copy.

So shallow copy is only a concept with pointers.

Shared pointer is useful in terms of avoiding memory leaks and double frees.
Used when copying objects
- pass object by value as a parameter
- return object by value
- construct object based on another w/ same class
- C++ provides compiler-defined constructor if no user-defined
- default 
	- memberwise copy, values of each data member copied to new object
- pointers
	- pointer is copied, not what it points to
	- [[Shallow Copy]] vs. [[Deep Copy]]

## Best Practices

- Provide copy constructor if class has raw pointer members
	- const reference parameter
		- prevents modification of source object
- STL classes provide copy constructors
- Avoid raw pointer members if possible


## Declaration

```cpp
Player::Player(const Player &source);
```


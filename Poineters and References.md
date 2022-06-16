# [[Pointers]]

- [[C++ Pointers]]
	- [[Arrays and Pointers]]
	- [[Passing Pointers to Functions]]
	- [[Pointer Arithmetic]]
	- [[Pointer Pitfalls]]

# [[References]]

# When to Use Pointers and References

- [[Pass by Value]]
	- Function does not modify actual parameter
	- Parameter is small and efficient to copy
		- int, char, double, etc.
- [[Pass by Reference]]
	- Pointer
		- Function does modify actual parameter
		- Parameter is expensive to copy
		- Okay for pointer to have nullptr value
	- Pointer to `const` variable
		- Function does not modify actual parameter
		- Parameter is expensive to copy
		- Okay for pointer to have nullptr value
	- `const` pointer to a `const` variable
		- Function does not modify actual parameter
		- Parameter is expensive to copy
		- Okay for pointer to have nullptr value
		- Don't want to modify pointer itself
	- Reference
		- Function does modify actual parameter
		- Parameter is expensive to copy
		- Parameter will never be nullptr
	- `const` reference
		- Function does not modify actual parameter
		- Parameter is expensive to copy
		- Parameter will never be nullptr
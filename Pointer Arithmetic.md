# [[C++]]

Only makes sense with raw arrays

## Increment (`++`) and Decrement (`--`) Operators 

- Point to neighboring addresses in memory
	- considers size of data type
		- if 4 byte int, will increment by 4 addresses

## Addition and Subtraction

- increment/decrement pointer by `n * sizeof(type)`

```cpp
// increment
int_ptr += n;
// or
int_ptr = int_ptr + n;

// decrement
int_ptr -= n;
// or
int_ptr = int_ptr - n;
```

- Subtracting pointers
	- Determines number of elements between pointers
	- must point to same data type

## Comparison (`==`. `!=`)
- Determine if two pointers point to same location
	- does ***not*** compare data where they point
		- value can be the same, but in different location
- Determine if pointers have same value
	- [[Dereferencing|Dereference]] pointers, then compare
		- `*score_ptr++` operates right to left
			- increments pointer, then dereferences
		- `(*score_ptr)++`
			- dereferences pointer, then increments dereferenced value
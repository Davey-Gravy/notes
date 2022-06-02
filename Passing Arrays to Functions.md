# C++

```c
void print_array(int numbers []);
```

- Array elements are ***not*** copied
	- array name -> memory address of the array
	- memory address is copied
- Function does not know size of the array
	- only knows memory address of array 
		- memory address of array = memory address of first element in array

Example (doesn't work)

```c
void print_array(int numbers []);

int main() {
	int my_numbers[] {1,2,3,4,5};
	print_array(my_numbers);
	return 0;
}

void print_array(int numbers []) {
	// does not know size of array
}
```

Example (does work)

```c
void print_array(int numbers [], size_t size);

int main() {
	int my_numbers[] {1,2,3,4,5};
	print_array(my_numbers, 5);
	return 0;
}

void print_array(int numbers [], size_t size) {
	for (size_t i{0}; i<size; i++) {
		cout << numbers [i] << endl;
	}
}
```

- Modifies elements of the array
	- not working with a copy of values
	- passed the actual memory address
	- define array as `const` to avoid modification
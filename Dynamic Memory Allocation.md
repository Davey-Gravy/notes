Allocating storage from the heap at runtime

- Ideally we know how much storage we need from the outset, but often we don't know how much storage we will need
	- We can allocate storage at runtime
- - Use [[Pointers|pointers]] to access newly allocated heap storage

# [[C++]]

- [[C++ Arrays]]
	- Need to provide size
		- fixed size
- [[C++ Vectors]]
	- Dynamic size
		- use techniques to allocate/deallocate from heap

## Allocate

Use `new` to allocate storage:

```cpp
// define pointer to integer
int *int_ptr {nullptr};
// allocate memory for integer on heap
int_ptr = new int;			
// prints memory address
cout << int_ptr << endl; 	
// prints garbage, didn't initialize
cout << *int_ptr << endl;	

*int_ptr = 100;
cout << *int_ptr << endl;	// 100
```

Variables
* Allocated storage on the heap
* Contain garbage until initialized
* Does not have a name
	* only accessible via pointer
		* if lost due to scoping or reassignment without deleting
			* memory leak!

Arrays:

```cpp
// define int array pointer, size
int *array_ptr {nullptr};
int size {};

cout << "What size array do you want? ";
cin >> size;
// allocate memory for int array on heap
arry_ptr = new int[size];

```

## Deallocate

Use `delete` to deallocate storage:

```cpp
int *int_ptr {nullptr};

int_ptr = new int;
...
delete int_ptr;	
```

Arrays:

```cpp
// define int array pointer, size
int *array_ptr {nullptr};
int size {};

cout << "What size array do you want? ";
cin >> size;
// allocate memory for int array on heap
arry_ptr = new int[size];
...
delete [] array_ptr;
```
# [[C++]]

## Declaration/Initialization

Declaration:

```cpp
variable_type *pointer_name;

int *int_pointer;
double *double_pointer;
char *char_pointer;
string *string_pointer;
```

Initialization:

```cpp
variable_type *pointer_name {nullptr};

int *int_pointer {};
double *double_pointer {nullptr};
char *char_pointer {nullptr};
string *string_pointer {nullptr};
```

Ensure that pointers are initialized
- point randomly otherwise -> garbage data
- initialize to zero or `nullptr` points to address zero
- type of pointer and variable must match

## Accessing and Storing Addresses

- `&`
	- address operator
	- unary (like binary but one) operator
	- returns address of the operand
		- operand cannot be const or temp expression
	
```cpp
int num{10};

cout << "Value of num is: " << num << endl; 	// 10
cout << "sizeof num is: " << sizeof num << endl; // 4 (bytes)
cout << "Address of num is: " << &num << endl; 	// 0x61ff1c
```

```cpp
int *p;

cout << "Value of p is: " << p << endl; // 0x61ff60 (garbage)
cout << "sizeof p is: " << sizeof p << endl; // 4 (bytes)
cout << "Address of p is: " << &p << endl; 	// 0x61ff18

p = nullptr; // tell p to point nowhere

cout << "Value of p is: " << p << endl; // 0
```

## Size

The size of a pointer and the size of what it points to are different

All pointers in a program have the same size, but could point to types of very small/large types

##


- Storing addresses
- Dereferencing
- Dynamic memory allocation
- Arithmetic
- [[Arrays]]
- [[Pass by Reference]]
- `const`
- Raw vs. Smart Pointers
	- smart pointers safer to use
		- [[Object-Oriented Programming (OOP) | OOP]]
	- 
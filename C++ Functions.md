# Overview

Allow for modularization of programs

- Logically separated, self-contained units
- Reusable
- Abstraction
	- hide internal mechanisms of code

# Prototypes

Compiler needs to know about functions before they are used

- Define function before calling
	- works in a pinch
	- not as scalable
- Use function prototypes
	- Provides necessary information to compiler without full function definition
	- "Forward declarations"
	- Placed at beginning of program
	- header files

```c
int function_name(); // prototype

int function_name(int);

int function_name(int a);

int function_name () { // full definition
	return 0;
}
```

# Parameters

We can pass data into a function when calling it

- In the function call -> ***arguments***
- In the function definition -> ***parameters***

Must match in number, order, and type

```c
void say_hello(std::string name) {
	cout << "Hello " << name << endl;	
}

// compiler converts C-style string to C++ string
say_hello("Frank"); 
```

Pass-by-value (default argument pass to function)

- copy of data is passed to function
- changes made to parameter in function (formal) do not affect argument that was passed in (actual)

Formal and Actual parameters

- formal
	- parameter defined in function header
- actual
	- parameter used in function call (argument)

# Default Argument Values

Functions can be defined such that if an argument is not passed into the function, a default parameter may be used
- Best practice -> define in [[C++ Functions#Prototypes| function prototype]]

```c
// without default arguments
double calc_cost (double base_cost, double tax_rate);

double calc_cost (double base_Cost ,double tax_rate) {
	return base_cost += (base_cost * tax_rate);
}

int main() {
	double cost {0};
	cost = calc_cost(100.0, 0.06);
	return 0;
}
```

```c
// with default arguments
double calc_cost (double base_cost, double tax_rate==0.06);

double calc_cost (double base_Cost ,double tax_rate) {
	return base_cost += (base_cost * tax_rate);
}

int main() {
	double cost {0};
	cost = calc_cost(200.0);		// uses default argument
	cost = calc_cost(100.0, 0.08);	// does not
	return 0;
}
```

# Overloading

Functions with different parameter lists, but the same name
- Compiler looks at types of arguments, function definition/prototype, decides which version to use
	- Return type not considered by compiler
- Polymorphism -> same concept in different application


```c
// prototypes
int add_numbers(int, int);
double add_numbers(double, double);

int main() {
	cout << add_numbers(10, 20) << endl;
	cout << add_numbers(10.0, 20.0) << endl;
	return 0;
}

// definitions
int add_numbers(int a, int b) {
	return a + b;
}

double add_numbers(double a, double b) {
	return a + b;
}
```

# Passing Arrays to Functions

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

# Pass by Reference

Elements of arrays can be changed within functions

Maybe being able to change other variable types would be useful

Use the address of the actual parameter

Formal parameter becomes an alias for the actual parameter

- formal/actual distinction ignored

```c
void scale_number(int &num);
// & indicates reference to variable

int main() {
	int number {1000};
	scale_number(number);
	cout << number << endl;
	return 0;
}

void scale_number(int &num) {
	if (num > 100) {
		num = 100;
	}
}
```

Pass by value:

```c
void print(std::vector<int> v);

int main() {
	std::vector<int> data {1,2,3,4,5};
	print(data);
	return 0)
}

void print(std::vector<int> v) {
	for (auto num: v) {
		cout << num << endl;
	}
}
```

Makes copy of actual parameter, increasing memory usage

Pass by reference:

```c
void print(const std::vector<int> &v);

int main() {
	std::vector<int> data {1,2,3,4,5};
	print(data);
	return 0)
}

void print(const std::vector<int> &v) {
	for (auto num: v) {
		cout << num << endl;
	}
}
```

Passes reference to actual parameter, making formal parameter an alias of the actual parameter

Additional memory does not need to be allocated
# Overloading

Functions with different parameter lists, but the same name
- Compiler looks at types of arguments, function definition/prototype, decides which version to use
	- Return type not considered by compiler
- Polymorphism -> same concept in different application

## [[C++]]
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
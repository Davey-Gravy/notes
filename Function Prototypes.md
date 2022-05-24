# [[C++]]

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
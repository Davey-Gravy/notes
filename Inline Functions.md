# [[C++]]

- Avoid function call overhead
- Generate inline assembly code -> faster
- Could lead to duplication of code, bloat
	- usually used in header (`.h`) files
- Some compilers automatically make function inline, don't worry about defining them

```c
inline int add_numbers(int a, int b) {
	return a + b;
}

int main() {
	int result {0};
	result = add_numbers(100, 200);
	return 0;
}
```
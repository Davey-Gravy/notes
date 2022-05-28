# [[Pass by Reference]]

- Formal parameter is a pointer
- Actual parameter is a pointer or address of variable

```cpp
void double_data(int *int_ptr);

void double_data(int *int_ptr) {
	*int_ptr *= 2;
}
```
- Function parameter is pointer to integer
	- Function call expects address to integer

```cpp
int main() {
	int value {10};
	
	cout << value << endl; // 10
	
	double_data(&value);
	
	cout << value << endl; // 20
}
```
Allow for modularization of programs

- Logically separated, self-contained units
- Reusable
- Enable abstraction
	- hide internal mechanisms of code

# Related Concepts

- [[Function Prototypes]]
- [[Function Parameters]]
- [[Default Argument Values]]
- [[Function Overloading]]
- [[Passing Arrays to Functions]]
- [[Pass by Value]]
- [[Pass by Reference]]
- [[Function Calls]]

# C++

```c
using namespace std

void add_numbers(int a, int b){
	return a + b;
}

int main() {
	cout << add_numbers(5, 10) << endl;
}
```
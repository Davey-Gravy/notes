- "No-args" constructor
	- Expects no arguments
- [[C++]] automatically generates default constructor if no constructors defined
	- compiler will error if arguments do not match user-defined constructor
	- default constructor not generated

```cpp
class Dog {
	private:
		string name;
		int age;
	public:
		// no-args constrcutor
		Dog() {
			name = "Max";
			age = 0;
		}
}
```
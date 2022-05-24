# [[C++]]

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

[[Pass-By-Value]]l)

[[Formal and Actual Parameters]]
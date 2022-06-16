# C++

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
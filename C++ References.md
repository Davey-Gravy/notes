# C++
```cpp
int main() {
	
	// reference is alias to variable
	int num {100};
	int &ref{num};
	
	cout << num << endl; // 100
	cout << ref << endl; // 100
	
	// can change variable
	num = 200;
	cout << num << endl; // 200
	cout << ref << endl; // 200
	// or reference
	ref = 300;
	cout << num << endl; // 300
	cout << ref << endl; // 300
}
```
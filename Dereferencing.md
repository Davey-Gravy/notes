Accessing data [[Pointers|pointer]] points to


# [[C++ Pointers]]
- `*`
	- dereferencing operator
	- same operator as declaring pointer

```cpp
int score {100};
int *score_ptr {&score};

cout << *score_ptr << endl;		// 100

*score_ptr = 200;
cout << *score_ptr << endl;		// 200
cout << score << endl;			// 200
```
- Pointer (*) points to reference (&) to memory address
- Dereferencing pointer will return value in memory address


```cpp
double high_temp {100.7};
double low_temp {37.4};
double *temp_ptr {&high_temp};

cout << *temp_ptr << endl; // 100.7

temp_ptr = &low_temp;
cout << *temp_ptr << endl; // 37.4
```
Changing the reference `temp_ptr` points to changes the value when dereferencing

```cpp
string name {"Frank"};
string *string_ptr {&name};

cout << *string_ptr << endl; // Frank
name = "James";
cout << *string_ptr << endl; // James
```

Changing the value of `name` changes the value when dereferencing `string_ptr`

```cpp
vector<string> stooges {"Larry", "Moe", "Curly"};
vector<string> *vector_ptr {nullptr};

vector_ptr = &stooges

cout << "First stooge: " << (*vector_ptr).at(0) << endl; // Larry 

cout << "Stooges: ";
for (auto stooge: *vector_ptr)
	cout << stooge << " ";
cout << endl;
```

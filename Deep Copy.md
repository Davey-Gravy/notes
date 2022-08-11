- Doesn't copy the pointer
- Copies data that pointer points to
	- same value, different memory location
- Use when raw pointer is a class data member

```cpp
Deep::Deep(const Deep &source)
{
	data = new int;
	*data = *source.data;
}
```

[[Delegating Constructors|Delegate]]

```cpp
Deep::Deep(const Deep &source)
	: Deep{*source.data} {
		cout << "Copy constructor - deep" << endl;
}
```
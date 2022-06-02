* Value of an array name is the address of first element in array
* Value of pointer variable is address
* If pointer points to same data type as array element, pointer and array name can be used (almost) interchangeably

```cpp
int scores[] {100, 95, 89}

// prints address of first element
cout << scores << endl;
// prints value of first element
cout << *scores << endl;

*int score_ptr {scores};
// also prints address of first element
cout << score_ptr << endl;
// also prints value of first element
cout << *score_ptr << endl;
```

Can do array subscripting on pointers:

```cpp
int scores[] {100, 95, 89};

int *score_ptr {socres};

cout << score_ptr[0] << endl;
cout << score_ptr[1] << endl;
cout << score_ptr[2] << endl;
```

| Subscript notation   | Offset notation         |
| -------------------- | ----------------------- |
| `array_name[index]`  | `*(array_name + index)` |
| `pointer_name[index]` | `*(pointer_name + index)`                        |

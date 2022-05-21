# Characteristics

- Fixed size
- Compound data type
	- Collection of elements of the same type
- Elements can be accessed directly
- Stored contiguously in memory
- First element at index 0
- Last element at index size-1
- No bounds checking
- Always initialize

```c
int test_score_1 {0};
int test_score_2 {0};
int test_score_3 {0};

// or

int test_scores[3] {0};
```

# Declaration and Initialization

```c
element_type array_name[number_of_elements] {initialization};
```

```c
int test_scores[5];

const int days_in_year {365};
// init all to zero
double hi_temperatures[days_in_year] {0}; 

// automatic sizing
int another_array [] {1, 2, 3, 4, 5}; 
```

# Accessing and Modifying Elements

```c
int test_scores [5] {100, 95, 99, 87, 88};

// access: array_name[element_index]
cout << test_scores[0] << endl;
// 100

// modify: array_name[element_index] = value
test_scores[4] = 84;
// test_scores [5] {100, 95, 99, 87, 84} 
```
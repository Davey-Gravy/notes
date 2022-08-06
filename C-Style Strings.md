# C-Style Strings

- Sequence of characters
	- contiguous in memory
	- array of characters
	- terminated by null character (zero)
		- zero/null terminated string

## String Literal

- Sequence of characters with double quotes
	- "Frank"

## String Variables

```cpp
char my_name [5] {"Frank"};
Frank\0
```

- Defined character array of size 5
	- "Frank" takes up indices 0-4
	- String terminated by null character (\0)
```cpp
my_name[5] = 'y';
```

- Won't work
	- replaces terminating null character

```cpp
char my_name [8] {"Frank"};
Frank\0\0\0
```

- Defined character array of size 8
	- "Frank" takes up indices 0-4
	- String terminated by 3 null characters

```cpp
my_name[5] = 'y';
```

- Will work
	- replaces first null character
		- not terminating null character

## \#include \<cstring>

Functions to handle C-style strings

- Copying
	- `strcopy()`
- Concatenation
	- `strcat()`
- Comparison
- Searching

## \#include \<cstdlib>

Functions that convert C-style strings to:
- integer
- flaot
- long
- etc.
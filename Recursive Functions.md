A function that calls itself either directly or indirectly through another function

Certain problems are handled well using recursion

- Sorting and Ssrting
	- binary search
	- search trees
- Mathematical series
	- Fibonacci
	- factorial
	- fractals

# [[C++]]

## Factorials

How to solve factorials with recursion:

```c
unsigned long long factorial(unsigned long long n) {
	if (n==0)
		return 1;	// base (initial) case
	return n * factorial(n-1);	// recursive case
}

int main() {
	cout << factorial(3) << endl;
}

```

Recursive function calls get pushed onto stack until `n = 0`

For `n = 3`:

- main
	- sees `factorial(3)`,  pushed on stack
- factorial(3)
	- sees `factorial(2)`, pushed on stack
- factorial(2)
	- sees `factorial(1)`, pushed on stack
- factorial(1)
	- sees `factorial(0)`, pushed on stack 
- factorial(0)
	- returns 1
	- popped off stack
- factorial(1)
	- returns 1 * 1 = 1
	- popped off stack
- factorial(2)
	- returns 2 * 1 = 2 
	- popped off stack
- factorial(3)
	- returns 3 * 2 = 6
	- popped off stack
- main
	- returns 6
	- popped off stack
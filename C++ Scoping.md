- local (blocks)
	- only active, accessible to the local function or block
		- inner blocks can see outer blocks, not vice versa
	- not preserved between function calls
- global
	- declared outside function or class
	- accessible throughout the program
	- okay to use constants
		- be careful with variables
- `static` 
	- initialized once on first function call
	- retains value between function calls
	- behaves as a global variable for its function


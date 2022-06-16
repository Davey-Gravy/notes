# [[C++]]

- Function call/program stack
	- think of a stack of books
	- LIFO -> last in first out
	- push and pop
- Stack Frame, Activation Record
	- function call creates an activation record which is pushed on the stack
	- activation record popped after function termination and returned
	- local variables and function parameters allocated on stack
- Stack Overflow

Example

- main
	- pushes space on stack for return value
	- pushes space on stack for function parameters
	- push the return address
	- transfer control to helper function (jump)
- helper function
	- push address of previous activation record
	- push register values 
	- perform code
	- restore register values
	- restore previous activation record
		- move stack pointer
	- store function results
	- transfer control to the return address
- main
	- pop parameters
	- pop return value
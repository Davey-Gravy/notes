Date: 20/10/2021
## Summary
- view routes as a graph/network
	- nodes + arcs
- well-established problem
	- generalized version of traveling salesman
		- visit all nodes, return to main node
		- maximize efficiency -> minimize cost
		- NP-hard problem, solved with:
			- ant algorithm
			- genetic algorithm
			- others
	- minimize 
		- cost / distance time / pollution
		- number of vehicles
	- related to warehouse optimization
	- simple if each car has same capacity
- used Google OR-Tools
	- python package
- proper routing optimization can lower costs by 13%
## Discussion
- Why use OR-Tools?
	- Vast library, more choices
		- Specific module for routing problem

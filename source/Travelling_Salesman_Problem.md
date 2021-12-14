# Travelling Salesman Problem
Date: 27/10/2021

## Summary
Minimize distance while visiting all locations
- NP hard --> use heuristics to find "good enough" solution

## Implementation
Based on mouse looking for cheese in maze
- Generates maze, place pieces of cheese
	- Find distance between each piece of cheese
		- Convert maze into graph
		- Use Dijkstra algorithm
			- Finds shortest path between point a and b
			- creates weighted graph
		- Greedy algorithm
			- go to the closest non-taken cheese
			- only one-step into the future

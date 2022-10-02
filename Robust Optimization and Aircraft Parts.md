Date: 27/10/2021

## Summary
Overview of robust optimization

Rotable optimization
- spare part inventory management
	- purchase
	- exchange
	- repair
- if part malfunctioning, can result in:
	- "no-go"
	- plane can fly for 3 days, 10 days, 30 days
		- based on severity

## Model
Implmeneted in both Excel and GurobiPy
- for a specific bolt
- branch and bound simplex
- similar results
- could be more effective if dynamically updated as parts used
- other parameters could be included
	- inventory cost, etc.

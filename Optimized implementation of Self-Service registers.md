# Optimized implementation of Self-Service registers
Date: 20/10/2021
## Summary
Self-service registers installed throughout Iceland (Bonus, Kronan)
- Why?
	- Shorter lines
	- Better use of human resources
	- Reduced labor cost
### Formulation
#### Data
- Cost of register: $30,000
- Cost of employee $4,000/month
- 1 employee per manual register
- 1 employee per self-service area
- area considerations
Minimize monthly cost of checkout process
#### Constraints
- space
- minimum registers
- Customer satisfaction
	- 33% of registers must be manual
#### Results
- In store's interest to move completely to self-service
	- but need to consider customer satisfaction
	- customers get used to self-service as time passes
		- added progressive term to model this
	- Less than 8 month pay off time for each register
## Discussion
Effect of store size?
- More likely to have larger orders? 
	- Too lazy to do self-service?

#OPTI #optimization 
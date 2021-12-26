# Hydropower
Uses modified Hotelling model

Must regulate:
1. Supply of energy over yearly cycle
	- low demand in summer
	- high demand in winter
2. Current supply
	- most flexible balancing power

Assume we have a reservoir:
- Want to find the time pattern of water use in the reservoir
- Water used for power today could be used tomorrow
- Aim to maximize social surplus
- Assumed that hydro generation has zero marginal cost

### Cost Struccture
- Not considering new investments, want to find optimal management for existing capacities

### Variables
- $R_t\quad$ amount in reservoir
- $w_t\quad$ inflow of water
- $r_t\quad$ outflow of water

Use a transformation coefficient to translate water flow to electricity
- $e_t^H \leq \frac{1}{a}r_t$

Water management based on filling and emptying reservoir:
$$R_t \leq R_{t-1} + w_t -e^H_t$$
- conservation of water in reservoir

### Basic Hydro Model
Assumptions:
- unlimited transferability b/w time periods
	- infinite reservoir
- no emptying of reservoir until last period
- start with water "endowment"
	- amount of water to use over time horizon *T*
- no discounting (short period)
- Electricity production during each time period is equal to the endowment
$$\underbrace{\sum_{t=1}^T e_t^H}_{\substack{\text{Total} \\ \text{production}}}=\underbrace{W}_{\substack{\text{Water} \\ \text{enodowment}}}$$
- demand function is marginal utility
	- marginal willingness to pay --> demand

Optimization problem:
- Maximize sum of utilities from electricity consumption for the given time period, without using more electricity than the water endowment provides
$$\text{max}\quad\sum_{t=1}^TU_t(e_t^H)$$
$$\text{subject to}\quad\sum_{t=1}^Te_t^H\leq W, e_T^H \geq 0, t= 1,\dots,T$$
#### Results
- Solution: how to allocate water over time to maximize surplus
- Shadow price
	- Change in sum of utilities due to a change in water endowment
		- 0 if the reservoir is not emptied
		- marginal utility is constant, equal to shadow price

#### Bathtub Diagram
Looks at two periods
- "x" axis is total energy for both periods
	- assume all water is used
- left y-axis price for period 1
- right y-axis price for period 2
- demand curves
	- left to right for period 1
	- right to left for period 2
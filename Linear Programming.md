# Linear Programming

Method of formulating a ***linear*** system of equations and ***linear*** constraints to find its optimal solution.

## Wyndor Glass Example

A glass product company has two main products in their lineup: a glass door with aluminum framing and a wood-framed window, each with their levels of profit The company owns three plants, each with varying production capacity for each product. Product 1 requires production hours from Plants 1 and 3, while Product 2 is made in Plants 2 and 3. Therefore the two products are competing for the same allocation of production hours in Plant 3. How many of each product will yield the highest profit?

-tx-
|                    | Production Time per Batch (hours) ||                                                |     
| :-----------------:|:---------------------------------:| :-----: | ------------------------------------- | 
|                    |            **Product**            ||                                                |     
| **Plant**          |               **1**               | **2** | **Production Time Available per Week (hours)** |     
| 1                  |                    1               |     0  |             4                              |     
| 2                  |                0                   |    2   |                12                          |     
| 3                  |                3                   |  2     |          18                                |     
| *Profit per batch* |                $3,000              |  $4,000     |                                  |     
[Data for the Wyndor Glass Example]
This can be written as:

$$
\begin{alignat}{3}
	\text{max} 	\quad &&& \mathrlap{z = 3x_1+5x_2}\\
	\text{s.t}	\quad &&&& x_1 &\leq 4 \\
					  &&&& 2x_2 &\leq 12 \\
					  &&&& 3x_1+2x_2 &\leq18 \\
					  &&&& x_1, x_2 &\geq 0
\end{alignat}
$$

Tools such as the [[Simplex Method]] can be used to determine the optimal solution.

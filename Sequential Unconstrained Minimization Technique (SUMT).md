# Sequential Unconstrained Minimization Technique (SUMT)

Add a barrier function to objective to keep it from leaving the feasible solution area
- want terms of barrier function to be small
	- grows larger as approaches solution boundaries
	- *r* acts as weight for penalty function
		- increases if solution is near boundary 

## Example

$$
\begin{alignat*}{3}
	\text{mat} \quad &&& \mathrlap{-x_1^2+2x_1-x_2^2+3x_2} \\
	\text{s.t.}\quad &&&& x_1+x_2&\leq2 \\
					 &&&& x_1, x_2&\geq0
\end{alignat*}
$$

Rewrite as:

$$
P(x, r) = -x_1^2+2x_1-x_2^2+3x_2-r\bigg(\frac{1}{2-x_1-x_2}+\frac{1}{x_1}+\frac{1}{x_2}\bigg)
$$
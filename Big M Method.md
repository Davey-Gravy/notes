# Big M Method
- Variant of the [[Simplex Method]]
- Used if the origin is not part of the initial basis
	- Equality constraints
	- Negative right-hand sides
	- Constraints in &ge; form
- Analog to the [[Two-Phase Simplex Method]]
##  Example
$$
\begin{alignat}{3}
	\text{max}	\quad &&& \mathrlap{z = 3x_1+5x_2}\\
	\text{s.t.}	\quad &&&& x_1 &\leq 4\\
				\quad &&&& 2x_2 &\leq 12\\
				\quad &&&& 3x_1+2x_2 &= 18\\
				\quad &&&& x_1,x_2 &\geq 0
\end{alignat}
$$
Add slack variables to get standard form:
$$
\begin{alignat}{3}
	\text{max}	\quad &&& \mathrlap{z = 3x_1+5x_2}\\
	\text{s.t.}	\quad &&&& x_1 + s_1 &= 4\\
				\quad &&&& 2x_2 + s_2 &= 12\\
				\quad &&&& 3x_1+2x_2 &= 18\\
				\quad &&&& x_1,x_2,s_1,s_2 &\geq 0
\end{alignat}
$$
Need to add an artificial variable to constraint that was initially  an equality. The cost of the artificial is $M$, a very large number:
$$
\begin{alignat}{3}
	\text{max}	\quad &&& \mathrlap{z = 3x_1+5x_2-Ma_1}\\
	\text{s.t.}	\quad &&&& x_1 + s_1 &= 4\\
				\quad &&&& 2x_2 + s_2 &= 12\\
				\quad &&&& 3x_1+2x_2 + a_1 &= 18\\
				\quad &&&& x_1,x_2,s_1,s_2,a_1 &\geq 0
\end{alignat}
$$
- If the objective function is to be maximized, $a_1$ must equal 0 since it will drive the function's value down
- If $a_1 \geq 0$ in the optimal solution, the problem is not feasible


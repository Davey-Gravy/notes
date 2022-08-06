# Two-Phase Simplex Method
If there is a constraint with a = sign, can't use normal simplex method. Simplex method searches for corner points of feasible solution area, but if the origin is not part of the feasible solution area, need to use either the [[Big M Method]] or Two-Phase Simplex Method:
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
Need to add an artificial variable to constraint that was initially  an equality:
$$
\begin{alignat}{3}
	\text{max}	\quad &&& \mathrlap{z = 3x_1+5x_2}\\
	\text{s.t.}	\quad &&&& x_1 + s_1 &= 4\\
				\quad &&&& 2x_2 + s_2 &= 12\\
				\quad &&&& 3x_1+2x_2 + a_1 &= 18\\
				\quad &&&& x_1,x_2,s_1,s_2,a_1 &\geq 0
\end{alignat}
$$
- Phase 1: used to find a basic feasible solution to initial problem
	- Objective function becomes minimization of artificial variables: $$\text{min}\quad z = a_1$$
- Phase 2: finds an optimal solution to the real problem
	- Use the solution of Phase 1 as initial solution for second phase
	- Revert to original objective function
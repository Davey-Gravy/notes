# Quadratic Programming

Only difference from [[Linear Programming]] is inclusion of $x_j^2$, $x_ix_j$ $(i\neq j)$ terms. Quite a difference in formulation, however.

## General form

$$
\begin{alignat}{3}
	\text{max}	\quad &&& 	\mathrlap{f(\textbf{x}) = \textbf{cx}-\frac{1}{2}\textbf{x}^T\textbf{Qx}}\\
	\text{s.t.}	\quad &&&&	\textbf{Ax} &\leq \textbf{b}\\
					  &&&&	\textbf{x} &\geq 0
\end{alignat}
$$

Objective function given as:
$$f(x) = \textbf{cx} - \frac{1}{2}\textbf{x}^T\textbf{Qx}=\sum_{j=1}^nc_jx_j-\frac{1}{2}\sum_{i=1}^n\sum_{j=1}^nq_{ij}x_ix_j$$
$\textbf{c}$ is given by the linear terms in $x$.

So if $i = j$, then $x_ix_j = x^2$, so its coefficient is $-\frac{1}{2}q_{ij}$.

When $i\neq j$, we get $-\frac{1}{2}(q_{ij}x_ix_j+q_{ji}x_jx_i)=-q_{ij}x_ix_j$, so $-q_{ij}$ is the coefficient for $x_ix_j$.

Because of this, the matrix $\textbf{Q}$ is always symmetric.

## Example

Given as:

$$
\begin{alignat}{3}
\text{max}\quad &&& \mathrlap{f(x_1, x_2) = 15x_1 + 30x_2 + 4x_1x_2 - 2x_1^2-4x_2^2} \\
\text{s.t}\quad &&&& x_1 + x_2 &\leq 30 \\
				&&&& x_1,x_2 &\geq 0
\end{alignat}

$$

Rewrite as:

$$
\textbf{Q} = \begin{bmatrix}
q_{11}& q_{21}\\
q_{12}& q_{22}
\end{bmatrix}
=
\begin{bmatrix}
4 & -4\\
-4 & 8
\end{bmatrix}
$$

$$
\textbf{c} = 
\begin{bmatrix}
	15 & 30
\end{bmatrix}
$$

$$
\textbf{x} = 
\begin{bmatrix}
	x_1\\
	x_2
\end{bmatrix}
$$

## Modified Simplex Method
1. Find [[KKT Conditions]]
2. Rewrite the linear constraints into standard form 
Write in form:

$$
\begin{alignat}{3}
	\textbf{Qx} + \textbf{A}^T\textbf{u} - \textbf{y} &= \textbf{c}^T\\
	\textbf{Ax} + \textbf{v} &= b\\
	\textbf{x}, \textbf{u}, \textbf{y}, \textbf{v} &\geq 0\\
	\textbf{x}^T\textbf{y} + \textbf{u}^T\textbf{v} &= 0
\end{alignat}
$$

3. Often need artificial variables, use [[Two-Phase Simplex Method]]
4. Complementary constraint:
	- Final constraint says one variable of each pair must be zero
		- Simplex: cannot be in basis at the same time
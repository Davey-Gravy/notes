# Differential Equations
Definition: a mathematical expression containing a function and one or more of its derivatives

$$
\frac{d^ny(x)}{dx^n}+\dots+\frac{dy(x)}{dx}+y(x)=f(x)
$$

## First-Order Linear Differential Equations

A ***first-order*** differential equation contains only first derivatives of the function

A ***linear*** differential equation can be written as a sum of multiples of the function and its derivatives

A differential equation with scalar multipliers has ***constant coefficients***

$$
b_n\frac{d^ny(x)}{dx^n}+\dots+b_1\frac{dy(x)}{dx}+b_0y(x)=f(x)
$$

A differential equation whose *forcing function*, or right hand side, is equal to zero, is called ***homogeneous***

$$
b_n\frac{d^ny(x)}{dx^n}+\dots+b_1\frac{dy(x)}{dx}+b_0y(x)=0
$$


### Solving
$$
y'+ay=0
$$

$$
y=Ce^{-at}
$$
#### Example

$$
\begin{align}
\frac{dy}{dt}-5y&=0\\
y(0)&=3
\end{align}
$$
##### Solution
$$
y=Ce^{-5t}
$$

$$
3=Ce^{(0)t}
$$

$$
C=3
$$

$$
\boxed{y=3e^{-5t}}
$$

## Second-Order Linear Differential Equations
A ***second-order*** differential equation contains both first *and* second derivatives of the function

$$
y''+ay'+by=0
$$

Second-order differential equations often describe real-world systems such as electrical circuits, spring-mass systems, fluid flows, heat transfer, etc. The behavior of these systems is classified by the amount of ***damping*** (electrical resistance, mechanical friction, pressure drop, thermal insulation, etc.) in the system:
- underdamped
	- transient behavior gradually decays in an oscillatory manner to steady-state behavior
	- ***damping ratio*** $\zeta < 1$
	- characteristic equation has two complex roots
- overdamped
	- transient behavior decays sluggishly without oscillation to steady-state behavior
	- $\zeta>1$
	- characteristic equation has two distinct real roots
- critically damped
	- transient behavior reaches steady-state the quickest out of the three cases, without oscillation
	- $\zeta=1$
	- characteristic equation has two identical real roots

### Solving
Given the differential equation:

$$
y''+ay'+by=0
$$

rewrite as the characteristic equation:
$$
r^2+ar+b=0
$$

and find its roots

$$
r_{1,2}=\frac{-a\pm\sqrt{a^2-4b}}{2}
$$

- $a^2>4b$
	- roots are real and different
	- system is overdamped
- $a^2=4b$
	- roots are real and identical
	- system is critically damped
- $a^2<4b$
	- roots are imaginary and take the form $(\alpha+i\beta)$ and $(\alpha-i\beta)$

Solution can appear as:

$$
y=C_1e^{r_1x}+C_2e^{r_2x}
$$

$$
y=(C_1+C_2x)e^{rx}
$$

$$
y=e^{\alpha x}(C_1\cos\beta x+C_2\sin\alpha x)
$$

$$
\alpha = -a/2\qquad\beta=\frac{\sqrt{4b-a^2}}{2}
$$

#### Example
What is the general solution to this homogeneous differential equation?

$$
y''-8y'+16y=0
$$

##### Solution
$$
r^2-8r+16=0
$$

$$
r_{1,2}=\frac{8\pm\sqrt{8^2-4(16)}}{2}=4
$$

System is critically damped

$$
\boxed{y=(C_1+C_2x)e^{4x}}
$$

## Nonhomogeneous Differential Equations

$$
y(x)=y_h(x)+y_p(x)
$$

- $y_h(x)$ - complementary (homogeneous) solution
- $y_p(x)$ - particular solution

### Method of Undetermined Coefficients
A method of finding the particular solution
- can only be used if the forcing function (right hand side) is one of the following

| form of $f(x)$                    | form of $y_p(x)$                  |
| --------------------------------- | --------------------------------- |
| $A$                               | $B$                               |
| $Ae^{\alpha x}$                   | $Be^{\alpha x}$                   |
| $A_1\sin\omega x+A_2\cos\omega x$ | $B_1\sin\omega x+B_2\cos\omega x$ | 

- $A_i$, $B_i$ not known --> ***undetermined coefficients***
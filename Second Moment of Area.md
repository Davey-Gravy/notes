# Second Moment of Area

Measure of a shape's area relative to a given axis

- Can be calculated for any axis using the [[Parallel Axis Theorem|parallel axis theorem]]
- Associated with resistance to bending along a reference axis
	- a long rectangular plank laid  on the skinnier side is less resistant to bending than laid wider side down

> Second moment of area
> $$
> I_x=\int_Ay^2\,dA\qquad I_y=\int_Ax^2\,dA
> $$
> Second (polar) moment of area (by the [[Perpendicular Axis Theorem|perpendicular axis theorem]])
> $$
> J=I_x+I_y
> $$

- $x$ - distance from the y-axis
- $y$ - distance from the x-axis

## Shapes

### Rectangle

Applying this to a rectangle with base $b$ and height $h$ centered at the origin:

$$
\begin{align}
I_x&=
\int_A y^2\,dA\quad &I_y&=\int x^2\,dA\\
&=\int_{-\frac{h}{2}}^\frac{h}{2}by^2\,dA\quad&&=\int_{-\frac{b}{2}}^\frac{b}{2} hy^2\,dA\\
&=b\left[\frac{y^3}{3}\right]_{-\frac{h}{2}}^\frac{h}{2}\quad&&=h\left[\frac{y^3}{3}\right]_{-\frac{b}{2}}^\frac{b}{2}
\end{align}
$$

$$
\boxed{I_x =\frac{bh^3}{12}\qquad I_y=\frac{b^3h}{12}} 
$$

### Circle

Given a circle with radius $r$:

$$
I_x=I_y=\frac{\pi r^4}{4}
$$
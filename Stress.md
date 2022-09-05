# Stress

## Engineering Stress

### Axial Stress

Load applied on an area direct along the axis of the object:

$$
\sigma=\frac{P}{A_0}\:\left[\frac{\text{N}}{\text{m}^2}\right]=[\text{Pa}]
$$

- $P$ - load
- $A_0$ - cross-sectional area of the specimen before deformation

$$
P=\int dF=\int_A\sigma\,dA
$$

Axial stress distribution assumed to be uniform across area, acts through the centroid of the object.

### Shear Stress

Load applied on an area perpendicular to the axis of the object:

$$
\tau_\text{ave}=\frac{P}{A}
$$

Cannot be assumed to be uniformly distributed.

### Axial Loading on an Oblique Plane

Decompose $P$ into normal component $F$ and tangential component $V$:

$$
F=P\cos\theta\quad V=P\sin\theta
$$

$$
\sigma=\frac{F}{A_\theta}\quad\tau=\frac{V}{A_\theta}
$$

$$
A_\theta=A_0/\cos\theta
$$

$$
\sigma=\frac{P}{A_0}\cos^2\theta\quad\tau=\frac{P}{A_0}\sin\theta\cos\theta
$$

Naming convention:

$$
\begin{array}{c}
\tau_{xy}\\
\;\;\swarrow\;\searrow\\
\mbox{perpedicular surface}\quad \mbox{direction of component}
\end{array}
$$
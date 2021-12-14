# Aspect ratio
$$
\text{Aspect ratio} = \frac{\text{Longest side}}{\text{Shortest side}}
$$

- Want aspect ratio to be as close to 1 as possible
- ANSYS Fluent:
	- measures distance from centroid to node (corners and face centers)
- OpenFOAM:
	- 2D - directly uses side lengths
	- 3D - creates a bounding box around cell, calculates areas of each face

#meshing
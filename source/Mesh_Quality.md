# Mesh Quality
How good are our cells?
- Tetrahedrons
- Hexahedrons
- Polyhedrons

Why do bad meshes result in solution divergence?

## Recommended Mesh Quality Metrics
| Metric                     | Stable Solution | Accurate Solution | Ideal mesh |
| -------------------------- | --------------- | ----------------- | ---------- |
| [[Aspect Ratio]]           | < 1000          | < 10              | 1          |
| [[Jacobian Determinant]]   | > 0.1           | > 0.2             | 1          |
| Face [[Non-Orthogonality]] | < 70&deg;       | < 60&deg;         | 0&deg;     |
| [[Equiangle Skewness]]     | < 0.95          | < 0.9             | 0          |

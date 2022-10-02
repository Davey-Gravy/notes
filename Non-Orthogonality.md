Most important mesh quality metric affecting stability of CFD solutions

Ideally the vector connecting neighboring cell centroids $\boldsymbol{d}_{PN}$ would be parallel with the face outward normal $\hat{\boldsymbol{n}}_f$

The difference between this vector and the face outward normal is the non-orthogonality angle

$$
\boldsymbol{d}_{PN}\cdot\hat{\boldsymbol{n}}_f=|\boldsymbol{d}_{PN}||\hat{\boldsymbol{n}}_f|\cos(\theta_{\text{face}})
$$

$$
\theta_{\text{face}}=\cos^{-1}\bigg(\frac{\boldsymbol{d}_{PN}\cdot\hat{\boldsymbol{n}}_f}{|\boldsymbol{d}_{PN}||\hat{\boldsymbol{n}}_f|}\bigg)
$$

May be expressed as non-orthogonality quality:

$$
\theta_\text{quality}=1-\max(\theta_\text{face, 1},\theta_\text{face, 2},\dots,\theta_\text{face, N})
$$
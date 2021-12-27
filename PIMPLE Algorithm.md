# PIMPLE Algorithm

*From the [OpenFOAM Wiki](https://openfoamwiki.net/index.php/OpenFOAM_guide/The_PIMPLE_algorithm_in_OpenFOAM)*

A combination of the [[SIMPLE Algorithm|SIMPLE]] and [[PISO Algorithm|PISO]] algorithms
- allows for ($Co >>1$)

A steady-state solution for each time step is computed with [[Under-Relaxation|under-relaxation]] using outer correction loops
- in OpenFOAM, if `nOuterCorrectors = 1`, the PIMPLE algorithm will work in PISO mode
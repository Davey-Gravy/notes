# OpenFOAM Solvers

*From [CFD Direct](https://cfd.direct/openfoam/user-guide/v9-standard-solvers/#x13-960003.5)*

## Basic

- laplacianFoam
- potentialFoam
- scalarTransportFoam

## Incompressible

### Steady-State

- adjointShapeOptimizationFoam
- boundaryFoam
- simpleFoam
	- [[SIMPLE Algorithm]]
	- porousSimpleFoam
	- SRFSimpleFoam

### Transient

- icoFoam
- nonNewtonianIcoFoam
- pimpleFoam
	- [[PIMPLE Algorithm]]
	- SRFPimpleFoam
- pisoFoam
	- [[PISO Algorithm]]
- shallowWaterFoam

## Compressible

- rhoCentralFoam
- rhoPimpleFoam
- rhoPorousSimpleFoam
- rhoSimpleFoam

## Multiphase

###  Incompressible

- driftFluxFoam
- interFoam
	- multiphaseInterFoam
- interMixingFoam
- multiphaseEulerFoam
- potentialFreeSurfaceFoam
- twoLiquidMixingFoam

## Direct Numerical Simulation (DNS)

- dnsFoam

## Combustion

- buoyantReactingFoam
- chemFoam
- coldEngineFoam
- engineFoam
- PDRFoam
- reactingFoam
- XIEngineFoam
- XiFoam

## Heat Transfer / Buoyancy-Driven

- buoyantPimpleFoam
- buoyantSimpleFoam
- chtMultiRegionFoam
- thermoFoam

## Particle-Tracking

- denseParticleFoam
- particleFoam
- rhoParticleFoamf

## Discrete Methods

- dsmcFoam
- mdEquilibrationFoam
- mdFoam

## Electromagnetics

- electrostaticFoam
- magneticFoam
- mhdFoam

## Stress Analysis of Solids

- solidDisplacementFoam
- solidEquilibriumDisplacementFoam
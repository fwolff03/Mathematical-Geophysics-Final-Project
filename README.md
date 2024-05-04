# Mathematical Geophysics Final Project on Saint-Venant Equations
## Project Members: 
- Max Ercolani (MaxErcGP)
- Finley Wolff (fwolff03)
## Summary: 


## Background Infomation:


## Objectives:

The objective of this project is to design and carry out a simulation of the 1-dimentional, steady state Saint-Venant Equations. We aim to describe the simulation completly and show multiple states of the simulation.

## Software Packages Used:

We used the [SWE_Solver](https://github.com/DanielCortild/SWE-Solver/tree/main) or the Shallow Water Equation Solver that was created by Daniel Cortild and is public on Github. It solves equations such as the Saint-Venant partial diferntial equations. 

First we attempted to use [FiPy](https://www.ctcms.nist.gov/fipy/), a widely used partial differential equation solver. It is capable of solving couppled PDE's as well as non-linear PDE's which was mandatory for our project.

## How to Recreate Simulations

1) pip install SWE_Solver
2) import plotSWE from the SWE_Solver package
3) define the following parameters - all are necessary to carry out the simulation
  - B (Bottom topography function)
  - h0 (Initial water height profile)
  - u0 (Initial water velocity profile)
  - Nx (Number of spatial grid points)
  - tEnd (End time of the simulation)
  - timePoints (List of time points at which you want to visualize the results)
4) run the SWE_Solver function, h, u = plotSWE(B, h0, u0, Nx, tEnd, timePoints, g=1, method='C')
  - this function will solve for h, water depth, and u, stream velocity at each point along the length of the channel
  - g is the gravitational constant
  - method selection ('A', 'B' or 'C')
    - c is the default
## Contribution Statement:


## References:


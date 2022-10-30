---
uid: "contribution/stablefluids"
uid-meta: "contribution/stablefluids-meta"
comments: 
 items: 
  - uid: "246738"
  - uid: "246752"
  - uid: "246753"
  - uid: "246754"
  - uid: "246755"
  - uid: "246756"
  - uid: "246757"
  - uid: "246759"
  - uid: "246761"
  - uid: "246903"
  - uid: "246914"
uid-files: "contribution/stablefluids-files"
title: "StableFluids"
image: "fluidCrop.png"
contribution: "true"
---

This project was a research project for the **#node17** visuals and wasn't really aimed for production. It quite strictly reproduces the credited paper, since it mainly served as a reference for evaluating other algorithms and implementation attempts. The only deviations are the additional vorticity confinement routines, eliminating the restriction to a square and evenly spaced base grid, and using Jacobi instead of Gauss-Seidel solver in order to benefit from SIMD instructions.

The repo demonstrates one way how to take advantage of c++'s native speed (SSE instructions) in vvvv without the need for two separate dlls and interop.

<https://github.com/woeishi/StableFluids> for detailed info

##  Nodes
all nodes come 2d and 3d versions
* StableFluid: Creates and holds a fluid simulation space
* Evaluate: Drives the fluid simulation, giving access to global parameters
* SetVelocity / SetDensity: Sets the velocities/densities of the entire fluid simulation space
* AddVelocity / AddDensity: Adds velocities/densities to the entire fluid simulation space
* AddRadialVelocity / AddRadialDensity: Adds velocities/densities around the given center to the fluid simulation space (think of it as an emitter)
* AddRadial: Adds velocities and densities around the given center to the fluid simulation space
* GetVelocity / GetDensity: Returns the velocities/densities of the enire fluid simulation space
* Split: Returns the velocities and densities of the enire fluid simulation space

<div class="box">
Note:
please check [this list](https://en.wikipedia.org/wiki/Advanced_Vector_Extensions#CPUs_with_AVX) if your cpu is compatible
</div>

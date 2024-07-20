---
layout: page
title: Houdini Mini Tasks
description: Geometry and Simulation
img: assets/img/houdini/heat.png
importance: 1
category: project
---

A collection of mini projects about geometry and simulation with Houdini. Codes are written in VEX and Python.

## Geometry
### Poisson Problem
Positive and negative charges are set at the red and blue poles. Build a surface Laplacian operator first and use that to solve the Poisson equation to obtain electirc potential.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/houdini/poisson.png" title="Poisson Equation" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
</div>
<div class="caption">
    Using surface Laplacian to solve Poisson equation.
</div>

### Geodesic Distance using Heat Equation
To solve geodesic distance, build a Lplacian operator first. Then setup initial impulse at points according to corresponding point areas. Next, evolve Heat equation $$\star_0 \frac{\partial u}{\partial t} = - d_0^T \star_1 d_0 u$$ with backward Euler for a few steps to achieve equilibrium. After that, find the gradient of the heat flow on the primitives. Finally, use Poisson reconstruciton to find a distance field that best fits the gradient.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/houdini/heat.png" title="Heat Method" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
</div>
<div class="caption">
    Using heat method to compute geodesic distance on a bunny.
</div>

### Spectral Conformal Flattening
Conformal coordinates are a kind of texture map that has minimal shearing distortion and only infinitesimally scales and rotates the texture. To obtain this, minimize the discrete conformal energy as the difference between the Dirichlet energy and the sum of area on the complex plane $$z=u+iv$$, $$C[z] = \frac{1}{2}||dz||^2-Area[z]$$. The desired texture coordinates $$(u,v)$$ are the minimizer of the conformal energy.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/houdini/conformal/aircraft.png" title="Texture Aircraft" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/houdini/conformal/beetle.png" title="Texture Beetle" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/houdini/conformal/cathead.png" title="Texture Cat Head" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/houdini/conformal/face.png" title="Texture Face" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
</div>
<div class="caption">
    Coformal texture coordinates. These map a square checkerboard texture onto different geometries.
</div>

### Smoothest Cross Field Assignment
Assign a cross to each point on the surface and try to keep crosses parallel to each other. To do this, define a reference tangent on the frame of each point. Then, compute the Levi-Chivita connection for this tangent bundle. From there, a covariant derivative operator can be built. This gives rise to a connection Laplacian. Finally, minimize the Dirichelet energy of the field by finding the smallest eigenvalue of the Laplacian acting on the rotation.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/houdini/field.png" title="Cross Field" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
</div>
<div class="caption">
    Smoothest complex line bundle field.
</div>

## Simulation
### Dzhanibekov Effect (Rigidbody Simulation)
This simulates tha Dzhanibekov effect (aka. tennis racket theorem). It applies a Lie group integrator (2nd order Buss' method) to compute the rotation at each moment by preserving angular momentum.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/img/houdini/dzhanibekov.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Dzhanibekov effect.
</div>

### Cloth Simulation from Finite Strain Theory
This simulates a piece of elastic cloth swinging with its two corners fixed. I derived the equation of motion from Finite Strain Theory instead of using a existing cloth model. As a result, the simulation is exremely unstable so I only put a screenshot here.
<div class="row">
    {% include figure.liquid loading="eager" path="assets/img/houdini/cloth.png" title="Array of Materials" class="img-fluid rounded z-depth-1" zoomable=true%}
</div>
<div class="caption">
    A piece of cloth.
</div>

### Lid-driven Cavity Flow Simulation from Lattice Boltzmann Method
This simulates fluid in a tank driven by a sliding lid, using Lattice Boltzmann Method. Instead of solving NS equations, LBM propagates particles between lattice.
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/img/houdini/lbm.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Lid-driven cavity flow simulation. The color indicates the magnitude of the velocity.
</div>
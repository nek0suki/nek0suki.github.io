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
    Using surface Laplacian to solve Poisson equation.
</div>

### Conformal Texture Coordinates
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
    Using surface Laplacian to solve Poisson equation.
</div>

### Smoothest Cross Field Assignment
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/houdini/field.png" title="Cross Field" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
</div>
<div class="caption">
    Using surface Laplacian to solve Poisson equation.
</div>

## Simulation
### Dzhanibekov Effect (Rigidbody Simulation)
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/img/houdini/dzhanibekov.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Three-Body
</div>

### Cloth Simulation from Finite Strain Theory
<!-- <div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/img/houdini/dzhanibekov.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Three-Body
</div> -->

### Lid-driven Cavity Flow Simulation from Lattice Boltzmann Method
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/img/houdini/lbm.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Three-Body
</div>
---
layout: page
title: Houdini Mini Tasks
description: with background image
img: assets/img/4.jpg
importance: 1
category: project
---

A collection of mini projects about geometry and simulation with Houdini. Codes are written in VEX and Python.

## Geometry
### Poisson Equation
Build a Laplacian operator first, and then use it to solve a Poisson equation. Positive and negative charges are set at the red and blue poles.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/houdini/poisson.png" title="Poisson Equation" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
</div>
<div class="caption">
    Using surface Laplacian to solve Poisson equation.
</div>

### Geodesic Distance using Heat Equation
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
        {% include figure.liquid loading="eager" path="assets/img/houdini/conformal/aircraft.png" title="Heat Method" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/houdini/conformal/beetle.png" title="Heat Method" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/houdini/conformal/cathead.png" title="Heat Method" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/houdini/conformal/face.png" title="Heat Method" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
</div>
<div class="caption">
    Using surface Laplacian to solve Poisson equation.
</div>

### Smoothest Cross Field Assignment
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/houdini/field.png" title="Heat Method" class="img-fluid rounded z-depth-1" zoomable=true%}
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
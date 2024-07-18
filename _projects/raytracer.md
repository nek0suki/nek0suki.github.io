---
layout: page
title: Whitted-style Ray Tracer
description: Ray tracing in one weekend
img: assets/img/1.jpg
importance: 1
category: project
---

A whitted-style ray tracer, following <a href="https://raytracing.github.io/books/RayTracingInOneWeekend.html">Ray Tracing in One Weekend</a>. It is a WebGPU based project and is built upon <a href="https://threejs.org/">Three.js</a> library. The ray tracing logic is written inside a fragment shader with GLSL, on other words, only a quad is drawn. There are also some utilities in JavaScript. Though no acceleration structure is implemented, you can walk through the scene with WASDQE due to the simplicity of the scene.


<a href="https://acsweb.ucsd.edu/~zew027/raytracer/index.html ">Click To Play!</a>

<div class="row">
    <div class="row-sm mt-1 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/raytracer/preview.png" title="Preview" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
</div>
<div class="caption">
    A preview of everything.
</div>
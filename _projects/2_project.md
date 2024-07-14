---
layout: page
title: OptiX Path Tracer
description: Path, BDPT, and MMLT Integrators
img: assets/img/3.jpg
importance: 1
category: project
---

A physically-based Monte-Carlo hardware path tracer using <a href="https://developer.nvidia.com/rtx/ray-tracing/optix">NVIDIA OptiX</a> written in C++ and CUDA. It features with three integrators, which are standard path tracing, bidirectional path tracing, and multiplexed Metropolis light transport. The implementation is highly inspired by <a href="https://pbr-book.org/">PBRT</a>. However, I did not pay many efforts on BXDFs so that it only comes with a modified Phong model and GGX model. As a result, some abilities of Metropolis light transport (e.g., caustics) cannot be showcased. A report is can be found <a href="/assets/pdf/optix.pdf">here</a>.

Some example images:
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/optix/cornellOcclusion_path.jpg" title="Cornell Occlusion Path" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/optix/cornellOcclusion_bdpt.jpg" title="Cornell Occlusion BDPT" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/optix/cornellOcclusion_mlt.jpg" title="Cornell Occlusion MMLT"  class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A scene with occlusion. Images rendered with path, bdpt, and mmlt integrators respectively. Path tracing fails easily.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/optix/cornellOcclusion_path.png" title="Cornell Occlusion Path" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/optix/cornellOcclusion_bdpt.png" title="Cornell Occlusion BDPT" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/optix/cornellOcclusion_mlt.png" title="Cornell Occlusion MMLT"  class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A even more challenging scene. Images rendered with path, bdpt, and mmlt integrators respectively. 
</div>

<div class="row">
    <div class="row-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/optix/dragon.png" title="Dragon" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="row-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/optix/ggx.png" title="GGX" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Some other scenes rendered with path tracing.
</div>
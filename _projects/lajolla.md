---
layout: page
title: La Jolla Renderer Extensions
description: Disney Principled BRDFs and Volumetric Path Tracing
img: assets/img/7.jpg
importance: 1
category: project
---

In this project, I implemented two extensions in an educational renderer, <a href="https://github.com/BachiLi/lajolla_public">La Jolla Renderer</a>.

## Disney Principled BRDFs
This follows the famous SIGGRAPH course in 2012. <a href="https://media.disneyanimation.com/uploads/production/publication_asset/48/asset/s2012_pbs_disney_brdf_notes_v3.pdf">Disney principled BRDFs</a>. It contains diffuse, metal, glass, clearcoat, and sheen components.

<div class="row">
    {% include figure.liquid loading="eager" path="assets/img/lajolla/array.png" title="Array of Materials" class="img-fluid rounded z-depth-1" zoomable=true%}
</div>
<div class="caption">
    An array of material balls with different UBER parameters.
</div>

<div class="row">
    {% include figure.liquid loading="eager" path="assets/img/lajolla/coffee.png" title="Coffee Maker" class="img-fluid rounded z-depth-1" zoomable=true%}
</div>
<div class="caption">
    A coffee maker from <a href="https://mitsuba.readthedocs.io/en/latest/src/gallery.html">Mitsuba3 scenes</a>.
</div>

## Volumetric Path Tracing
This implements the <a href="https://dl.acm.org/doi/10.1145/2661229.2661292">Ratio Tracking</a> method to render heterogeneous medium. It applys a majorant value of the volume and determines whether rays hitting a real or fake particle according to the ratio of the extinction coefficient at the point and the majorant (aka. homogenization).

<div class="row">
    {% include figure.liquid loading="eager" path="assets/img/lajolla/hetvol_colored.png" title="Heterogeneous Chromatic Volume" class="img-fluid rounded z-depth-1" zoomable=true%}
</div>
<div class="caption">
    Heterogeneous chromatic volumes.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lajolla/balls.png" title="Balls" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lajolla/teapot.png" title="Teapot" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
</div>
<div class="caption">
    Some other volumes.
</div>

In addition, I also implemented <a href="https://onlinelibrary.wiley.com/doi/abs/10.1111/j.1467-8659.2012.03148.x">Equiangular Sampling</a> for circular light sources as a bonus. It gives a higher weight to places closer to light sources during importance sampling, so as to sample paths with fewer decades caused by scatter and absorption of the volume. Moreover, this is combined with the transmittance sampling method with multiple importance sampling to further increase efficiency.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lajolla/es_trans.png" title="Only Transmittance Sampling" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lajolla/es_eq.png" title="Only Equiangular Sampling" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lajolla/es_MIS.png" title="MIS" class="img-fluid rounded z-depth-1" zoomable=true%}
    </div>
</div>
<div class="caption">
    Left: Transmittance sampling only. Middle: Equiangular sampling only. Right: MIS Combined. Note the differences between the images at the center and the boundary of the sphere.
</div>

---
layout: page
title: Automatic-Differentiation Rigidbody Dynamics
description: Course project of UCSD CSE291 Differentiable Programming
img: assets/img/12.jpg
importance: 1
category: project
related_publications: false
---

This project implements forward and reverse mode automatic differentiation mechanism in compiler for the <a href="https://github.com/BachiLi/loma_public">loma</a> programming language.  

After that, a toy python module is developed to derive the trajectories of mass points given arbitrary coordinate system and potential energy function. It automatically computes the Jacobian and Hessian tensors 

Some examples include:  

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/AdSolver/triple_pendulum.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        ```python
        def sys_coords(q : In[MatrixMN]) -> MatrixMN:
            l1 : float = 5
            l2 : float = 5
            l3 : float = 5

            ori_x : float = 0
            ori_y : float = 0

            theta1 : float = q.arr[0]
            theta2 : float = q.arr[1]
            theta3 : float = q.arr[2]

            x1 : float = -l1 * sin(theta1) + ori_x
            y1 : float = -l1 * cos(theta1) + ori_y
            x2 : float = -l2 * sin(theta2) + x1
            y2 : float = -l2 * cos(theta2) + y1
            x3 : float = -l3 * sin(theta3) + x2
            y3 : float = -l3 * cos(theta3) + y2

            x : MatrixMN
            x.m = 6
            x.n = 1
            x.arr[0] = x1
            x.arr[1] = y1
            x.arr[2] = x2
            x.arr[3] = y2
            x.arr[4] = x3
            x.arr[5] = y3
            return x

        def sys_potential(q : In[MatrixMN], m : In[MatrixMN]) -> float:
            x : MatrixMN = sys_coords(q)
            g : float = 9.8
            return (x.arr[1] * m.arr[1] + x.arr[3] * m.arr[3] + x.arr[5] * m.arr[5]) * g
        ```
    </div>
</div>
<div class="caption">
    Triple Pendulum
</div>


{% include video.liquid path="assets/video/AdSolver/three_body.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}

Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images, even citations {% cite einstein1950meaning %}.
Say you wanted to write a bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}

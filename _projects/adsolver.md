---
layout: page
title: Automatic-Differentiation Rigidbody Dynamics
description: A Toy Python Module
img: 
importance: 1
category: project
---

This project implements forward and reverse mode automatic differentiation mechanism in compiler for the <a href="https://github.com/BachiLi/loma_public">loma</a> programming language.  

After that, a toy python module is developed to derive the trajectories of mass points given arbitrary coordinate system and potential energy function. Leveraging Hamiltonian mechanics, it automatically computes the Jacobian and Hessian tensors and figures out the equation of motion.

Some examples include:  

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/AdSolver/triple_pendulum.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Triple Pendulum
</div>

Corresponding code:
```
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

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/AdSolver/three_body.mp4" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
</div>
<div class="caption">
    Three-Body
</div>

Corresponding code:
```
def sys_coords(q : In[MatrixMN]) -> MatrixMN:
    r1 : float = q.arr[0]
    theta1 : float = q.arr[1]
    r2 : float = q.arr[2]
    theta2 : float = q.arr[3]
    r3 : float = q.arr[4]
    theta3 : float = q.arr[5]

    x1 : float = cos(theta1) * r1
    y1 : float = sin(theta1) * r1
    x2 : float = cos(theta2) * r2
    y2 : float = sin(theta2) * r2
    x3 : float = cos(theta3) * r3
    y3 : float = sin(theta3) * r3

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

    x1 : float = x.arr[0]
    y1 : float = x.arr[1]
    x2 : float = x.arr[2]
    y2 : float = x.arr[3]
    x3 : float = x.arr[4]
    y3 : float = x.arr[5]

    r12 : float = sqrt((x1-x2)*(x1-x2) + (y1-y2)*(y1-y2))
    r13 : float = sqrt((x1-x3)*(x1-x3) + (y1-y3)*(y1-y3))
    r23 : float = sqrt((x2-x3)*(x2-x3) + (y2-y3)*(y2-y3))

    m1 : float = m.arr[0]
    m2 : float = m.arr[2]
    m3 : float = m.arr[4]
    
    G : float = 1
    return - G * (m1*m2/r12 + m1*m3/r13 + m2*m3/r23)
```
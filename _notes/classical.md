---
layout: notes
title: Classical Mechanics
category: notes 
---

Important Theorems and Equations for Classical Mechanics

# Survey of the Elementary Principles
Recall:

$$ F = m \frac{d\vec{v}}{dt} = m\vec{a}$$

$$ \vec{a} = \frac{d^2 \vec{r}}{dt^2 } $$

**Generalized Form:**

$$ \vec{F} = \frac{d\vec{p}}{dt} $$


## Theorem: Conservation for the linear momentum of a particle

If the total force $$ \vec{F} = 0 $$, then $$ \dot{p} = 0 $$ and the linear momentum $$ p $$ is conserved. 

### Angular Momentum and Torque

Angular momentum is defined as: 

$$  \vec{L} =  \vec{r} \times \vec{p} $$

As a result, torque is defined as: 

$$ \vec{N} = \vec{r} \times \vec{F} $$

For something analogous to $$ \vec{F} \equiv \dot{p} $$ for $$ \vec{N} $$, 

$$ \vec{N} = \vec{r} \times m \frac{d\vec{v}}{dt}  $$

via a vector identity:

$$ \vec{N} = \frac{d}{dt} ( \vec{r} \times m \vec{v} ) = \vec{v} \times m \vec{v} + r \times \frac{d \vec{v}}{dt} $$ 

We find that torque a time derivative of angular momentum:

$$ \vec{N} = \frac{d}{dt} (\vec{r} \times m \vec{v}) = \frac{d \vec{L}}{dt} \equiv \dot{L} $$


In other words, the moment of force about point $$ O $$. 

## Theorem: Angular Momentum of a particle

If the total torque, $$ \vec{N} = 0 $$, then $$ \dot{L} = 0 $$, and angular momentum $$ \vec{L} $$ is conserved.

### Work

Work done by an external force of a particle going from point 1 to 2 is defined as:

$$ W_{1,2} = \int_{1}^{2} \vec{F} \dot{} d\vec{s}$$

### Kinetic Energy
We can obtain the kinetic energy of the particle (assuming constant $$ m $$):

$$ \int{} \vec{F} \dot{} d\vec{s} = m \int{} \frac{d\vec{v}}{dt} \dot{} \vec{v} dt = \frac{m}{2} \int{} \frac{d}{dt} (\vec{v}^2) dt $$

Note that $$ \frac{d}{dt} \vec{v}^2 = 2 \vec{v} \frac{d\vec{v}}{dt} $$

$$ W_{1,2} = \frac{m}{2} (v^{2}_{2} - v^{2}_{1}) $$

Let $$ T = \frac{mv^2}{2} $$ then we have:

$$ W_{1,2} = T_{2} - T_{1} $$

## Theorem: Conservative Theorem for a particle

If the forces acting on a particle are conservative, then the total energy of the particle, $$ T + V $$ is conserved.

### Conservative Systems

A system is conservative if $$ W_{1,2} $$ is path independent. Defined as a closed contour integral:

$$ \oint \vec{F} \dot{} d\vec{s} = 0 $$

Gravitional forces = conservative 

Frictional forces = non-conservative

### Potential Energy

Potential Energy is defined as:

$$ \vec{F} = - \nabla{V}(\vec{r}) $$

We can say that:

$$ W_{1,2} = V_{1} - V_{2} $$ 

Combining $$ W_{1,2} $$ in terms of kinetic energy and $$ W_{1,2} $$ in terms of potential energy, we get:

$$ V_{1} + T_{1} = V_{2} + T_{2} $$

# System with Multiple Particles

Newton's 2nd Law for the i-th particle:

$$\sum_{j} \vec{F}_{ji} + \vec{F}^{(e)}_{i} = \dot{p}_i  $$ 

We define a vector $$ \vec{R} $$ that points from some origin as an average of the radii vectors of particles, $$O$$ to the center of mass/gravity of a particle system:

$$ \vec{R} = \frac{\sum m_{i}\vec{r_i}}{ \sum m_i} = \frac{\sum m_{i}\vec{r_i}}{M}$$

Rewriting the 2nd law for a system of particles in terms of $$ \vec{r} $$:

$$ M \frac{d^2}{dt^2} \vec{R} = \sum_{i} \vec{F}^{(e)}_{i} \equiv \vec{F}^{(e)} $$

We find that the total linear momentum of a system is:

$$ \vec{P} = \sum m_{i} \frac{d \vec{r}_{i}}{dt} = M \frac{d \vec{R}}{dt} $$

## Theorem: Conservation of Linear Momentum of a System of Particles:

If $$ \vec{F}^{(e)} = 0 $$, then $$ \vec{p} $$ is conserved. 

**Strong Law of Action and Reaction**: If the internal forces between two particles, in addition to being equal and opposite, _AND also_ lie along the line joining the particles.

**Weak Law of Action and Reaction**: If the internal forces between two particls are equal and opposite.

### Angular Momentum of a System of Particles
$$ \sum_{i} (\vec{r_{i}} \times \dot{\vec{p_{i}}}) = \sum_{i} \frac{d}{dt} (\vec{r_{i}} \times \vec{p}_{i} = \vec{\dot{L}} = \sum_{i} \vec{r}_{i} \times \vec{F}^{(e)}_{i} + \sum_{i,j}^{i\neq j} \times \vec{F}_{i,j} $$

For the last term on the right:

$$ r_{i} \times \vec{F}_{j,i} + r_{j}  \times \vec{F}_{i,j} = (\vec{r}_{i} - \vec{r}_{j}) \times \vec{F}_{j,i} $$


# References

+ Classical Mechanics by Goldstein, Poole & Safko



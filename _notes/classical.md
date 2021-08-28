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

## Particles








# References

+ Classical Mechanics by Goldstein, Poole & Safko



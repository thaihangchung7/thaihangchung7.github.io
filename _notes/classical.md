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

$$ \vec{p} = m \vec{v} $$

**Generalized Form:**

$$ \vec{F} = \frac{d\vec{p}}{dt} \equiv \dot{p} $$

for an _inertial_ or _Galilean_ system.
## Theorem: Conservation for the linear momentum of a particle

If the total force $$ \vec{F} = 0 $$, then $$ \dot{p} = 0 $$ and the linear momentum $$ p $$ is conserved. 
=======
**(Theorem) Conservation for the linear momentum of a particle**: If the total force $$ \vec{F} = 0 $$, then $$ \dot{p} = 0 $$ and the linear momentum $$ p $$ is conserved. 

### Angular Momentum and Torque

Angular momentum is defined as: 

$$  \vec{L} =  \vec{r} \times \vec{p} $$

As a result, torque (or moment of force) is defined as: 

$$ \vec{N} = \vec{r} \times \vec{F} $$

For something analogous to $$ \vec{F} \equiv \dot{p} $$ for $$ \vec{N} $$, 

$$ \vec{N} = \vec{r} \times m \frac{d\vec{v}}{dt}  $$

via a vector identity:

$$ \vec{N} = \frac{d}{dt} ( \vec{r} \times m \vec{v} ) = \vec{v} \times m \vec{v} + r \times \frac{d \vec{v}}{dt} $$ 

We find that torque a time derivative of angular momentum:

$$ \vec{N} = \frac{d}{dt} (\vec{r} \times m \vec{v}) = \frac{d \vec{L}}{dt} \equiv \dot{L} $$


In other words, the moment of force about point $$ O $$. 

**(Theorem) Angular Momentum of a particle**: If the total torque, $$ \vec{N} = 0 $$, then $$ \dot{L} = 0 $$, and angular momentum $$ \vec{L} $$ is conserved.

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

**(Theorem) Conservative Theorem for a particle**: If the forces acting on a particle are conservative, then the total energy of the particle, $$ T + V $$ is conserved.

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

$$ \vec{R} = \frac{\sum m_{i}\vec{r_i}}{ \sum m_{i}} = \frac{\sum m_{i}\vec{r_{i}}}{M}$$

Rewriting the 2nd law for a system of particles in terms of $$ \vec{r} $$:

$$ M \frac{d^2}{dt^2} \vec{R} = \sum_{i} \vec{F}^{(e)}_{i} \equiv \vec{F}^{(e)} $$

We find that the total linear momentum of a system is:

$$ \vec{P} = \sum m_{i} \frac{d \vec{r}_{i}}{dt} = M \frac{d \vec{R}}{dt} $$

**(Theorem) Conservation of Linear Momentum of a System of Particles**: If $$ \vec{F}^{(e)} = 0 $$, then $$ \vec{p} $$ is conserved. 

**Strong Law of Action and Reaction**: If the internal forces between two particles, in addition to being equal and opposite, _AND also_ lie along the line joining the particles.

**Weak Law of Action and Reaction**: If the internal forces between two particls are equal and opposite.

### Angular Momentum of a System of Particles
$$ \sum_{i} (\vec{r_{i}} \times \dot{\vec{p_{i}}}) = \sum_{i} \frac{d}{dt} (\vec{r_{i}} \times \vec{p}_{i} ) = \vec{\dot{L}} = \sum_{i} \vec{r}_{i} \times \vec{F}^{(e)}_{i} + \sum_{i,j}^{i\neq j} \times \vec{F}_{i,j} $$

For the last term on the right:

$$ r_{i} \times \vec{F}_{j,i} + r_{j}  \times \vec{F}_{i,j} = (\vec{r}_{i} - \vec{r}_{j}) \times \vec{F}_{j,i} $$


# Path to Lagrange

A infinitesimal virtual displacement is denoted by $$ \delta \vec{r_{i}} $$. This is also referred to as a "variation" (arises from calculus of variations). As opposed to a physical displacement, a _virtual_ displacement is anaglous to a blind person infinitesimally probing their surroundings where as a seeing person physically takes an infinitesimal step.

To put it another way $$ d\vec{r} $$ typically involves times, and $$ \delta \vec{r} $$ is time independent. If it isn't obvious yet, I am **very** uncomfortable with virutal displacement.


For a system in equilibrium ($$ F_{i} = 0 $$):

$$ \sum_{i} \vec{F_{i}} \dot{} \delta \vec{r_{i}} = 0 $$

### A word on generalized coordinates and constraints

We _transform_ our system of old coordinates and put in terms of generalized coordinates to parametrize our system:

$$ \vec{r} = \vec{r}_1 ( q_{1}, q_{2}, q_{m}, t) $$

where $$ m = 3N - k $$ degrees of freedom ($$ k $$ is the number of constraints ).  

Differentiating...

$$ \delta \vec{r}_{i} = \sum_{j=1}^{m} \frac{\partial \vec{r}_{i} }{\partial q_{j}} dq_{j} + \frac{\partial \vec{r}_{i}}{\partial t} dt $$

The principle of virtual work for a system is defined as:

$$ \delta W = \sum_{i=1}^{N} \vec{F_{i}^{a}} \delta \vec{r_{i}} = 0 $$  

The coefficients of $$ \delta \vec{r}_{i} $$ can no longer be set to zero i.e. $$ \vec{F}^{a}_{i} \neq 0 $$ since $$ \delta \vec{r}_{i} $$ are bound by constraints. However, this is not ideal. 

# D'Alembert's Principle

Note that the principle of virtual work $$ \delta W $$ does not contain $$ f_{i} $$, however, it only deals with statics even though it uses virtual displacements $$ q_{i} $$. To extend this to the general motion of the system, we can start from an equation of motion $$ F = \dot{P} $$ and use some definitions, namely $$ \vec{F_{i}} + \vec{F_{i}^{a}} + f_{i} $$.

$$ \sum_{i} (\vec{F_{i}^{a}} - \dot{\vec{p_{i}}} ) \dot{} \delta \vec{r_{i}} + \sum \vec{f_{i}} \dot{} \delta \vec{r_{i}} = 0 $$

"Restricting ourselves to systems for which the virtual work of the forces of constraint vanishes":

$$ \sum_{i} (\vec{F_{i}^{a}} - \dot{\vec{p_{i}}} ) \dot{} \delta \vec{r_{i}} = 0 $$

We've arrived at **D'Alembert's principle**.

However, we must generalize this equation further. The goal is to come up with an equation uses generalized coordinates $$( q $$ and $$ \dot{q})$$ for virtual displacements. This will allow us to set the coefficient of $$ \delta q_{i} $$ equal to zero since vitual displacements of generalized coordinates are dependent of each other.

After using the following definitions:

$$ \delta \vec{r_{i}} = \sum_{j} \frac{\partial \vec{r_{i}} }{\partial q_{j}} \delta q_{j} $$

$$ Q_{j} = \sum_{i} \vec{F_{i}} \dot{} \frac{\partial \vec{r_{i}}}{\partial q_{j}} $$ 

and after some derivation...

$$ \frac{d}{dt} (\frac{\partial T}{\partial \dot{q_{j}}}) - \frac{\partial T}{\partial q_{i}} = Q_{j} $$

## Generalizing to Lagrange

For a conservative system:

$$ F_{i} = - \nabla_{i} V $$

Recall that this rises from the fact that in order for $$ W = 0 $$:

$$ W = \int \int \nabla \times \vec{F_{i}^{a}} = 0 $$

this result is true if and only if $$ F_{i} = - \nabla_{i} V $$ so that:

$$ W = \int \int \nabla \times \nabla V = 0 $$ 

Rewriting generalized force:

$$ Q_{j} = \sum_{i} \vec{F_{i}} \dot{} \frac{\partial \vec{r_{i}}}{\partial q_{j}} = - \sum_{i} \nabla_{i} V \dot{} \frac{\partial \vec{r_{i}}}{\partial q_{j} } $$

$$ = - \sum_{i} \frac{\partial V}{\partial \vec{r_{i}}} \frac{\partial \vec{r_{i}}}{\partial q_{j}}$$ 

$$ Q_{j} = - \frac{\partial V}{\partial q_{i}} $$ 

Substituting $$ Q_{j} $$ into D'Alembert's generalized principle, we have

$$ \frac{d}{dt} ( \frac{\partial L}{\partial \dot{q_{j}}} ) - \frac{\partial L}{\partial q_{j}} = 0 $$

We've arrived at **Lagrange's Equation** where $$ L = T - V $$ defines the **Lagrangian**. 

"There is no unique choice of Lagrangian such that the Euler-Lagrange equations lead to the equation of motion in the given generalized coordinates."

If $$ L (q , \dot{q}, t )$$ is an approximate Lagrangian. $$ F(q,t) $$ is any differentiable function, then:

$$ L'(q,\dot{q}, t) = L (q, \dot{q}, t) + \frac{dF}{dt} $$

Keep in mind that it is often possible to find alternative Lagrangians. 

# Velocity-Dependent Potentials and the Dissipation Function

Let us "redefine" the Lagrangian:

$$ L = T - U $$ 

where $$ U $$ is called a "generalized potential" or a __"velocity-dependent potential"__. 

Consider an electric charge, $$ q $$, with mass $$ m $$, moving at velocity, $$ \vec{v} $$. The charge is placed in an $$ \vec{E} $$ and $$ \vec{B} $$ field, which both depend on time and position. The charge experiences the Lorentz force:

$$ \vec{F_{Lorentz}} = q [\vec{E} + (\vec{v} \times \vec{B})] $$  

The goal here is to turn $$ F_{Lorentz} $$ into some potential $$ U $$ for the Lagrangian.

Using some of Maxwell's EM equations, namely:

$$ \nabla \dot{} \vec{B} = 0$$ 

$$ \nabla \times \vec{E} = \frac{\partial \vec{B}}{\partial t}$$

We define the scalar and vector potentials:

$$ \vec{E} = - \nabla \phi - \frac{\partial \vec{A}}{\partial t} $$ ; $$\phi (t,x,y,z) $$

$$ \vec{B} = \nabla \times \vec{A} $$ ; $$ \vec{A} (t,x,y,z) $$

Insert $$\vec{E}$$ and $$\vec{B}$$ into $$\vec{F}_{Lorentz} $$:

$$ \vec{F}_{Lorentz} = q [ -\nabla \phi - \frac{\partial \vec{A}}{\partial t} + \vec{v} \times \nabla \times \vec{A} ] $$

To deal with the vector triple product, here are some helpful definitions and hints:

Restricting our triple product to the $$ x $$ component since the $$ y $$ and $$ z $$ computations will be the same.

Look for $$ - v_{x} \frac{\partial A_{x}}{\partial x} - v_{y} \frac{\partial A_{x}}{\partial y} - v_{z} \frac{\partial A_{x}}{\partial z} $$ 

Look for the term $$ \frac{\partial A_{x}}{\partial t} - \frac{\partial A_{x}}{\partial t}$$ using:

$$ \frac{\partial A_{x}}{\partial t} = v_{x} \frac{\partial A_{x}}{\partial x} + v_{y} \frac{\partial A_{y}}{\partial y} + v_{z} \frac{\partial A_{z}}{\partial z} + \frac{\partial A_{x}}{\partial t} $$ 

Analytically "guessing" a solution:

$$ \frac{\partial}{\partial x} (\vec{v} \dot{} A) = \frac{\partial}{\partial x} (v_{x} A_{x} + v_{y} A_{y} + v_{z} A_{z}) = A_{x} $$

The vector triple product is:

$$ ( v \times \nabla \times A) = \frac{\partial}{\partial x} ( v \times A ) - \frac{d}{dt} (\frac{\partial}{\partial x} (v \times A)) + \frac{\partial A_{x}}{\partial t}$$

Plugging in our definitions, the $$ x $$ component of the Lorentz force will be:

$$ \vec{F_{Lor,x}} = q [ - \frac{\partial \phi}{\partial x} - \frac{A_{x}}{\partial t} + \frac{\partial}{\partial x} (\vec{v} \dot{} \vec{A} ) - \frac{d}{dt} ( \frac{\partial}{\partial t} (\vec{v} \dot{} \vec{A} ) + \frac{\partial A_{x}}{\partial t}) ] $$

$$ = q [- \frac{\partial}{\partial x} \big(\phi - (\vec{v} \dot{} \vec{A} )\big) - \frac{d}{dt}(\frac{\partial}{\partial x} ( \phi - (\vec{v} \dot{} \vec{A} ) ) ] $$


$$ F_{Lor,x} = \frac{d}{dt} (\frac{\partial U}{\partial x} ) - \frac{\partial U}{\partial x} $$ 

Finally, we define $$ U $$, the **generalized EM potential**  :

$$ U = q \phi - q \vec{A} \dot{} \vec{v} $$

such that the Lagrangian $$ L = T - U $$ is:

$$ L = \frac{1}{2} m v^{2} - q \phi + q \vec{A} \dot{} \vec{v} $$


# References

+ Classical Mechanics by Goldstein, Poole & Safko

+ Mechanics by Landau & Lifshitz 

+ [David Tong's Notes on Classical Mechanics](http://www.damtp.cam.ac.uk/user/tong/dynamics.html)

+ [Caltech Notes](https://sites.astro.caltech.edu/~golwala/ph106ab/ph106ab_notes.pdf)

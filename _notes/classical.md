---
layout: notes
title: Classical Mechanics
category: notes 
---

Important Theorems and Equations for Classical Mechanics

Table of Contents
=================

* [Survey of the Elementary Principles](#survey-of-the-elementary-principles)
* [Angular Momentum and Torque](#angular-momentum-and-torque)
* [Work](#work)
* [Kinetic Energy](#kinetic-energy)
* [Conservative Systems](#conservative-systems)
* [Potential Energy](#potential-energy)
* [System with Multiple Particles](#system-with-multiple-particles)
* [Angular Momentum of a System of Particles](#angular-momentum-of-a-system-of-particles)
* [Generalizing Coordinates](#generalizing-coordinates)
  * [A word on constraints and generalized coordinates](#a-word-on-constraints-and-generalized-coordinates)
* [D'Alembert's Principle](#dalemberts-principle)
* [Generalizing to Lagrange](#generalizing-to-lagrange)
* [Velocity-Dependent Potentials and the Dissipation Function](#velocity-dependent-potentials-and-the-dissipation-function)
* [References](#references)


# Survey of the Elementary Principles
Recall:

$$ F = m \frac{d\vec{v}}{dt} = m\vec{a}$$

$$ \vec{a} = \frac{d^2 \vec{r}}{dt^2 } $$

$$ \vec{p} = m \vec{v} $$

**Generalized Form:**

$$ \vec{F} = \frac{d\vec{p}}{dt} \equiv \dot{p} $$

for an _inertial_ or _Galilean_ system.

**(Theorem) Conservation for the linear momentum of a particle**

If the total force $$ \vec{F} = 0 $$, then $$ \dot{p} = 0 $$ and the linear momentum $$ p $$ is conserved. 

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

The work done on a particle when it travels some distance $$ds$$ is given by:

$$ \vec{F} \dot{} ds = - \frac{\partial V}{\partial s} \dot{} ds $$

A system is conservative if $$ W_{1,2} $$ is path independent. Defined as a closed contour integral:

$$ \oint \vec{F} \dot{} d\vec{s} = 0 $$

Mathematically, a force or vector field is conservative if it meets any of the following conditions:

1) $$ \nabla \times \vec{F} = \vec{0} $$

2) $$ W \equiv \oint_{C} \vec{F} \dot{} d\vec{r} = 0 $$

3) $$ \vec{F} = - \nabla \Phi $$; 

where $$ \Phi $$ is some potential. 

Conservative forces: Gravity, Particle in an $$ \vec{E} $$ field 

Non-Conservative forces: Friction, Particle in a $$ \vec{B} $$ field,

### Conservation of Energy and Conservative Forces 

Potential Energy is defined as:

$$ \vec{F} = - \nabla{V}(\vec{r}) $$

We can say that:

$$ W_{1,2} = V_{1} - V_{2} $$ 

Combining $$ W_{1,2} $$ in terms of kinetic energy and $$ W_{1,2} $$ in terms of potential energy, we get:

$$ V_{1} + T_{1} = V_{2} + T_{2} $$

In other words, the system's total energy is conserved if the force can be written as $$ \vec{F} = - \nabla V (\vec{r}) $$ or $$ \vec{F} = - \frac{\partial V}{ \partial s} $$

# System with Multiple Particles

Newton's 2nd Law for the i-th particle:

$$\sum_{j} \vec{F}_{ji} + \vec{F}^{(e)}_{i} = \dot{p}_i  $$ 

where $$ \vec{F_{ji}} $$ refer to the interforces between the particles and $$ \vec{F}_{i}^{(e)} $$ refers to the external force acting on the system.   

We define a vector $$ \vec{R} $$ that points from some origin as an average of the radii vectors of particles, $$O$$ to the center of mass/gravity of a particle system:

$$ \vec{R} = \frac{\sum m_{i}\vec{r_{i}}}{ \sum m_{i}} = \frac{\sum m_{i}\vec{r_{i}}}{M}$$

Rewriting the 2nd law for a system of particles in terms of $$ \vec{r} $$:

$$ M \frac{d^2}{dt^2} \vec{R} = \sum_{i} \vec{F}^{(e)}_{i} \equiv \vec{F}^{(e)} $$

We find that the total linear momentum of a system is:

$$ \vec{P} = \sum m_{i} \frac{d \vec{r}_{i}}{dt} = M \frac{d \vec{R}}{dt} $$

**(Theorem) Conservation of Linear Momentum of a System of Particles**: If $$ \vec{F}^{(e)} = 0 $$, then $$ \vec{p} $$ is conserved. 

**Strong Law of Action and Reaction**: If the internal forces between two particles, in addition to being equal and opposite, _AND also_ lie along the line joining the particles.

**Weak Law of Action and Reaction**: If the internal forces between two particles are equal and opposite.

### Angular Momentum of a System of Particles
$$ \sum_{i} (\vec{r_{i}} \times \dot{\vec{p_{i}}}) = \sum_{i} \frac{d}{dt} (\vec{r_{i}} \times \vec{p}_{i} ) = \vec{\dot{L}} = \sum_{i} \vec{r}_{i} \times \vec{F}^{(e)}_{i} + \sum_{i,j}^{i\neq j} r_{i} \times \vec{F}_{i,j} $$

For the last term on the right:

$$ r_{i} \times \vec{F}_{j,i} + r_{j}  \times \vec{F}_{i,j} = (\vec{r}_{i} - \vec{r}_{j}) \times \vec{F}_{j,i} $$

Due to the equality of actiona and reaction, $$ r_{i} - r_{j} $$ is identical to $$ r_{ij} $$. We can rewrite the equation above:

$$ r_{ij} \times \vec{F_{ji}} $$

Applying the strong law of action and reaction, the cross products of vectors that lie on the line joining the particles vanish, leaving only the external forces. Hence:

$$ \frac{d \vec{L}}{dt} = \vec{N}^{e} $$

in other words, the time derivative of the total angular momentum is equal to the moment of the external force about a given point.

# Generalizing Coordinates

A infinitesimal virtual displacement is denoted by $$ \delta \vec{r_{i}} $$. This is also referred to as a "variation" (arises from calculus of variations). As opposed to a physical displacement, a _virtual_ displacement is anaglous to a blind person infinitesimally probing their surroundings where as a seeing person physically takes an infinitesimal step.

To put it another way $$ d\vec{r} $$ typically involves times, and $$ \delta \vec{r} $$ is time independent.

For a system in equilibrium ($$ F_{i} = 0 $$):

$$ \sum_{i} \vec{F_{i}} \dot{} \delta \vec{r_{i}} = 0 $$

### A word on constraints and generalized coordinates

Constraints are classified in various ways. Constraints that are **holonomic** take the form:

$$ f(\vec{r_{1}}, \vec{r_{2}}, ... , t) = 0 $$ 

i.e. a holonomic constraint depends on coordinates $$ x_{j} $$ and maybe $$ t $$. It does not depend on any higher-order derivatives with respect to $$ t $$ such as velocity. 

The simplest examples of holonomic constraint is a rigid body or a particle constrained to move along any curve.  

On the other hand, **non-holonomic** constraints are expressed as:

$$ f(\vec{r_{1}}, \vec{r_{2}}, ... , t) < 0 $$ 

The walls of a gas container is an example of non-holonomic constraint.

Constraints can be further classified by their dependence on time.

If constraints contain time as an explicit variable, then these contraints are known as **rheonomous**. 

Otherwise, if the contraint is time-independent, then they are known as **scleronomous**. The equation of constraints can be described by generalized coordinates. 

We _transform_ our system of old coordinates and put in terms of generalized coordinates to parametrize our system:

$$ \vec{r} = \vec{r}_1 ( q_{1}, q_{2}, q_{m}, t) $$

where we have $$m$$ independent coordinates; $$ m = 3N - k $$ with $$ 3N $$ degrees of freedom $$ k $$ number of constraints.  

Differentiating...

$$ \delta \vec{r}_{i} = \sum_{j=1}^{m} \frac{\partial \vec{r}_{i} }{\partial q_{j}} dq_{j} + \frac{\partial \vec{r}_{i}}{\partial t} dt $$

The **principle of virtual work** for a system in static equilibrium is defined as:

$$ \delta W = \sum_{i=1}^{N} \vec{F_{i}^{a}} \delta \vec{r_{i}} = 0 $$  

The coefficients of $$ \delta \vec{r}_{i} $$ can no longer be set to zero i.e. $$ \vec{F}^{a}_{i} \neq 0 $$ since $$ \delta \vec{r}_{i} $$ are bound by constraints. However, this is not ideal. 

# D'Alembert's Principle

Note that the principle of virtual work $$ \delta W $$ does not contain $$ f_{i} $$, however, it only deals with statics even though it uses virtual displacements $$ q_{i} $$. To extend this to the general motion of the system, we can start from an equation of motion $$ F = \dot{P} $$ and use some definitions, namely $$ \vec{F_{i}} = \vec{F_{i}^{a}} + f_{i} $$.

$$ \sum_{i} (\vec{F_{i}^{a}} - \dot{\vec{p_{i}}} ) \dot{} \delta \vec{r_{i}} + \sum \vec{f_{i}} \dot{} \delta \vec{r_{i}} = 0 $$

"Restricting ourselves to systems for which the virtual work of the forces of constraint vanishes". For systems in dynamic equilibrium:

$$ \delta W = \sum_{i} (\vec{F_{i}^{a}} - \dot{\vec{p_{i}}} ) \dot{} \delta \vec{r_{i}} = 0 $$

We've arrived at **D'Alembert's principle**.

However, we must generalize this equation further. The goal is to come up with an equation uses generalized coordinates $$( q $$ and $$ \dot{q})$$ for virtual displacements. This will allow us to set the coefficient of $$ \delta q_{i} $$ equal to zero since vitual displacements of generalized coordinates are dependent of each other.

After using the following definitions:

Virtual Displacement:

$$ \delta \vec{r_{i}} = \sum_{j} \frac{\partial \vec{r_{i}} }{\partial q_{j}} \delta q_{j} $$

and **Generalized Force**:

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


# Applications of the Lagrangian Formulation

When generalizing Cartesian coordinates, we make use of the transformation equations:

$$ r_{i} = r_{1}(q_{1},...,q_{3N-k},t) $$

$$ r_{i} = r_{N}(q_{1},...,q_{3N-k},t) $$

$$ r_{i} = r_{i}(q_{1},...,q_{n},t) $$

T in general is defined as:

$$ T = \sum_{i} \frac{1}{2} m_{i} v_{i}^{2} = \sum_{i} \frac{1}{2} m_{i} \bigg( \sum_{j} \frac{\partial r_{i}}{\partial q_{j}} \dot{q_{j}} + \frac{\partial r_{i}}{\partial t} \bigg)^{2}  $$

Carrying out the expansion on the squared term we end up with:

$$ T_{0} = \sum_{i} \frac{1}{2} m_{i} \bigg(\frac{\partial r_{i}}{\partial q_{j}} \dot{q}_{j} \bigg)^{2} + \sum_{i} m_{i} \bigg( \frac{\partial r_{i}}{\partial q_{j}} \dot{} \frac{\partial r_{i}}{\partial t} \bigg) \dot{q}_{j} + \frac{1}{2} \sum_{i} m_{i} \bigg( \frac{\partial r_{i}}{\partial t} \bigg)^{2}  $$


We define a couple terms...

$$ M_{0} = \frac{1}{2} \sum_{i} \bigg( \frac{\partial r_{i}}{\partial t} \bigg)^{2} $$

$$ M_{j} = \sum_{i} m_{i} \bigg( \frac{\partial r_{i}}{\partial q_{j}} \dot{} \frac{\partial r_{i}}{\partial q_{t}} \bigg) $$

$$ M_{jk} = \sum_{i} \frac{1}{2} m_{i} \bigg(\frac{\partial r_{i}}{\partial q_{j}} \frac{\partial r_{i}}{\partial q_{k}} \bigg) $$

So, generalized kinetic energy can be simplified to:

$$ T_{0} = M_{0} + M_{j} \dot{q}_{j} + M_{jk} \dot{q}_{j} \dot{q}_{k} $$

# Variational Principles and Lagrange's Equations

## Hamilton's Principle

D'Alembert's Principle takes the form of a "_differential principle_" since it take the instantaneous state of the system and a small virtual displacement about the instantaneous state into consideration.

In the context of **monogenic systems**, we introduce the _integral principle_. If the _generalized_ potential depends on generalized coordinates, velocity, and time, or $$ V(q, \dot{q}, t) $$, then the system is **monogenic**. Conservative systems are a  subset of monogenic systems in that the potential is only dependent on generalized coodinates. 

Hamilton's principle is stated as:

"The motion of the system from time $$ t_{1} $$ to time $$ t_{2} $$ is such that the line inegral (called the action or the action integral, sometimes denoted $$ S $$) is

$$ I = \int_{t_{1}}^{t_{2}} L (q(t), \dot{q}(t), t) dt $$

where $$ L $$ is the Lagrangian and has a stationary value for the actual path of motion." The system's true evolution is described by $$ N $$ generalized coordinates $$ \vec{q} = (q_{1}, ... , q_{N})$$ between two specific states $$ q(t_{1}) $$ and $$ q(t_{2}) $$. $$ t_{1} $$ and $$ t_{2} $$ are stationary points where the variation is $$ 0 $$ of the action functional.

A good way to think the integral is the "cost" or "effort" to perform the action.

For systems with constraints that are holonomic, Hamilton's principle below is nessessary and sufficient for Lagrange's equation.

$$ \delta I = \delta \int_{t_{1}}^{t_{2}} L (q(t), \dot{q}(t), t) dt = 0  $$

This integral represents the stability of a complex system. The variation of the line integral is $$ 0 $$. In other words, small deviation won't change the final result.

## Calculus of Variation Techniques

Consider a function $$ f(y, \dot{y},x) $$ defined on a path $$ y = y(x) $$ between two values $$ x_{1} $$ and $$ x_{2} $$, where 

$$ \dot{y} = \frac{dy}{dx} $$

The goal here is to find a particular path $$ y(x) $$ such that the line integral

$$ J = \int_{x_{1}}^{x_{2}} f(y, \dot{y},x) dx  $$

has a stationary value relative to paths differing infinitesimally from the correct function $$ y(x) $$. Namely, find $$ y(x) $$ such that 

$$ \delta J[ y ] = 0 $$ 

A quick aside on notion, $$J$$ is a "_functional_" and $$ f(x) $$ is a "_function_". So, $$ J[y] $$ is a "function of a function".

Since $$ J $$ must have a stationary value for the correct path relative to <u>any</u> neighboring path, the variation must be zero relative to some particular set of neighboring paths labeled by an infinitesimal parameter $$ \alpha $$.

The set of paths are $$ y(x,\alpha)$$ 

$$ y(x,\alpha) = y(x,0) + \alpha \eta (x) $$ 

and we take the optimal path defined as:

$$ J [y(x,0)] \leq J[y(x,0) + \alpha \eta(x)] $$

Here, $$ y(x,0) $$ represent the correct path and $$\alpha$$ can be thought of as a scaling factor. $$ \eta (x) $$, also known as the auxillary path, is any function selected that vanishes at $$ x = x_{1} $$ and $$ x = x_{2} $$. 

Note that $$ J $$ is also a function of $$ \alpha $$, and we want to optimize $$ \alpha $$ and thus we make use of a transformation from $$ J[y] \rightarrow J(\alpha) $$. 

$$ J(\alpha) = \int_{x_{1}}^{x_{2}} f ( y (x,\alpha), \dot{y} (x, \alpha), x) dx $$ 

This begins to look like an extremum problem if we apply variations (our buddy $$ \delta $$) to $$ J(\alpha) $$ 

$$ \delta J(\alpha) = 0$$

$$ \delta J(\alpha) = \delta \int_{x_{1}}^{x^{2}} f (y(x,\alpha), \dot{y}(x,\alpha), x) dx = 0 $$  

$$ J(\alpha) - J(\alpha = 0) = 0 $$ 

The condition for obtaining a stationary point is:

$$ \bigg( \frac{d J}{ d \alpha } \bigg)_{\alpha = 0} = 0 $$

where the derivative must be taken at the equilibrium.

We decompose the total derivative of our functional $$ f $$ as we take the derivative with respect to $$ \alpha $$:

$$ \bigg( \frac{d J}{d \alpha} \bigg)_{\alpha = 0} = \frac{d}{dt} \int_{x_{1}}^{x_{2}} f ( y, \dot{y}, x) dx  $$
 
$$  = \int_{x_{1}}^{x_{2}} \bigg( \frac{\partial f}{\partial y} \frac{\partial y}{\partial \alpha} + \frac{\partial f}{\partial \dot{y}} \frac{\partial \dot{y}}{\partial \alpha} + \frac{\partial f}{\partial x} \frac{\partial x}{\partial \alpha} \bigg) dx$$

Note that the last term in the integral, $$\frac{\partial x}{\partial \alpha} =0$$, since $$x$$ does not depend on $$\alpha$$.  

We trade the second term in the integral with a term defined below:

$$ \frac{d}{dx} \big( \frac{\partial f}{\partial \dot{y}} \frac{\partial y}{\partial \alpha} \big) = \frac{d}{dx} \bigg( \frac{\partial f}{\partial y} \bigg) \frac{y}{\partial \alpha} + \frac{\partial f}{\partial y} \frac{d}{dx} \bigg( \frac{\partial y}{\partial \alpha} \bigg) $$ 


$$ \frac{\partial f}{\partial y} \frac{d}{dx} \bigg( \frac{\partial y}{\partial \alpha} \bigg) =  \frac{d}{dx} \big( \frac{\partial f}{\partial \dot{y}} \frac{\partial y}{\partial \alpha} \big) - \frac{d}{dx} \bigg( \frac{\partial f}{\partial y} \bigg) \frac{y}{\partial \alpha} $$ 




Making use of the **Leibniz integral rule**: $$ \frac{d}{dx} \bigg( \int_{a}^{b} f(x,t) dt \bigg) = \int_{a}^{b} \frac{\partial}{\partial x} f(x,t) dt$$

$$ \frac{dJ}{d\alpha} = \int_{x_{1}}^{x_{2}} \frac{\partial f}{\partial y} \frac{\partial y}{\partial \alpha} + \frac{\partial f}{\partial \dot{y}} \frac{\partial \dot{y}}{\partial \alpha} dx $$  

$$ = \int_{x_{1}}^{x_{2}} \frac{\partial f}{\partial y} \frac{\partial y}{\partial \alpha} - \frac{d}{dx} \bigg( \frac{\partial f}{\partial \dot{y}} \bigg) \frac{\partial y}{\partial \alpha} dx $$ 

Pulling out the common factor, $$ \frac{\partial y}{\partial \alpha} $$.

$$ \int_{x_{1}}^{x_{2}} \bigg[ \frac{\partial f}{\partial y} - \frac{d}{dx} \bigg( \frac{\partial f}{\partial \dot{y}} \bigg) \bigg] \bigg(\frac{\partial y}{\partial \alpha}\bigg)_{\alpha = 0}dx $$

## The "Fundamental Lemma" of Calculus of Variations

If

$$ \int_{x_{1}}^{x_{2}} M(x) \eta(x) dx = 0 $$

for any arbitrary function $$ \eta(x) $$ continuous through $$ \frac{\partial^{2} y (x)}{\partial x^{2}}$$, then $$M(x) = 0$$, $$M(x)$$ must identically vanish in the interval $$(x_{1},x_{2} )$$. 

With $$ M(x) = \frac{\partial f}{\partial y} - \frac{d}{dx} \big(\frac{\partial f}{\partial \dot{y}} \big) $$ and $$ \eta(x) = \big(\frac{\partial y}{\partial \alpha} \big)_{\alpha = 0} $$,

Then by the Fundamental Lemma, we have found $$M(x) $$ to be the **Euler-Lagrange equation**:

$$ \frac{\partial f}{\partial y} - \frac{d}{dx} \big(\frac{\partial f}{\partial \dot{y}} \big) = 0 $$ 

Following from the discussion about our varied functional $$J$$, $$ J $$ can have a stationary value only if $$M(x) = 0 $$.

The assertion that $$J$$ is stationary for the correct path can be written as:


$$ \delta J =  \int_{x_{1}}^{x_{2}} \bigg[ \frac{\partial f}{\partial y} - \frac{d}{dx} \bigg( \frac{\partial f}{\partial \dot{y}} \bigg) \bigg] \delta y dx= 0 $$

## Deriving Lagrange's Equation from Hamilton's Principle

For $$ J[f] $$, we try to find an $$ x_{0} $$ which would give us an extremum:

$$ J[f] = \int_{x_{1}}^{x_{2}} L (x, f(x), f'(x)) dx $$

Define an arbitrary varied function and its derivative:

$$ f \rightarrow f + \delta f = f + \alpha \eta $$

$$ f' \rightarrow f' + \delta f' $$ 

$$ J[f + \delta f] = \int_{x_{1}}^{x_{2}} L (x, f + \delta f, f' + \delta f') dx$$ 

We can make use of the Taylor expansion (up to first order):

$$ J[f + \delta f] \approx \int_{x_{1}}^{x_{2}} \bigg( L + \frac{\partial L}{\partial f} \delta f + \frac{\partial L}{\partial f'} \delta f' \bigg) dx $$

Since we are trying to find $$ \delta J $$ such that: 

$$\delta J = J[f + \delta f] - J[f] \rightarrow 0 $$ 

Subtracting the two integrals:

$$ \delta J = \int_{x_{1}}^{x_{2}} \bigg( L + \frac{\partial L}{\partial f} \delta f + \frac{\partial L}{\partial f'} \delta f' - L \bigg) dx $$


$$ \delta J = \int_{x_{1}}^{x_{2}} \bigg( \frac{\partial L}{\partial f} \delta f + \frac{\partial L}{\partial f'} \delta f'  \bigg) dx = 0  $$

$$ \delta J = \int_{x_{1}}^{x^{2}} \delta L dx $$ 

Now we take a closer look at the $$ \delta L $$ term:

$$ \delta L = \sum_{i} \{ \frac{\partial L}{\partial f} \delta f + \frac{\partial L}{\partial \rho '} \delta \rho '\} $$ 

Introducing $$ \delta \rho ' $$ as:

$$ \delta \rho ' = \frac{d}{dx} \delta f $$ 

so that 

$$ \delta L = \sum_{i} \{ \frac{\partial L}{\partial f} \delta f + \frac{\partial L}{\partial \rho '} \frac{d}{dx} \delta f \} $$ 

We expand the last term to make use of some more terms. 

$$ \frac{d}{dx} \bigg( \frac{\partial L}{\partial f_{i}'} \delta f_{i} \bigg) = \frac{d}{dx} \bigg( \frac{\partial L}{\partial f_{i}'} \bigg) \delta f_{i} + \bigg( \frac{\partial L}{\partial f_{i}'} \bigg) \frac{d}{dx} \delta f_{i} $$  

$$ \frac{d}{dx} \bigg( \frac{\partial L}{\partial f_{i}'} \delta f_{i} \bigg) - \frac{d}{dx} \bigg( \frac{\partial L}{\partial f_{i}'} \bigg) \delta f_{i} = \bigg( \frac{\partial L}{\partial f_{i}'} \bigg) \frac{d}{dx} \delta f_{i} $$ 

Back to our $$ \delta J $$ integral:

$$ \delta J = \int_{x_{1}}^{x_{2}} \sum_{i} \{ \frac{\partial L}{\partial f_{i}} \delta f_{i} - \frac{d}{dx} \bigg(\frac{\partial L}{\partial f_{i}}\bigg) \delta f_{i} + \frac{d}{dx} \bigg( \frac{\partial L}{\partial f_{i}'} \delta f_{i}  \bigg)\}$$ 

We can simply this integral a bit. Taking a look at our last term:


$$ \sum_{i} \int_{x_{1}}^{x_{2}} \frac{d}{dx} \bigg( \frac{\partial L}{\partial f_{i}'} \delta f_{i}  \bigg) dx$$

$$ = \sum_{i} \int_{x_{1}}^{x_{2}} d \bigg( \frac{\partial L}{\partial f_{i}'} \delta f_{i}  \bigg) $$

$$ = \sum_{i} \frac{\partial L}{\partial f_{i}} \delta \rho_{i} \biggr|_{x_{1}}^{x_{2}} = 0 $$ 

Since there is no variation of the trajectory at the endpoint, this last term is $$ 0 $$. 

Back to $$ \delta J $$ again, we pull out a common factor $$ \delta f_{i} $$:

$$ \delta J = \int_{x_{1}}^{x_{2}} \sum_{i} \{ \frac{\partial L}{\partial f_{i}} - \frac{d}{dx} \bigg( \frac{\partial L}{\partial f_{i}} \bigg) \}\delta f_{i} dx$$  

Now we apply the fundamental lemma to the following terms:

$$ M(x) =  \frac{\partial L}{\partial f_{i}} - \frac{d}{dx} \bigg( \frac{\partial L}{\partial f_{i}} \bigg) $$  

$$ \eta (x) = \delta f_{i}$$

$$ M(x) $$ looks familiar... and with a change of variables:

$$ x \rightarrow t $$ 

$$ f_{i} \rightarrow q_{i} $$ 

we arrive at Lagrange's equation, $$ \frac{\partial L}{\partial q_{i}} - \frac{d}{dt} \bigg( \frac{\partial L}{\partial \dot{q_{i}}} \bigg) = 0 $$  

which follows from Hamilton's principle for monogenic systems with holonomic constraints. 

## Hamilton's Principle with Constraints

Hamilton's principle for multiple degrees of freedom is given by:

$$ \delta J = \int_{t_{1}}^{t_{2}} \sum_{i} \bigg( \frac{\partial L}{\partial q_{i}} - \frac{d}{dt} \frac{\partial L}{\partial \dot{q}_{i} }\bigg) \delta q_{i} dt = 0 $$

For a system with two degrees of freedom or 2 generalized coordinates ($$ N = 2 $$; $$q_{1}$$ & $$q_{2}$$):


$$ \delta J = \int_{t_{1}}^{t_{2}} \biggr[ \bigg( \frac{\partial L}{\partial q_{1}} - \frac{d}{dt} \frac{\partial L}{\partial \dot{q}_{1} }\bigg) \delta q_{1} + \bigg( \frac{\partial L}{\partial q_{2}} - \frac{d}{dt} \frac{\partial L}{\partial \dot{q}_{2} }\bigg) \delta q_{2} \biggr] dt = 0 $$  

and

$$ f(q_{1}, q_{2}, t) = 0 $$

where $$ f $$ is a fixed function (**NOT** related to $$ f_{i} $$ in variations). Since this function is _fixed_, there are no variations, $$\delta f = 0 $$.

Decomposing $$ \delta f $$ and solving for $$q_{2}$$...

$$ \delta f = \frac{\partial f}{\partial q_{1}} \delta q_{1} + \frac{\partial f}{\partial q_{2}} \delta q_{2} = 0 $$ 

$$ \delta q_{2} = - \frac{\partial f/ \partial q_{1}}{\partial f / \partial q_{2}} \delta q_{1} $$ 

we replace $$ \delta q_{2} $$ in $$ \delta J = 0$$ 

$$ \biggr[ \bigg( \frac{\partial L}{\partial q_{1}} - \frac{d}{dt} \frac{\partial L}{\partial \dot{q}_{1} }\bigg) \delta q_{1} = -  \bigg( \frac{\partial L}{\partial q_{2}} - \frac{d}{dt} \frac{\partial L}{\partial \dot{q}_{2} }\bigg) \frac{\partial f/ \partial q_{1}}{\partial f / \partial q_{2}} \delta q_{1}  \biggr] = - \lambda(t) $$  

After some algebra, we end up with three equations with three unknowns:

(1) $$ \frac{\partial L}{\partial q_{1}} - \frac{d}{dt} \bigg( \frac{\partial L}{\partial \dot{q}_{1}} \bigg) + \lambda(t) \frac{\partial f}{\partial q_{1} } = 0 $$  


(2)  $$ \frac{\partial L}{\partial q_{2}} - \frac{d}{dt} \bigg( \frac{\partial L}{\partial \dot{q}_{2}} \bigg) + \lambda(t) \frac{\partial f}{\partial q_{2} } = 0 $$  

(3) $$ f ( q_{1}, q_{2}, t ) = 0 $$


Before we introduce the **Lagrange Multipler**, $$ \lambda (t) $$. For some context, treatment of non-holonomic systems with the variational principle is only possible if equations of constraint can be written as:

$$ f_{\alpha} (q_{1},...,q_{n}; \dot{q}_{1}, ..., \dot{q}_{n})  = 0 $$

when this can be done, the constraints are called "_semi-holonomic_", where $$ \alpha $$ indicates more than one such equation.

For $$ m $$ equations, $$ \alpha = 1,2,...,m $$, we can write this in a restricted form:

$$ \sum_{k} a_{ik} d_{qk} + a_{it} dt = 0 $$ 

When coordinates are not independent, but subject to constraint relations, it becomes important whether the varied path is or isnot constructed by displacements consistent with the constraints. Virtual displacements may or may not satisfy the constraints. To alleviate this, we use the method of **Lagrange undetermined multiplers** to eliminate extra virtual displacements. Lagrange's equation can be extended to:

$$ \frac{\partial L}{\partial q_{i}} - \frac{d}{dt} \frac{\partial L}{\partial \dot{q}_{i}} + \sum_{\alpha = 1}^{m} \lambda_{\alpha} \frac{\partial f_{\alpha}}{\partial q_{i}} = 0 $$

For $$ i = 1,...,m $$, $$ f_{\alpha} (q_{i} ,t ) = 0 $$, and $$ n = 3N-(k-m) $$.

### An Example Lagrangian with Constraints

Consider a particle described by the Lagrangian:

$$ L = \frac{1}{2} m ( \dot{x}^{2} + \dot{y}_{2} + \dot{z}_{2}) - V(x , y , z) $$

subject to the constraint:

$$f(\dot{x},\dot{y},\dot{z}) = \dot{x} \dot{y} + ky = 0 $$ 

where $$ k $$ is a constant.

Solving the Lagrangian for $$ \frac{\partial L}{\partial q_{k}} $$ and $$ \frac{\partial L}{\partial \dot{q}_{k}}$$ yields these equations of motions:

$$ m \ddot{x} + \lambda \ddot{y} + \dot{\lambda} \dot{y} = \frac{\partial V}{\partial x} = 0 $$ 

$$ m \ddot{y} + \lambda \ddot{x} - k \lambda + \dot{\lambda} \dot{x} + \frac{\partial V}{\partial y} = 0 $$

$$ m \ddot{z} + \frac{\partial V}{\partial z} = 0 $$ 

The equation of constraint then becomes:

$$ \dot{y} \dot{x} + k y = 0 $$ 



# Conservation Theorems

A system with $$n$$ degrees of freedom will have $$n$$ differential equations that are second order in time. The solutions to these equations will require two integrations, $$2n$$ constants of integration. The initial values or coordinates $$nq_{j}$$ and $$n\dot{q}_{j}$$ will determine the value of these constants. 

Many problems that take the form:

$$ f( q_{1}, q_{2},...,\dot{q}_{1},\dot{q}_{2},...,t) = constant $$ 

are first order differential equations, where their first integrals can be obtained immediately, which can give us physical information about our system. 

Recall the particle in an electromagnetic field described by a velocity dependent potential[*](#velocity-dependent-potentials-and-the-dissipation-function).

The Lagrangian that describes the system is:

$$ L = \frac{1}{2} \sum_{i} m_{i} \vec{\dot{r}^{2}_{i}}  - \sum_{i} q_{i} \phi (\vec{r}_{i} )+ \sum_{i} q_{i} \vec{A}(\vec{r}_{i}) \dot{} \vec{\dot{r}}_{i} $$ 

Note that $$q_{i}$$ in this Lagrangian denotes EM charge, _not_ generalized coordinates!  

Consider just the $$ x $$ component of the Lagrangian ($$ y $$ and $$ z $$ will follow the same treatment):

$$ \frac{\partial L}{\partial \dot{x}_{i}} \equiv \frac{\partial T}{\partial \dot{x}} - \frac{\partial V}{\partial \dot{x}} $$ 

Velocity is dependent on position, $$ x $$, not velocity, $$ \dot{x} $$! Therefore, $$ \frac{\partial V}{\partial \dot{x}} = 0$$. 

$$ \frac{\partial L}{\partial \dot{x}_{i}} = \frac{\partial T}{\partial \dot{x}} = m \dot{x} = p_{ix} $$

We come to the conclusion that:

$$ \frac{\partial L}{\partial \dot{q}_{j}} = p_{j}$$. 

This term has a number of names, **generalized momentum**, **canonical momentum**, **conjugate momentum**. All these names refer to the same type of momentum.
So with $$\frac{d}{dt} \frac{\partial L}{\partial \dot{q}} = 0$$...

It turns out that $$ p_{j} = constant $$.

It should also be noted that $$ p_{j} $$ does not nessessarily have dimensions of linear momentum. Furthermore, with a velocity dependent potential, the geneneralized potential will not be identical with _mechanical potential_.

Another thing to notice is that the Lagrangian does not contain a given coordinate $$ q_{j} $$, although it may have the corresponding $$ \dot{q} $$. These coordinates are known as **cyclic** and are _ignorable_.

**(Theorem) General Conservation Theorem; Cyclic Coordinates:** The generalized momentum conjugate to a cyclic coordinate is conserved.  

For instance, if a Lagrangian is independent of position coordinate, $$ x $$, then linear momentum is conserved in the $$ x $$ direction. We call the $$ x $$ coordinate a cyclic coordiate. 

Stepping back to view the grand scheme of things, the conservation theorem provides a new way of thinking about conservation beyond the Newtonian framework:

+ Newtonian framework: With $$ F = ma $$ and $$ F_{x} = 0 $$, this implies that $$ P_{x} = constant $$and momentum is conserved.

+ Lagrangian framework: If $$ L(\{ q_{i} \}, \{ \dot{q}_{i} \}, t) $$ is independent of $$q_{i}$$, then the corresponding conjugate (to $$q_{i} $$) momenum is conserved. Mathematically, $$ P_{i} \equiv \frac{\partial L}{\partial \dot{q}_{i}} = constant $$ is a statement of conservation.

The Lagrangian makes use of symmetry. In other words, symmetry implies conservation!

# The Central Force Problem

Consider a monogenic system such as the one below:

<img src="/assets/twobody.png" class="center">

The Lagrangian will have the form: 

$$ L = T ( \dot{\vec{R}}, \dot{\vec{r}} ) - U (\vec{r},\dot{\vec{r}},... )  $$

We choose the two generalized coordinates, $$ q_{i} $$:

$$ \vec{R}_{CM} = \frac{m_{1} \vec{r}_{1} + m_{2} \vec{r}_{2}}{m_{1}+m_{2}} $$ 


$$ \vec{r} = \vec{r}_{2} - \vec{r}_{1} $$ 

$$ R_{CM} $$ points to the center of mass of the system and $$ \vec{r} $$ is the distance between $$ m_{1} $$ and $$ m_{2} $$. 

It is also worth defining vectors _relative_ to the center of mass:

$$ \vec{r}_{1}' = \vec{r}_{1} - R_{CM} $$

$$ \vec{r}_{2}' = \vec{r}_{2} - R_{CM} $$

Recall that the total kinetic energy, $$ T $$ can be decomposed into motion components of the center of mass,$$ T_{CM} $$, and motion relative to the center of mass, $$T_{rcm}$$.

$$ T = T_{CM} + T_{rcm} $$

Center of mass kinetic energy is straightforward:

$$ T_{CM} = \frac{1}{2} (m_{1} + m_{2}) \dot{\vec{R}}_{CM}^{2} $$

Now, before dealing with $$T_{rcm}$$, $$\vec{r}$$ should be expressed in terms of $$\vec{r}_{1}'$$ and $$ \vec{r}_{2}'$$. TO do this we take advantage of center of mass coordinates relative to the center of mass, which is just a zero vector:

$$ m_{1} \vec{r}_{1}' + m_{2} \vec{r}_{2}' = \vec{0} $$

Combining this with $$ \vec{r} = \vec{r}_{2} - \vec{r}_{1} $$, we obtain our coordinates relative to the center of mass in terms of $$\vec{r}$$:

$$ \vec{r}_{1}' = - \frac{m_{2} \vec{r}}{m_{1} + m_{2}} $$ 

$$ \vec{r}_{2}' = \frac{m_{1} \vec{r}}{ m_{1}+m_{2}} $$

Now, setting up $$ T_{rcm} $$,

$$T_{rcm} = \bigg[ \frac{1}{2} m_{1} \bigg( \frac{m_{2}}{ m_{1} + m_{2} } \bigg)^{2} \bigg] \dot{\vec{r}}^{2} = \frac{1}{2} \bigg( \frac{m_{1} m_{2}}{ m_{1} + m_{2}} \bigg) \dot{\vec{r}}^{2}$$

Let $$ \mu = \frac{m_{1} m_{2}}{m_{1} + m_{2}}$$, the reduced mass. The term "reduced" is given because it reduces motion about the center of mass of two objects down to one. T_{rcm} then simplifies to ,

$$ T_{rcm} = \frac{1}{2} \mu \dot{\vec{r}}^{2} $$

The Lagrangian with all its terms is:

$$ L = \frac{m_{1} + m_{2}}{2} \dot{\vec{R_{CM}^{2}}}+ \frac{1}{2} \frac{m_{1} m_{2}}{m_{1} + m_{2}} \dot{\vec{r}}^{2} - U(\vec{r}, \dot{\vec{r}}, ...) $$ 




# References

+ Classical Mechanics by Goldstein, Poole & Safko

+ Mechanics by Landau & Lifshitz 

+ [David Tong's Notes on Classical Mechanics](http://www.damtp.cam.ac.uk/user/tong/dynamics.html)

+ [Caltech Notes](https://sites.astro.caltech.edu/~golwala/ph106ab/ph106ab_notes.pdf)

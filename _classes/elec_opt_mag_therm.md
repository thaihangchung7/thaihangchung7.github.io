---
layout: notes
title: Electical, Optical, Magnetic, Thermal Material Properties 
category: notes
---

# Maxwell-Boltzmann Distribution

The **Boltzmann distribution** describes the probability of a system to exist in a particular state as a function of temperature ($$T$$) and its energy ($$E$$). The distribution can be expressed as:

$$ \frac{n_{E}}{N} = C \exp(-\frac{E}{kT})$$

where 

+ $$n_{E}$$ is the number of atoms per unit volume at energy $$E$$
+ $$N$$ is the total number of atoms per unit volume in the system
+ $$C$$ is a system dependent constant (so-called weak energy dependence)
+ $$k$$ is Boltzmann's constant
+ $$T$$ is the temperature

Consider a system with a large number non-interacting classical particles the probability distribution function 

$$ f(v)d^{3}v = \bigg[ \frac{m}{2\pi kT} \bigg]^{3/2} \exp\bigg( - \frac{mv^{2}}{2kT} \bigg) d^{3} v $$



# Kinetic Molecular Theory

# Drude Model
## Classical Theory of Conductivity

Consider a monovalent metal such as Sodium which has a bcc strucutre. We assume an electron cloud where each atom contributes one electron to. The number of atoms per cubic centimeter, $$N_{a}$$ is given by,

$$N_{a} = \frac{N_{0} \rho}{M} $$

where $$N_{0}$$ is Avagadro's number, $$\rho$$ is the density of the element, and $$M$$ is the mass of the element. 

Under the influence of an applied electric field $$\vec{E}$$, the electrons experience a force $$e\vec{E}$$ and are accelerated towards the anode with a drift described by,

$$ m \frac{dv}{dt} = e \vec{E}$$

where $$e$$ is the charge, $$\vec{E}$$ is the applied field, and $$m$$ is the electron mass. However, this suggests that as long as the electric field is present, the electrons drift with constant acceleration, which also means that when $$\vec{E}$$ is removed, the electrons drift with a constant velocity. Barring a few superconducting materials, this is an unphysical phenomenon. 

Materials have an intrinsic resistance that counteracts the electrostatic force $$e \vec{E}$$. As electrons move through a material medium, they lose energy due collisions against lattice atoms. Moreover, resistance is dependent on defect properties such as impurities, vacancies, grain boundaries, dislocations, amongst other defect types.

To rectify this, a "friction" term, $$\gamma v$$ is added to adjust for electrical resistance. 

$$m \frac{dv}{dt} + \gamma v = e \vec{E} $$

where $$\gamma$$ is a constant and $$v$$ is the damping force which also contains the drift velocity. 

We consider the steady state case $$v=v_{f}$$ where the friction force and the electrostatic force are equal in magnitude, then $$dv/dt = 0$$.

$$ \gamma v_{f} = e \vec{E} $$

Solving for $$\gamma$$,

$$\gamma = \frac{e \vec{E}}{v_{f}} $$

Reinserting into the adjusted drift velocity equations yields a differential equation for electrons under the effects of an electrostatic force and a resistive force.

$$m \frac{dv}{dt} + \frac{e \vec{E}}{v_{f}} v = e \vec{E}$$

The solution for $$v$$ is, 

$$v = v_{f} \bigg[ 1 - \exp \bigg( - \bigg( \frac{e\vec{E}}{m v_{f}} t \bigg) \bigg) \bigg] $$

The average time between collisions or **relaxation time** is contained within a time constant, $$\tau$$, 

$$\tau = \frac{m v_{f}}{e \vec{E}} $$

This equation can be rearranged to obtain and expression for the final drift velocity $$v_{f}$$,

$$v_{f} = \frac{\tau e \vec{E}}{m}$$

A quick analysis of units reveals the definition for the mean free path,

$$l = v \tau$$ 

### Classical Definition for Conductivity

Recall the current density, $$j$$:

$$j = N v e$$

where $$N$$ is the number of electrons per unit volume, $$v$$ is the electron velocity, and $$e$$ is the charge. The current density, $$j$$ can also be written in terms of conductivity, $$\sigma$$, and the electric field, 

$$j = \sigma \vec{E}$$

All together, by combining the two definitions of current density, we can obtain an important expression for conductivity,

$$ j = N v e = \sigma \vec{E}$$ 

$$ \sigma = \frac{N e^{2} \tau}{m}$$

This equation for conductivity, which is now written in terms of the number of free electrons, $$N$$, and relaxation time, $$\tau$$, reveals that the conductivity is proportional to both variables. 

# Fermi Distribution

For electrons in a crystal, the Fermi energy, $$E_{F}$$, is the maximum energy electrons occupy at $$0 K$$. In terms of the free elecron density,

$$E_{F} = \bigg( 3 \pi^{2} \frac{N^{*}}{V} \bigg)^{2/3} \frac{\hbar^{2}}{2m} $$

This begins with the *Fermi function*, $$F_{E}$$. Suppose we have a free electron cloud that follows Fermi-Dirac statistics, in other words, identical and indistinguishable particles, the distribution is given by,

$$F(E)  = \frac{1}{\exp \bigg( \frac{E - E_{F} }{k_{B} T } + 1 \bigg) }$$ 

Pointing out a few details, first, if energy level $$E$$ is completely occupied by electrons, then the exponential term becomes $$e^{0} = 1$$ and $$F_{E} = 1$$. Second, for $$E=0$$, or an empty energy level, then we have $$F(E) = 0$$. Third, for $$T \neq 0 $$, the curve is broadened slightly as shown in the figure below. Note that the decrease in $$F(E)$$ for increasing $$E$$ is overemphasized. In practice, the $$\Delta E$$ amounts to $$1\%$$ of $$E_{F}$$.

<img src = '/assets/Fermi_dist.png' class='center'>

<!--
# Density of States



$$ S_{v} (E') = \int_{0}^{E'} g(E) dE $$

$$ E = \frac{h^{2}}{8m_{e} L^{2}} (n_{1}^{2} + n_{2}^{2} + n_{3}^{2} ) $$

$$S_{orb} (n') = \frac{1}{8} \bigg( \frac{4}{3} \pi n'^{3} \bigg) = \frac{1}{6} \pi n'^{3} $$

$$ S(n') = 2 S_{orb} (n') = \frac{1}{3} \pi n'^{3} $$

$$ S(E') = \frac{ \pi L^{3} (8 m_{e} E')^{3/2}}{3 h^{3}} $$

$$ S_{v} (E') = \frac{ \pi (8 m_{e} E')^{3/2} }{3 h^{3} } $$

$$ g(E) = (8 \pi 2^{1/2} ) \bigg( \frac{m_{e}}{h^{2}} \bigg)^{3/2} E^{1/2} $$

$$n = \int_{band} f(E) g(E) dE $$

-->

<!--

## Reciprocal Lattice Vector Definitions

To obtain the reciprocal lattice vectors for given direct lattice vectors, 

$$ b_{1} = 2\pi \frac{ a_{2} \times a_{3} }{ a_{1} \cdot a_{2} \times a_{3} } $$

$$ b_{2} = 2\pi \frac{ a_{3} \times a_{1} }{ a_{1} \cdot a_{2} \times a_{3} } $$

$$ b_{3} = 2\pi \frac{ a_{1} \times a_{2} }{ a_{1} \cdot a_{2} \times a_{3} } $$

where the denominator is the volume of the unit cell $$ V_{cell} = a_{1} \cdot a_{2} \times a_{3}$$. In other conventions, the vectors are also labeled:

$$ a = a_{1}$$,
$$ b = a_{2}$$,
$$ c = a_{3}$$,

and 

$$ a^{*} = b_{1}$$,
$$ b^{*} = b_{2}$$,
$$ c^{*} = b_{3}$$

Consider a simple cubic lattice, as shown below:

<img src='/assets/real_recip_lattice.png' class='center'>

The real lattice vectors (drawn in red) form a unit cell from which the reciprocal lattice (blue) can be defined. Notice that the reciprocal lattice is perpendicular to the real space face of the lattice, which also be seen by the cross product definition of the reciprocal lattice vector ($$a^{*} = b \times c$$, or $$b^{*} = c \times a$$).

<img src='/assets/real_space_face.png' class='center'>

This property can also be represented in terms of a delta function:

$$ b_{j} \cdot a_{i} = 2 \pi \delta_{ij}$$

-->

# Lattice Dynamics and Thermal Properties

## Phonons

Lattice vibrations traveling along $$x$$ can be described as,

$$ u_{r} = A\exp{i(kx_{r} - \omega t)} $$

The phonon energy and momentum is,

$$ E_{phonon} = \hbar \omega = hf $$

$$ p_{phonon} = \hbar k $$

and the dispersion relationship is,

$$ \omega = 2 \big( \frac{K}{M} \big)^{1/2} \big| \sin{ (\frac{1}{2} ka) } \big| $$

Using $$\omega$$, the derivative with respect to wavevector $$k$$ is the group velocity,

$$ v_{g} = \frac{d\omega}{dk} = a \big(\frac{K}{M}\big)^{1/2} \cos{ \frac{ka}{2}}$$

where, for sufficiently long wavelengths, $$\frac{ka}{2} \ll 1$$, we can see that $$v_{g}$$ reduces to a constant, 




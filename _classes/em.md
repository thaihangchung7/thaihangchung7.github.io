---
layout: notes
title: Electromagnetism 
category: notes 
---

Important concepts and applications in Electromagnetism (and a meager attempt at interpreting Jackson's book). 

## Deriving Current Density $$ J $$ 

Consider a conductive cylinder with some cross-sectional area $$ A $$. Let $$ dx $$ be an infinitesimal section of the cylinder. The number of electrons passing through the cylinder is:
$$ n_{e^{-}} = - e N A dx $$ 

Taking the time-derivative yields the current:

$$ I = \frac{d Q}{dt} = - e N A \frac{dx}{dt} $$ 

Dividing through by $$ A $$ gives current density, $$ J $$:

$$ \frac{I}{A} = J = - e N v $$

### In a Metal

Using out definition of $$ J $$ from above, we put the equation of motion of an electron in a metal in terms of velocity, $$ \vec{v} $$ and plug in $$ \vec{v} $$ in terms of $$ J $$.

$$ m \frac{d^{2}\vec{r}}{dt^{2}} = - e \vec{E} - \gamma m \frac{d\vec{r}}{dt} $$



# Polarization of a Dielectric Medium 

Consider a simple dielectric, a non-conducting (no free-charges) material whose properties are isotropic. The application of an $$ \vec{E} $$ field produces an induced dipole, a slight shift in the electron cloud relative to the nucleus.

The **dipole moment** can be defined as:

$$ \vec{p} = - q \vec{r} $$

where $$q$$ is the magnitude of the displace charge and $$ \vec{r} $$ points from the effective negative charge center relative to the effective positive charge center in a dipole.The direction of the dipole moment points from the negative to positive charges. 

The **Polarization** of the medium is defined as the collective dipole moment per unit volume:

$$ \vec{P} = - N e \vec{r} $$ 

where $$ N = n/V $$, the number of elementary dipoles per unit volume and $$ e $$ is the magnitude electron charge. 

We can start out with a simple Hooke's law model where electrons are bound by spring-like forces to a fixed nucleus. Like a spring, the forces binding the electrons to the nucleus has a restoring force that is proportional to the displacement and is oppositely directed.

$$ F_{s} = -K_{s} \vec{r} $$

Adding another layer to the model, due to the intertions of neighboring atoms and thermal energy loss in the presence of an alternating $$ E $$ field, an oscillating electron can be modelled after a damped harmonic oscillator with a "frictional" force proportional to velocity. 

Thus, the resulting equation of motion for this model is:

$$ -K_{s} \vec{r} - m \gamma \frac{d \vec{r}}{dt} - e \vec{E} = m \frac{d^{2} \vec{r}}{dt^{2}} $$

where $$ K_{s} $$ is the force constant of an effective spring, $$ m $$ is the electron mass and $$ \gamma $$ is the frictional constant with dimensions $$ s^{-1} $$. 

**A small detour: Negligible $$ F_{\vec{B}}$$**

Notice that the equation of motion for our electron-nucleus model does not include the force provided by a $$ \vec{B} $$ field. Let's find the ratio of the forces of the $$ \vec{E}$$ and $$ \vec{B} $$ fields. 

$$ \frac{F_\vec{E}}{F_\vec{B}} = \frac{e |E|}{v |B|} $$

Recall that the speed of light is a ratio of the $$ \vec{E} $$ and $$ \vec{B} $$ fields i.e. $$ c = \frac{E}{B} $$. Using that definition:

$$ \frac{F_\vec{E}}{F_\vec{B}} = \frac{c}{v} $$

Here $$ c = 3 \times 10^{8} m/s \gg v $$. Hence, $$F_{\vec{B}}$$ is negligible. 

**A small detour II: static $$\vec{E} $$ fields** 

In the special case of an applied $$ \vec{E} $$ field that is _static_, the dipoles do not oscillate, both $$ \frac{d^{2} \vec{r}}{dt^{2}} $$ and $$ \frac{d \vec{r}}{dt} $$ are both $$ 0 $$.  

Using this result, **static polarization** is defined as:

$$ \vec{P} = \frac{N e^{2} \vec{E}}{K_{s}} $$ 

## Polarization of a Dielectric Medium (continued)

Suppose that $$ \vec{E} $$ is a harmonic field given by:

$$ \vec{E} = \vec{E}_{0} e^{-i \omega t}$$ 

$$ \vec{r} = \vec{r}_{0} e^{-i \omega t}$$ 

The derivatives for the differential equation:

$$ \frac{d\vec{r}}{dt} = - i \omega r_{0} e^{-i \omega t} = - i \omega \vec{r} $$ 

$$ \frac{d^{2} \vec{r}}{dt^{2}} = - \omega^{2} r_{0} e^{- i \omega t} = - \omega^{2} \vec{r} $$ 

Solving...

$$ - K_{s} \vec{r} - m \gamma (- i \omega \vec{r} ) - e \vec{E} = m ( - \omega^{2} \vec{r} ) $$

$$ \vec{r} = \frac{e \vec{E}}{- m \omega^{2} - i m \omega \gamma + K_{s}} $$

Substituting this into the Polarization equation yields:

$$ \vec{P} = \bigg( \frac{Ne^{2}}{-m \omega^{2} - i m \omega \gamma + K_{s}} \bigg) \vec{E} $$

## Relationship between $$ n $$ and $$ \epsilon_{r} $$

The index of refraction can be represented as the ratio between the speed of light in vacuum versus in a medium:

$$ n = \frac{c}{v} $$ 

Recall the speed of light (in vacuum) can be written as:

$$ c = \frac{1}{\sqrt{\mu_{0} \epsilon_{0}}} $$

whereas in a medium:

$$ v = \frac{1}{\sqrt{\mu_{0} \epsilon }} $$

Combining the two definitions above:

$$ n = \frac{\sqrt{\mu_{0} \epsilon}}{\sqrt{\mu_{0} \epsilon_{0}}} $$

$$ n = \sqrt{\frac{\epsilon}{\epsilon_{0}}} = \sqrt{\epsilon_{r}} $$

Where $$ \epsilon_{r} $$ is the **relative permittivity**.


# Lasers (pew pew)

## Photon Absorption and Emission
Due to quantum mechanics, electrons are found in discrete energy levels, or "positions" in orbitals. Atoms exchange energy via absorption, spontaneous emission, and stimulated emission. To paraphrase Einstein: A boson can stimulate or induce another boson into the same quantum state causing an even like atomic transition. 

+ Absorption: Just as it sounds, a photon is absorbed, bumping an electron into a higher energy state.

+ Spontaneous Emission: An excited electron is inherently unstable in its higher energy state and will drop to a lower energy state, spontaneously releasing a photon. 

+ Stimulated Emission: One incoming photon with a specfic frequency interacts with an excited electron dropping it to a lower energy state. Subsequently, two photons with identical properties are released. Such properties include phase, frequency, polarization. The emitted photons are _coherent_ and _monochromatic_.   

Max Planck's radiation law states that when a oscillator changes from energy state $$ E_{2} $$ to a lower energy state $$ E_{1} $$, a photon with energy $$ \Delta E = E_{2} - E_{1} = h \nu $$ is emitted.

## Boltzmann Distribution

The Boltzmann Distribution is given by:

$$ P_{i} = P_{0} e^{- \Delta E / k_{B} T } $$


Where $$ P_{0} $$ is the ground state probability, $$ \Delta E = E_{i} - E_{0} $$, $$ k_{B} $$ is the Boltzmann constant, and $$ T $$ is temperature.

In thermal equilibrium, the Boltzmann distribution states that when there are more atoms in the ground state than the excited state, the probability of absorption is much higher than emission. If there are more excited states then the process of stimulated emission is more likely, and under the right conditions, a single input photon can result in a cascade of photons, "amplifying" the input photon.

## Principle Components

A laser requires three major components:

1) Gain meduim (gas,solid,liquid dye or semiconductor)

2) Pump source (electric discharge, flashlamp, laser diode)

3) Feedback system (crystal oscillator)

Lasing mediums contain at least three energy levels, $$ E_{1} $$, $$ E_{2} $$, and $$ E_{3} $$. Each level are purposed as follows:

+ $$ E_{1} $$: A ground state

+ $$ E_{2} $$: An metastable (intermediate) state, with a relatively long lifetime $$t_{s}$$

+ $$ E_{3} $$: A high energy pump state

## Three Level Laser System

All atoms of the laser material are initially in their ground state, $$ E_{1} $$. The pump radiation exictes the ground state atoms to a short lived pump state with energy $$ E_{3} $$. Atoms undergo a radiationless transition to a metastable state with energy $$ E_{2} $$.

To obtain population inversion, $$ t_{s} > t_{3} $$, where $$ t_{3} $$ is the lifetime of the high energy pump state.



# References

+ Classical Electrodynamics, J.D. Jackson 

+ Introduction to Electrodynamics, D.J. Griffiths

+ [maxwells-equations.com/equations/wave.php](EM wave equation)
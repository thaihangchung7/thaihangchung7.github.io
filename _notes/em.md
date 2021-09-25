---
layout: notes
title: Electromagnetism 
category: notes 
---

Important concepts in Electricity and Magnetism (and a meager attempt at interpreting Jackson's book). 

## Deriving Current Density $$ J $$ 

Consider a conductive cylinder with some cross-sectional area $$ A $$. Let $$ dx $$ be an infinitesimal section of the cylinder. The number of electrons passing through the cylinder is:
$$ n_{e^{-}} = - e N A dx $$ 

Taking the time-derivative yields the current:

$$ I = \frac{d Q}{dt} = - e N A \frac{dx}{dt} $$ 

Dividing through by $$ A $$ gives current density, $$ J $$:

$$ \frac{I}{A} = J = - e N v $$

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








# References

+ Classical Electrodynamics, J.D. Jackson 

+ Introduction to Electrodynamics, D.J. Griffiths

---
layout: notes
title: Electromagnetism 
category: notes 
---

Important concepts in Electricity and Magnetism. 

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




# References

+ Classical Electrodynamics, J.D. Jackson 

+ Introduction to Electrodynamics, D.J. Griffiths

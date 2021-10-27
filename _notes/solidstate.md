---
layout: notes
title: Solid State Physics 
category: notes 
---

Background required for research, mostly solid state physics (maybe a wee bit of particle physics)

# Solid State Physics

## Electrons in a Crystal

Using X-ray diffraction and electron microscopy atoms, we know that electrons are arranged uniformly in a lattice due to a periodic potential. In a one dimensional model, there are two models to consider:

+ The Kronig-Penny model:
This is an approximate/simplified model for an electron in a one dimensional periodic potential. The states that an electron can occupy can be found with the Schrodinger equation. The potential $$V(x)$$ is a square wave. 

<img src="/assets/kronigpenny.png" class="center">

+ Muffin-tin approximation:
Developed by John C. Slater (with ties to QTP at UF!) is a more accurate approximation of the potential well in a crystal lattice. It is commonly used for simulations of electronic band structure in solids.

For now, we use the Kronig-Penny model to determine the behavior of an electron in a periodic potential. Starting from the Schrodinger equation:

$$ - \frac{\hbar}{2m} \frac{d^{2} \psi}{d x^{2}} + V(x) = E \psi $$ 

As stated before, we solve the equation for two regions, $$ I $$ and $$ II $$.

In region $$I$$, the potential is $$ V(x) = 0 $$:

$$ \frac{d^{2} \psi}{d x^{2}} +  \frac{2m}{\hbar} E \psi  = 0 $$

The solved energy comes out to be:

$$ \frac{2m}{\hbar^{2}} E = \alpha^{2} \rightarrow E = \frac{\hbar^{2}}{2m} \alpha^{2}$$

In region $$II$$, $$V(x) = V_{0} $$: 

$$ \frac{d^{2} \psi}{d x^{2}} + \frac{2m}{\hbar^{2}} (E - V_{0}) \psi = 0 $$

*there appears to be a negative sign absorbed in here... not sure into what though.

Let $$ \gamma^{2} = \frac{2m}{\hbar^{2}} (V_{0} - E) $$ 

To solve for these to regions simultaneously, we use the **Bloch Function**:

$$ \psi(x) = U(x) e^{ikx} $$ 

where $$ U(x) $$ is a periodic potential. Product differentiation to the second order gives:

$$ \frac{d \psi}{d x} = \frac{d U(x)}{dx} e^{ikx} + U(x) ik e^{ikx} $$

$$ \frac{d^{2} \psi}{d x^{2}} = i \frac{d U(x)}{d x} e^{ikx} + \frac{d^{2} U(x)}{dx} e^{ikx} + i \frac{d U(x)}{dx} e^{ikx} + i^{2} k^{2} U(x) e^{ikx} $$

$$ = e^{ikx} \bigg[ \frac{d^{2} U(x)}{dx^{2}} + 2 i k \frac{d U(x)}{dx} - k^{2} U(x) \bigg]$$

Now its just a matter of plugging in the solved quantities into the differential equations. In region $$ I $$: 

$$ \frac{d^{2} U(x)}{dx^{2}} + 2ik \frac{d U(x)}{dx} - (k^{2} - \alpha^{2}) U(x) = 0 $$

In region $$ II $$:

$$ \frac{d^{2} U(x)}{dx^{2}} + 2ik \frac{d U(x)}{dx} - (k^{2} + \alpha^{2}) U(x) = 0 $$

We arrive at the master equation:

$$ \frac{d^{2} U(x)}{dx^{2}} + D \frac{d U(x)}{dx} + C U(x) = 0 $$ 


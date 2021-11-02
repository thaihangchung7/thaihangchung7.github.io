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

The general solution to this equation is:

$$ U(x) = e^{- \frac{D}{2} x} \bigg[ Ae^{i \eta x} + Be^{-i \eta x} \bigg] $$ 

where $$ \eta = \sqrt{ C - \frac{D^{2}}{4}} $$ 


The solutions for regions $$I$$ and $$II$$ are as follows:

### Region $$I$$

$$ U(x) = (A e^{i \alpha x} + B e^{- i \alpha x}) e^{-ikx}$$

### Region $$II$$

$$ U(x) = ( C e^{-\gamma x} + D e^{i\gamma x} ) e^{-ikx} $$

From here, determine coefficients $$ A, B, C, D $$ from boundary conditions (refer to V(x) graph).

**Boundary Condition** $$ 1 $$: The first boundary condition is at $$ x = 0 $$, the wave function of both regions must be equal to each other:

$$ \Psi_{I} = \Psi_{II} $$ 

which implies:

$$ A + B = C + D $$ 

**Boundary Condition** $$ 2 $$: The wavefunctions must also be continuous through their derivatives at $$x=0$$:

$$ \frac{d}{dx} \Psi_{I} = \frac{d}{dx} \Psi_{II} $$

$$ \bigg( \frac{d U(x)}{dx} \bigg)_{I} = \bigg( \frac{d U(x)}{dx} \bigg)_{II} $$ 

Again we solve for regions $$ I $$ and $$ II $$ evaluating the derivatives at $$ x = 0 $$ :

**Region** $$I$$:

$$ \frac{d U(x)}{dx} = - i k A e^{i \alpha x} + A i \alpha e^{-ikx} - i k B e^{i\alpha x} + B (- i \alpha) e^{i k x} $$ 

$$ \frac{d U(x)}{dx}\bigg|_{x=0} = -ik A + A i \alpha - ik B + B (-i \alpha) $$

$$ = A ( i\alpha - ik) - B ( i \alpha + ik) $$ 

**Region** $$ II $$:

$$ \frac{d U(x)}{dx} \bigg|_{x=0} = C (-\gamma - ik ) + D (\gamma - ik) $$ 

Therefore, the derivatives at $$ x = 0 $$ can be written as:

$$ A (i \alpha - ik) - B (i \alpha + ik) = C (-\gamma - ik) - D (\gamma - ik) $$
**Boundary Condition** $$III$$:

$$ \Psi_{I} (x=a) = \Psi_{II} (x=-b) $$ 

and

$$ U_{I} (x=a) = U_{II} (x=-b) $$ 

The resulting evaluation:

$$ A e^{(i \alpha - ik) a} + B e^{(i \alpha - i k) a }  = C e^{(ik + \gamma)b} + D e^{(ik - \gamma) b} $$

**Boundary Condition** $$4$$:

As before, the wavefunctions must be continuous through its derivatives:

$$ \frac{d U(x)}{dx} \bigg|_{I (x=a)} = \ \frac{d U(x)}{dx} \bigg|_{II (x=-b)} $$ 

The result:

$$ A i (\alpha - k) e^{i\alpha(a-k)} - Bi(\alpha+k) e^{i\alpha(a+k)} = -C (\gamma + ik) e^{(ik+\gamma)b} + D(y-ik) e^{(ik - \gamma)b} $$ 

### Applying some approximations:

*Most of this will be "left as an exercise to the reader", but I will at least leave some bread crumbs along the way:* 

Making use of Euler's equations: 

$$ e^{ix} = \cos(x) + i \sin(x) $$ 

$$ \cos(x) = \frac{1}{2} (e^{ix} + e^{-ix}) $$

$$ \sin(x) = \frac{1}{2i} (e^{ix} - e^{-ix}) $$ 

we arrive at:

$$ \frac{\gamma^{2} - \alpha^{2}}{2\alpha\gamma} \sinh(\gamma b) \sin(\alpha a) + \cosh(\gamma b) \cos(\alpha a) = \cos(k (a+b)) $$ 

Using the following approximations and definitions:

+ $$V_{0} \gg E $$ 

+ $$b \ll $$ 

+ $$\gamma^{2} \gg \alpha^{2} $$

+ $$ b \gg a $$ 

We can simply $$\gamma$$ which also extends to $$\gamma b$$:

$$ \gamma = \sqrt{ \frac{2m}{\hbar^{2} } (V_{0} - E)} \approx \sqrt{\frac{2m}{\hbar^{2}} V_{0}}$$

For small $$\gamma b $$:

$$\cosh(\gamma b) \approx 1 $$

$$\sinh(\gamma b) \approx \gamma b $$

### Allowed solutions/Allowed energy zones

These approximation simplify the periodic solution to:

$$ \frac{P \sin(\alpha a)}{\alpha a} + \cos(\alpha a) = \cos(k a) $$ 

where

$$ P = \frac{2 m V_{0} b a}{\hbar^{2}}$$

This equation determines the allowed solutions in a periodic potential. 


---
layout: notes
title: Solid State Physics 
category: notes 
---

Background required for research, mostly solid state physics (maybe a wee bit of particle physics)

# Electrons in a Periodic Potential 

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

$$ \frac{d^{2} \psi}{d x^{2}} +  \frac{2m}{\hbar^{2}} E \psi  = 0 $$

The solved energy comes out to be:

$$ \frac{2m}{\hbar^{2}} E = \alpha^{2} \rightarrow E = \frac{\hbar^{2}}{2m} \alpha^{2}$$

In region $$II$$, $$V(x) = V_{0} $$: 

$$ \frac{d^{2} \psi}{d x^{2}} + \frac{2m}{\hbar^{2}} (E - V_{0}) \psi = 0 $$

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

This is also called the **Penny constant**, which determines the allowed solutions in a periodic potential. Recall that $$a$$ is the spereation distance between atoms in a lattice.

<img src="/assets/kronigpenney.png" class="center">

From here, some cases can be applied to investigate the behavior of the system.

### Cases for $$P$$ 

When $$P \rightarrow $$ large, the height of the curve grows larger with steeper slopes, the bands become narrow. In the limit that $$P \rightarrow \infty$$, they shrink to the quantized infinite square well energy ($$ E = \frac{n^{2}\hbar^{2}}{2ma^{2}} $$), since $$ P \propto V_{0}$$. Of course, the opposite applies. When $$ P \rightarrow $$ small, this results in wider bands. 

When $$P=0$$, $$ \cos(\alpha a) = \cos(ka) $$. Then, $$\alpha=k$$, this is the situation of the free electron with $$ E = \frac{\hbar^{2}k^{2}}{2m} $$.

## Brillion Zones

<img src="/assets/BZ.png" class="center">

The $$E(k)$$ curve can be segmented into regions called **Brillouin Zones**. 

For the case of a one dimensional lattice, the *first Brillouin zone* exists from $$ - \frac{\pi}{a} \leq k \leq \frac{\pi}{a} $$. This region is also known as the **n-band**.

The *second Brillouin zone* exists from $$ - \frac{2\pi}{a} \leq k \leq -\frac{\pi}{a} \cup \frac{\pi}{a} \leq k \leq \frac{2\pi}{a} $$, or the **m-band**. 




# Band Theory of Solids

## In Semiconductor Crystals

**Band Gaps** or energy gaps (usually denoted $$E_{g}$$) are the regions where no electronic states can exist as a result of Bloch's theorem and allowed solutions/energies in a periodic potential.

<img src="/assets/bandgap.png" class="center">
Above is the band diagram of silicon. Notice the band gap energy of about $$ 1eV $$ 

Flat band diagrams provide a better way of visualizing band gaps.

<img src="/assets/flatband.png" class="center">
Here is a flat band diagram of a p-n junction. 

Above $$E_{g}$$ is the **conduction band**, and below is the **valence band**. Both of these bands exist near the Fermi level ($$E_{f}$$ or $$ \mu$$) , is the top most energy of the occupied states

For reference, below is a table of Energy/Band gaps of common materials:

$$
\begin{array} {|r|r|}\hline 
Si & 1.17 eV \\ \hline 
Ge & 0.74 eV \\ \hline 
Sn & 0.08 eV \\ \hline 
C & 5.48 eV \\ \hline  \end{array}
$$

## Dispersion Relation E(k) 

$$ E = \frac{\hbar^{2}}{2m} k^{2} $$

## Effective Mass

Suppose an electron is subject to a force exerted by an $$\vec{E}$$ field. The group velocity is:

$$ v_{g} = \frac{d\omega}{dk}$$

Recalling some wave theory terms; the center frequency is $$ \omega = 2\pi\nu $$, the wavevector is $$ k = \frac{2\pi}{\lambda} $$, and $$ E=h \nu $$, the group velocity can be rewritten as:

$$ v_{g} =  \frac{d (2\pi\nu)}{dk} = \frac{2\pi(E/h)}{dk} = \frac{1}{\hbar} \frac{dE}{dk} $$ 

Following, the acceleration is simply the time derivative of $$v_{g}$$ (don't forget that this is an implicit derivative!!!):

$$ a = \frac{d v_{g}}{dt} = \frac{1}{\hbar^{2}} \frac{d^{2} E}{dk^{2}} \frac{dk}{dt}$$

We want to expand on the $$ \frac{dk}{dt} $$ term into something more useful. Beginning with the wave momentum or the deBrogile momentum: 

$$ p = \hbar k $$ 

$$ \frac{dp}{dt} = \hbar \frac{dk}{dt} $$ 

$$ \frac{1}{\hbar} \frac{dp}{dt} = \frac{dk}{dt} $$  

Coming back to the acceleration equation:

$$ a = \frac{1}{\hbar^{2}} \frac{d^{2}E}{dk^{2}} \frac{dp}{dt} $$ 

$$ = \frac{1}{\hbar^{2}} \frac{d^{2} E}{dk^{2}} \frac{d(m\vec{v})}{dt} $$ 

$$ = \frac{1}{\hbar^{2}} \frac{d^{2} E}{dk^{2}} F $$  

Following from the familiar $$ F=ma $$, the effective mass can be expressed as:

$$ m^{*} = \hbar^{2} \bigg(\frac{d^{2}E}{dk^{2}} \bigg)^{-1} $$ 

One thing to point out in this equation is that $$m^{*}$$ is inversly proportional to the the $$E(k)$$ curve! 

## Electron Mobility

There are a few ways to describe electron mobility, all of these decribe how an electron moves through a medium:

+ Hole mobility: When electrons make the jump to say, the conduction band, a hole is left behind. Neighboring electrons are attracted and fill the empty spot. The hole appears in a new location, giving it a sense of "mobility". 

+ Carrier mobility: This term refers to *both* electron and hole mobility.

Electron mobility can be defined in terms of drift velocity:

$$ v_{d} = -\mu_{e} E$$ 

where $$\mu_{e}$$ is the electron mobility, $$ v_{d} $$ is the drift velocity, and $$E$$ is the magnitude of the electric field applied across the material. Hole mobility is similary defined:

$$ v_{d} = \mu_{h} E$$ 

It is also useful to describe **conductivity** as it is proportional to the product of mobility and carrier concentration. Usually denoted $$\sigma$$, conductivity can be expressed in terms of mobility as:

$$ \sigma = N \mu e $$ 



### Fermi Energy/Level

A good way to think about the Fermi level is to put it in terms of population. Electrons are classified as fermions and follow Fermi-Dirac statistics. The distribution is given by:

$$ \frac{1}{1 + e^{(E-u)/k_{b}T}} $$ 

where $$ u $$ is the Fermi level, $$k_{b}$$ is the Boltzmann constant, and $$ T $$ is the temperature. When the system is at the Fermi level, the ratio $$ \frac{E}{u} = 1 $$ and $$k_{B}T$$ = 1. So, the population $$n$$ is $$ 1/2 $$. 

The distribution describes how parameters such as temperature $$T$$ and purity can increase the Fermi level, and by extension, increase conductivity. Suppose the system's Fermi energy sits in the middle of the valence and conduction band. Increase the temperature brings the Fermi level closer to the conduction band, allowing the electrons to make an easy jump to the conduction band. 

Introducing impurities, or doping the material with atoms that have excess electrons can also increase the Fermi energy. 

### p-Type and n-Type Semiconductor Doping

Consider an electrically neutral silicon semiconductor.

**Intrinsic semiconductors** are , well, naturally semiconducting. This means that the number of excited electrons and holes are equal, $$p=n$$. Applying an external voltage to the material will make some electrons jump the band gap, supporting charge flow. For example, pure silicon is a group $$IV$$ intrinsic semiconductor. The figure below on the left shows the four valence electrons with covalent bonds around each silicon atom.

<img src="/assets/pntype.png" class="center">

However, as stated earlier, doping semiconductors can dramatically affect the conductivity of the material, making these materials into **extrinsic semiconductors**. Suppose a group $$V$$ atom was introduced into the silicon lattice as shown in the center figure. There will be an free electron (conduction electron) making this impurity a **donor**. Moreover, since a *negatively* charged electron was introduced, this make the doped material an **n-type semiconductor**. 

On the other hand, doping the silicon semiconductor with a group $$III$$ atom makes the hole a majority carrier and the electrons a minority carrier. The holes accept the free elecron, so the impurity in this case is called an **acceptor**. Holes are "positively" charged which making this a **p-type semiconductor**.  



## Direct and Indirect Band Gaps

There are two classifications of band gaps; direct and indirect. **Direct band gaps** indicate that momemtum is conserved. In detail, the crystal momentum of electrons and holes are the same in both the conduction and valence band. The band diagram below is of Gallium Arsenide, a direct band gap semiconductor. This is a useful property since the electron can directly emit a photon!

<img src="/assets/dbg.png" class="center"> 
Notice that the *minimal energy state* of the conduction band and the *maximum energy state* of the valence band line up. If plotted in an $$E(k)$$ diagram, such as the one for silicon, one would say that these min/max energy states are characterized by a certain crystal momentum (k-vector).


Referring to the band diagram of of [Silicon](#in-semiconductor-crystals), an indirect band gap semiconductor. **Indirect band gaps** indiate that some energy was lost in order for momentum to be conserved. The electron must travel pass through an intermediate state in order such that momentum is transferred through the crystal lattice. Graphically, the min-max energies of the Silicon band diagram do not line up. 



(In band digrams, parabolas indicate free electrons?)

(What does it mean if the fermi level is near the conduction or valence band?)

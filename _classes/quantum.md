---
layout: notes
title: Quantum Mechanics 
category: notes 
---

$$ \let\vec\mathbf $$ 
$$\newcommand{\v}{\vec} $$
$$\newcommand{\d}{\dot{}}$$ 
$$\newcommand{\del}{\nabla}$$
$$\newcommand{\abs}{\rvert} $$
$$\newcommand{\h}{\hat}$$ 
$$\newcommand{\f}{\frac}$$ 
$$\newcommand{\~}{\widetilde}$$
$$\newcommand{\<}{\langle}$$
$$\newcommand{\>}{\rangle}$$
$$\newcommand{\eo}{\epsilon_{0}}$$
$$\newcommand{\hb}{\hbar}$$
$$\newcommand{\pd}{\partial}$$

# Time Independent Schrodinger Equation

For a given **potential energy function** $$V(x,t)$$, the Schrodinger equation, independent of $$t$$ is written as:

$$i \hb = - \f{\hb^{2}}{2m} \f{\pd^{2} \Psi}{\pd x^{2} } + V \Psi  $$


# Infinite Square Well

Consider a situation where a particle is trapped in a potential well with infinitely high walls. The potential is described mathematically as,

$$
V(x) = \left\{
\begin{array}{ll}
      0 & 0 \leq x \leq a, \\
      \infty & \verb|otherwise| \\
\end{array} 
\right.
$$

The time indpendent Schrodinger equation can be set up using known conditions of the system. 

+ Outside the well, the probability of finding the particle equal to zero, in other words, the wavefunction is $$psi(x) = 0$$. 

+ Inside the well, the potential is $$V=0$$

The Schrodinger equation then takes the form,

$$ - \f{\hb^{2}}{2m} \f{d^{2} \psi}{dx^{2}} = E \psi$$

We can divide through by $$ -\f{\hb^{2}}{2m} $$ and where $$k \equiv \f{\sqrt{2mE}}{\hb}$$

$$ \f{d^{2} \psi}{dx^{2}} = - k^{2} \psi$$

The general solution this differential equation is,

$$ \psi(x) = A\sin{kx} + B\cos{kx} $$

With both the wave function, $$\psi$$, and its derivative ,$$\f{d\psi}{dx}$$, being continuous, this just means that both are differentiable. 

Applying the boundary conditions, the continuity of $$\psi(x)$$ require that 

$$ \psi(0) = \psi(a) = 0 $$

Thus at $$\psi(0)$$, 

$$\psi(0) = 0  = A \sin{0} + B\cos{0} = B $$

Plugging $$ B = 0 $$ back into the general solution yields

$$\psi(x) = A \sin{kx} $$

At $$\psi(a) $$, we come across two cases in order to satify $$\psi(a) = 0 $$. The wavefunction at $$a$$ is,

$$ \psi(a) = A \sin{ka} $$

The two cases being,

+ $$A=0$$, non-normalizable $$ \psi(x) = 0 $$ (not a good solution, the wavefunction MUST appear somewhere!) 

+ $$\sin{ka} = 0 $$, which allows the existence of $$\psi$$

The latter is only true for certain values of $$ka$$, 

$$ ka = 0, \pm \pi, \pm 2\pi, \pm 3\pi, ...$$

Again, we come across another "bad" solution, $$k = 0$$, since this would imply that $$\psi(x) = 0$$. The minus sign from negative solutions such as $$\sin(-\theta) = -\sin(\theta)$$ can be absorbed into the constant $$A$$.

Thus, we arrive at distinct solutions where,

$$k_{n} = \f{n\pi}{a} $$ 

with values of $$n = 1, 2, 3, ...$$. Combining this with definition of $$k$$ in terms of energy $$E$$, 

$$ E_{n} = \f{\hbar^{2} k_{n}^{2}}{2m} = \f{n^{2} \pi^{2} \hb^{2}}{2ma^{2}} $$

To interpret this physically, the energy $$E_{n}$$ can only take on discrete values of $$n$$. We also attach the subscript $$n$$ to denote that $$k_{n}$$ represents the set of **allowed** energies of the wavefunction, which will be important to evaluating the upcoming integral.  

However, $$A$$ is still a missing part of the equation, which is determined by $$k$$. We can solve for $$A$$ by normalizing $$\psi$$. 

> With the help of a trigonometric identity: $$\sin^{2} (\theta) = \f{1-\cos(2\theta)}{2} $$...

$$ \int_{0}^{a} \abs A \abs^{2} \sin^{2}(k_{n} x) dx = \abs A \abs^{2} \int_{0}^{a} \f{1- \cos(2k_{n} x)}{2} dx = 1$$

Using u-subsitution, let $$u=2k_{n} x$$, where $$du = 2k_{n} dx $$, 

$$ \abs A \abs^{2} \bigg[ \f{x}{2} \bigg|_{0}^{a} - \int_{0}^{a} \f{\cos{u}}{2} \f{du}{2} \bigg] = 1$$ 

$$ \abs A \abs^{2} \bigg[ \f{x}{a} - \f{\sin{2k_{n} x}}{4k} \bigg]_{0}^{a} = 1$$

Now it is important to recall that $$k= \f{n \pi}{a}$$. $$k$$ is restricted by $$n = 1,2,3,...$$ and for this reason, the $$\sin2kx$$ term is zero at all values of $$n$$. Now simply solving for $$A$$ will yield the magnitude of $$A$$, picking the positive solution.

$$\abs A \abs^{2} \f{a}{2} = 1$$ 

$$A = \sqrt{\f{2}{a}} $$

Thus, the wavefunction solutions inside the well is,

$$ \psi_{n} (x) = \sqrt{\f{2}{a}} \sin\bigg(\f{n\pi x}{a}\bigg)$$

<img src='/assets/infsqsol.png' class='center'>

Note that the solutions alternate between even and odd between the intervals [0, a] . $$\psi_{1}$$ is even, $$\psi_{2}$$ is odd, $$\psi_{3}$$ is even. This also related to how many nodes, or zero crossings, for successive states $$\psi_{n}$$. The wave function that carries the lowest energy ,$$n=1$$, is the ground state, whereas wavefunctions of energies proportional to $$n^{3}$$ are the excited states. 

Due to the $$\sin$$ terms in states $$\psi_{n} (x)$$ end up being mutually orthogonal. In other words, 

$$\int \psi_{m} (x)^{*} \psi_{n}(x) dx = 0 $$ 

when $$m \neq n$$. 

> **_Orthogonality_**: 

$$ \int \psi_{m} (x)^{*} \psi_{n}(x) dx =  \f{2}{a} \int_{0}^{a} \sin{\bigg( \f{m\pi x}{a} \bigg)} \sin{\bigg( \f{n\pi x}{a} \bigg)} dx$$

> Using a product-to-sum trigonometric identity: $$\sin(\alpha)\sin(\beta) = \f{1}{2} [\cos(\alpha - \beta) - \cos(\alpha + \beta) $$

> $$ = \f{1}{a} \int_{0}^{a} \cos{\bigg(\f{ (m-n) \pi }{a} \bigg)} - \cos{\bigg(\f{ (m+n) \pi }{a} \bigg)}   dx $$ 
> $$ = \f{1}{a} \bigg[ \f{1}{ (m-n) \pi } \sin{\bigg(\f{ (m-n) \pi }{a} \bigg)} -  \f{1}{(m+n) \pi} \sin{\bigg(\f{ (m+n) \pi }{a} \bigg)} \bigg] \bigg|_{0}^{a} $$

> When evaluating from $$0$$ to $$a$$, it should be clear to see that only $$a$$ survives, leaving

> $$ = \f{1}{\pi} \bigg[ \f{ \sin{\bigg(\f{ (m-n) \pi }{a} \bigg)}}{(m-n)} -  \f{\sin{\bigg(\f{ (m+n) \pi }{a} \bigg)}}{(m+n)} \bigg] = 0 $$ (for $$m\neq n$$)

> Rewritten in terms of the Kronecker Delta, 

> $$\int \psi_{m} (x)^{*} \psi_{n}(x) dx = \delta_{mn} $$ 






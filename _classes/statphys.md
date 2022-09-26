---
layout: notes
title: Statistical Mechanics
category: notes
---

*"My life has consisted in learning and forgetting and learning and forgetting and learning and forgetting statistical mechanics".* - Leonard Susskind 

<!--
# Laws of Thermodynamics

## Zeroth Law

## First Law

## Second Law

## Third Law
-->

# A Review of Expectation Value

Recall that any system that has a discrete set of states in some parameter such as energy, $$E$$, the expectation value (or average) is defined as the weighted sum of the discrete energy states,

$$ \big< E \big> =  \sum_{i} p_{i} E_{i}$$

likewise, the average magnetization can be calculated as,

$$ \big< M \big> =  \sum_{i} p_{i} M _{i}$$

The same can be done for quantities such as spin...

<!--
# Boltzmann Distribution
-->

# Ensembles
The purpose of statistical mechanics is to calculate the macrostate properties such as temperature and pressure, without knowing the exact microstate of the system. 

Naturally, many different microstates (or a set of isolated systems?) subject to constraints can say something about a macrostate. This concept is known as an **ensemble**. 

## The Canonical Ensemble
While there are many ensembles in statistical mechanics, the one that gets the most mention is the **cannonical ensemble**.

The canonical ensemble describes a set of fixed state variables. Namely,

+ Fixed $$N$$: number of particles
+ Fixed $$V$$: Volume
+ Fixed $$T$$: Temperature (Note: This is not a statement about the system itself. The system is allowed to exchange energy with a heat bath with a large heat capacity such that the temperature *of the bath* stays fixed.)

That being said, a system decribed by the canonical ensemble is allowed to have energy flucuations. 

# Principle of Maximum Entropy

## Discrete Probability

Given that $$P$$ is discrete probability distribution, the discrete entropy is defined as,

$$ S(P) = - \sum_{x \in X} P(x)ln(P(x))$$

Suppose some constraints on $$P$$ are,

+ $$ P(x) \geq 0 $$.
+ $$ \sum_{x \in X} P(x) = 1 $$. 
+ $$ \sum_{x \in X} P(x) r_{i}(x) = \alpha_{i}$$ for $$ 1 \leq i \leq m$$ 

First, define $$S^{*}(P,\lambda_{1},\lambda{2})$$, which is entropy with the constraint terms subtracted from it.

$$S^{*} (P,\lambda_{0},\lambda_{1},...,\lambda_{m}) = -\sum_{x \in X} P(x)\ln(P(x)) + \lambda_{0} \big( \sum_{x \in X} P(x) - 1 \big) + \sum_{x \in X}^{m} \lambda_{i} \sum_{x \in X} \big( P(x) r_{i}(x) - \alpha_{i} \big)$$

We take the maximum of entropy by setting the derivative of $$S^{*}$$ with respect to $$P(x)$$ equal to zero:

$$\frac{\partial S^{*}}{\partial P(x)} = -\ln P(x) - 1 + \lambda_{0} + \sum_{i=1}^{m} \lambda_{i} r_{i}(x) = 0$$

solving for $$P(x)$$ gives,

$$P(x) = e^{(\sum_{i=1}^{m} \lambda_{i}r_{i}(x)) + \lambda_{0} - 1 }$$

$$P(x) = \frac{e^{(\sum_{i=1}^{m} \lambda_{i}r_{i}(x)) }  }{e^{1-\lambda_0} }$$

Applying the constraint $$\sum_{x \in X} P(x) = 1$$, 

$$\sum_{x \in X} P(x) = \sum_{x \in X} e^{(\sum_{i=1}^{m} \lambda_{i}r_{i}(x)) + \lambda_{0} - 1 }$$

$$ = e^{\lambda_{0} - 1 } \sum_{x \in X} e^{\sum_{i=1}^{m} \lambda_{i} r_{i}(x)} = 1$$

Thus, $$P(x)$$ is rewritten as,

$$ P(x) = \frac{e^{\sum_{i=1}^{m} \lambda_{i} r_{i}(x)}}{\sum_{x \in X} e^{\sum_{i=1}^{m} \lambda_{i} r_{i}(x)}}$$

 
## Principle of Max Entropy Applied to Continuous Systems

**Note: The notation can be simplified further. Since $$x \in \Omega$$ is the microstate parameter, we can simply write $$\Omega$$. Keeping in mind that $$\Omega$$ is a function of parameters such as momentum and position, $$\Omega(\vec{P_{1}},...,\vec{P_{N}},...,\vec{r_{1}},...,\vec{r_{N}}) $$**

The hamiltonian of any system can be written with the kinetic energy, interaction between particles, and external potential,

$$ H(\Omega) = \sum_{i} \frac{\vec{P_{i}^{2}}}{2m} + \frac{1}{2} V_{ij} + \sum_{i} U_{i}$$


Depending on whether the system is a gas or a fluid, the particle interaction term $$V_{ij}$$ is,

$$V_{ij} = 0$$ (for a gas)

$$V_{ij} \neq 0$$ (for a fluid)

Now consider an ideal gas, where we can assume $$V_{ij} = 0 $$ and $$U_{i}=0$$. This leaves the hamiltonian with only the kinetic energy term, 

$$H(n) = \sum_{i} \frac{P_{i}^{2}}{2m}$$

Some constraints can be set up using information about normalized distributions, 

$$\int P(\Omega)  d\Omega = 1 $$ 

and the definition of continous entropy,

$$S(X) = - \int_{x \in \Omega} P(x) \ln(P(x)) dx $$

where the expectation value of the Hamiltonian is equivalent to the expectation value of the energy (with a switch of notation from $$x$$ to $$\Omega$$),

$$\big< H \big> = \int_{x \in \Omega} H(\Omega) P(\Omega) d\Omega =  \big<E\big>$$

We can "extend" what we found for discrete probabilities for a continuous systems (non-rigorously exchanging the sums for integrals),

$$P(\Omega) = \frac{e^{-\lambda_{1} H(\Omega)}}{\int e^{-\lambda_{1} H(\Omega)} d\Omega}$$

Multiplying both sides by a $$d\Omega$$ term givesus something we can integrate,

$$P(\Omega) d\Omega = \frac{e^{-\lambda_{1} H(\Omega)}}{\int e^{-\lambda_{1} H(\Omega)} d\Omega} d\Omega$$


### (A quick detour) Introducing the Partition Function

In a system with discrete energy states, $${E_{i}}$$, the probability of the system being in the $$i$$-th state is 

$$ p_{i} = \frac{e^{-\beta E_{i}}}{\sum_{j} e^{-\beta E_{j}}}$$ 

where $$\beta = 1/k_{B} T$$, is Boltzmann's constant. The term in the denominator known as $$Z$$, the **partition function**. For a classical and discrete system described by the canonical ensemble, 

$$ Z = \sum_{j} e^{-\beta E_{j}}$$

where $$j$$ is the index of the microstates in the system. Using this partition function formalism, all state variables can be calculated! 

## Back to (Principle of Max Entropy Applied to Continuous Systems)

Using constraint for $$\big<H\big>$$, we can replace some terms, 

$$\big< H \big> = \int_{x \in \Omega} H(\Omega) P(\Omega) d\Omega$$

$$\big< H \big> = \int_{x \in \Omega} H(\Omega) \bigg( \frac{e^{-\lambda_{1} H(\Omega)}}{\int e^{-\lambda_{1} H(\Omega)} d\Omega}  \bigg) d\Omega$$

where the partition function for continuous systems is 

$$Z = \int e^{-\lambda_{1} H(\Omega)} d\Omega$$

so $$\big< H \big>$$ can be rewritten as

$$\big< H \big> =  \frac{ \int H(\Omega) e^{-\lambda_{1} H(\Omega)}}{Z} d\Omega$$

If we take a closer look at the partition function $$Z$$, we can natural log both sides of the equation,

$$ \ln(Z) = \ln(\int e^{-\lambda_{1}H} d\Omega)$$

Taking the partial derivative with respect to $$\lambda_{1}$$...

Recall that $$\frac{d \ln(e^{-ax})}{dx} = - \frac{a}{x}$$

$$\frac{\partial \ln(Z)}{\partial \lambda_{1}} = - \frac{\int (-H) e^{\lambda_{1} H} d\Omega}{\int e^{-\lambda_{1} H} d\Omega} = - \big< E \big>$$ 


More importantly,

$$\big< E \big> = -\frac{\partial}{\partial \lambda_{1}} \ln(Z)$$

In other words, instead of calculating multiple integrals, you can quickly arrive at $$\big< E \big>$$, given that you know what $$Z$$ is. 

Similarly, the following shows the relationship between the expecation value of $$E$$ and the partition function for discrete systems:

$$ \big< E \big> = \sum_{i} p_{i} E_{i} = \frac{\sum_{i} E_{i} e^{-\beta E_{i}}}{Z} = -\frac{\partial}{\partial \beta} \ln(Z) $$

This can be further extended to give a definition for the variance of a quantity. Recall that the variance is given by,

$$ \sigma_{H} = \big< H^{2} \big> - \big< H \big>^{2} $$

$$ = \int P(\Omega) H^{2}(\Omega) d\Omega - \bigg(  \int P(\Omega) H(\Omega) d\Omega  \bigg)^{2} $$

$$ = \frac{\partial^{2} \ln(Z) }{\partial \lambda^{2}_{1}}$$ 

<!--
## $$\big< E \big>$$ for an Ideal Gas
-->

# The Ising Model

Consider a chain of $$N$$ spins with $$S_{i} = \pm 1$$. The hamiltonian accounts for an external magnetic field $$\vec{B}$$ and a spin interaction term a magnitude $$J$$:

$$ H = - \sum_{i=1}^{N} s_{i} \vec{B} - J \sum_{i = 1}^{N} s_{i} s_{i+1} $$

It's difficult to see this *a priori*, but we prepare for a mathematical trick (a transfer matrix) by rewriting one of the spin terms using, 

$$ \sum_{i=1}^{N} s_{i} = \frac{1}{2} \sum_{i=1}^{N} s_{i} + s_{i+1} $$ 

If you stare at the equation long enough, you will understand that the factor of $$\frac{1}{2}$$ shows up to avoid double counting spins. The purpose of doing this is to rewrite the hamiltonian into a sequence of products, which will be helpful in constructing the transfer matrix. 

$$ H = - \sum_{i=1}^{N} \frac{1}{2} (s_{i} + s_{i+1}) \vec{B} - J \sum_{i = 1}^{N} s_{i} s_{i+1} $$

Applying the partition function for discrete systems, 

$$Z = \sum_{\Omega} e^{\beta H(\Omega)}$$ 

the sum over phase space $$\Omega$$ will be for each spin state for $$N$$ particles

$$ Z = \sum_{s_{1}} \sum_{s_{2}} ... \sum_{s_{N}} e^{\beta  \sum_{i=1}^{N} \frac{1}{2} (s_{i} + s_{i+1}) \vec{B} + J \sum_{i = 1}^{N} s_{i} s_{i+1} } $$

rewriting the sum as a product,

$$ Z = \sum_{s_{1}} \sum_{s_{2}} ... \sum_{s_{N}} \prod_{i=1}^{N} e^{\beta \frac{1}{2} (s_{i} + s_{i+1}) \vec{B} + J s_{i} s_{i+1} } $$

To simplify the busy equation, let $$ P_{ij} = e^{\beta \frac{1}{2} (s_{i} + s_{j}) \vec{B} + J s_{i} s_{j} }$$

$$ Z = \sum_{s_{1}} \sum_{s_{2}} ... \sum_{s_{N}} P_{s1s2} P_{s2s3} P_{s3s4} ... P_{sNs1} $$

for $$N$$ particles, it turns out to be the definition of trace for an $$N\times N $$ matrix, 

$$ = \sum_{s_i = \pm 1} P_{s1s1}^{N} = Tr[ P^{N}]$$ 

There will be 4 combinations of $$s_{i}$$, from which we can contruct a $$2\times 2 $$ matrix, 

$$s_{i} = +1, s_{i+1} = +1 \rightarrow \vec{B} + J$$ 

$$s_{i} = +1, s_{i+1} = -1 \rightarrow - J$$ 

$$s_{i} = -1, s_{i+1} = +1 \rightarrow - J$$ 

$$s_{i} = -1, s_{i+1} = -1 \rightarrow - \vec{B} + J$$ 

$$\bigg(  \begin{matrix}
e^{\beta (J+B)} & e^{-\beta J} \\
e^{-\beta J} & e^{\beta (J-B)}
\end{matrix} \bigg)$$

Given any $$N\times N$$ matrix, the traces is equal to the sum of its eigenvalues,

$$ Tr(A) = \sum_{i=1}^{N} \lambda_{i} $$

so the partition function can be written in terms of the two matrix eigenvalues:

$$ Z = \lambda_{1}^{N} + \lambda_{2}^{N} $$

The matrix eigenvalues can be solved for using the standard matrix diagonalization/characteristic equation method,

$$\det(A - \lambda \mathbb{1}) = 0 $$

$$(e^{\beta (J+B)} - \lambda) (e^{\beta (J-B)} - \lambda) - e^{-\beta J} e^{-\beta J} = 0 $$ 

In order to solve for $$\lambda$$, recall some hyperbolic identities,

$$\frac{e^{x} + e^{-x}}{2} = \cosh(x)$$

$$\frac{e^{x} - e^{-x}}{2} = \sinh(x)$$

After some algebra, 

$$\lambda_{1,2} = -e^{\beta B} \cosh(\beta B) \pm \sqrt{ \sinh^{2}({\beta B}) + e^{-4BJ} } $$

We can drop $$\lambda_{2}$$ if we make the case for $$N \rightarrow \infty$$,

$$ Z = \lambda_{1}^{N} + \lambda_{2}^{N} = \lambda_{1}^{N} \bigg( 1 + \frac{\lambda_{2}^{N}}{\lambda_{1}^{N}} \bigg)$$

Since $$\lambda_{1}$$ is the larger eigenvalue and will domininate when $$N$$ is taken to infinity, 

$$ Z \approx \lambda_{1}^{N} $$

## Mean Field Theory (MFT) Approach to 1-D Ising Model

Consider the [Ising model hamiltonian again](#the-ising-model). MFT aims to decouple the spin interaction terms by introducing $$\delta_{s_{i}} \equiv s_{i} + \big< s_{i} \big> $$, in other words, fluctuations about the mean of spin $$s_{i}$$

$$s_{i} =  \big< s_{i} \big> + \delta_{s_{i}} $$

The spin interaction terms can be expanded to include $$\delta_{s_{i}}$$ and $$\delta_{s_{j}}$$, 

$$s_{i} s_{j} = (\big< s_{i} \big> + \delta_{s_{i}}) (\big< s_{j} \big> + \delta_{s_{j}})$$

$$ = \big< s_{i} \big> \big< s_{j} \big> + \big<s_{i} \big> \delta_{s_{j}} + \big< s_{j} \big> \delta_{s_{i}} + \delta_{s_{i}} \delta_{s_{j}}$$.

MFT makes the assumption that fluctuations are small, where,

$$\delta_{s_{i}} \delta_{s_{j}} = 0 $$

By replacing the $$\delta$$'s with spin their definition, the spin interaction can be rewritten as the following approximation,

$$ \big< s_{i} \big> s_{j} + \big< s_{j} \big> s_{i} - \big< s_{i} \big> \big< s_{j} \big> $$ 

given that the system is translationally invariant, let $$\big< s_{i} \big> = m$$.

The spin interaction term is further simplified to, 

$$ s_{i} s_{j} = m (s_{j} + s_{i}) - m^{2} $$







# Some Useful Integrals

Gaussian integrals are all over the place in statistical mechanics (and quantum mechanics). Here are some shortcuts:

$$ \int_{-\infty}^{\infty} e^{-\alpha x^{2}} dx = \sqrt{\frac{\pi}{\alpha}}$$

$$ \int_{-\infty}^{\infty} x e^{-x^{2}} dx = -\frac{1}{2} e^{-x^{2}} \bigg|_{-\infty}^{\infty} = 0 $$

$$ \int_{-\infty}^{\infty} x^{2} e^{-x^{2}} dx = \frac{\sqrt{\pi}}{2}$$

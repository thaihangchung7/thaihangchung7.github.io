---
layout: notes
title: Statistical Mechanics
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
$$\newcommand{\h}{\hat}$$
$$\newcommand{\ket}[1]{\lvert #1 \rangle}$$

*"My life has consisted in learning and forgetting and learning and forgetting and learning and forgetting statistical mechanics".* - Leonard Susskind 

<!--
# Laws of Thermodynamics

## Zeroth Law

## First Law

## Second Law

## Third Law
-->

# 1st Law of Thermodynamics

The first law of thermodynamics is a statement concerning the internal energy of a system. For some composite system with partitioned with energies $$E_{1}$$ and $$E_{2}$$ partioned, the total internal energy ($$E$$) of the system is an *extensive* (additive) quantity:

$$E = E_{1} + E_{2} $$

Assuming this system is also self-contained, we expect that the energy of the system is conserved. From here, the defintion of heat can be constructed since the only way to add or remove energy, is to do so externally, in other words, perform work:

$$ dE = d Q  + d W $$

Note that both heat ($$Q$$) and work ($$W$$) are _path independent_ variables. 

# 2nd Law of Thermodynamics

Consider a box with a removable partition separating two collections of particles (red and blue). For a fixed number of particles, volume, and energy, the microstate of the system can be described as a function of the thermodynamic variables mentioned, $$\Omega(N,V,E)$$.

We'll describe the partitioned configuration of the box as $$\Omega_{1}$$. Removing the partition will allow the particles to mix (assuming homogeneity), which is the configuration we'll define as $$\Omega_{2}$$.

Upon removal of the partition with some shaking involved, it can be empirically demonstrated that the particles have access to more microstates,

$$ \Omega_{1} < \Omega_{2} $$

Using the Boltzmann defintion of entropy,

$$ S_{1} < S_{2}$$

The change in entropy between can be written as:

$$ ds = S_{2} - S{1} > 0 $$

David Chandler's statement on the second law of thermodynamics is as follows:

"There is an **extensive** function of state $$S(E,\bf{X})$$, which is a **monotonically** increasing function of $$E$$ and if state $$B$$ is **adiabatically** accessible from state $$A$$, then $$S_{B} \geq S_{A}$$"

In this statement $$\bf{X}$$ is an arbitrary parameter that can be assigned to macroscopic measureables such as volume. A few of the bolded terms in the statement can use some elaboration.

## Properties of Entropy (S)

Suppose there are two composite systems $$A$$ and $$B$$ with microstates $$\Omega_{A}$$ and $$\Omega_{B}$$. The systems are then brought together with microstate $$\Omega_{AB}$$. Combinatorically, it can be shown that,

$$ \Omega_{AB} = \Omega_{A}\Omega_{B}$$ 

For instance, if system $$A$$ contains 2 states and system $$B$$ contains 3, bringing the two together will form 6 possible states. Plugging this into the Boltzmann definition of entropy and performing some logarithmic arithmetic,

$$ S_{AB} = k \ln(\Omega_{AB})$$

$$ = k \ln(\Omega_{A} \Omega_{B})$$

$$ = k \ln(\Omega_{A}) + k \ln(\Omega_{B})$$

$$S_{AB} = S_{A} + S_{B}$$

So the two things we can glean from this... Entropy is an additive and extensive quantity! 

From Boltzmann's entropy we can see that $$S \propto ln(x)$$, which implies that $$S$$ is also a monotonically increasing function that cannot be negative.

# Equilibrium and Temperature

The concept of entropy is still a bit "abstract", at least in the context of experiments, much like energy. Although there is a mathematical definition of entropy, there isn't an "entropy-meter" or an instrument that directly measures microstates. However, the connection between entropy and measureable thermodynamic variables such as temperature can be derived empirically.

Consider a heat conduction system with two boxes with their respective $$E$$, $$T$$, and $$S$$. The boxes are thermally connected to each other via some sort of heat pump. At equilibrium, no heat flows between the system; an observational statement. 

An *internal constraint* (a quasi-static perturbation that couples to extensive variables and does not change the total state of the system) can be applied to create a *tiny* displacement from equilibrium. Variationally, the change in entropy is,

$$ (\delta S)_{E,\bf{X}} \leq 0$$

as required for heat to flow between the two systems. In the same context of the variational theorem, the total energy is held constant during displacment. As a consequence of the first law of thermodynamics:

$$ E_{i} = E^{(1)} + E^{(2)} $$ 

where $$E_{i}$$ is initial state of the total energy. Applying the perturbation gives,

$$ E_{f} = (E^{(1)} + \delta E^{(1)} )+ (E^{(2)} + \delta E^{(2)} ) $$ 

Again, because the perturbation is *tiny*, we can effectively say that the initial and final states are equivalent, $$E_{i} = E_{f}$$, in other words,

$$E_{f} - E_{i} = 0 $$

which implies that,

$$ \delta E^{(1)} + \delta E^{(2)} = 0 $$ 

Extending this to entropy using the same treatment, entropy can flow from state $$B$$ to $$A$$ via an internal constraint.

$$ (\delta S)_{E} = S_{A} - S_{B} \leq 0 $$

$$ = [ S^{(1)} (E^{(1)} + \delta E^{(1)} )+ S^{(2)}(E^{(2)} + \delta E^{(2)} ) ]_{A} - [ S^{(1)} (E^{(1)} ) + S^{2} (E^{(2)}) ]_{B} $$ 
 
Let's take a closer look at terms involving $$S(E + \delta E) $$. A Taylor expansion around $$\delta E$$ yields,

$$ S(E + \delta E) = S(E) + \frac{\pd S}{\pd E} \delta E $$

substituting this expansion into $$ (\delta S)_{E} = S_{A} - S_{B} $$ yields,

$$\delta S = \bigg( \frac{\pd S^{(1)}}{\pd E^{(1)}} \bigg) \delta E^{(1)} + \bigg( \frac{\pd S^{(2)}}{\pd E^{(2)}} \bigg) \delta E^{(2)} $$ 

## Equation of State for an Ideal Gas

Consider a volume with some gas and a movable piston enclosing it so that work can be done on the  volume by (de)compressing it. We begin with the definition of heat:

$$ dE = d_{p.i} Q  + d_{p.i} W $$

Here, the subscript $$p.i$$ denotes path independence of the variable (conventionally, this notation is dropped. As will these notes will too). The work done on the the volume by the piston is: 

$$ dW = - p \cdot dV $$ 

It is important to mention here that the negative sign in front of $$p$$ is *non-trivial*. In the case of compressing the system, $$dV$$ should decrease. In other words, for $$dW$$ to be positive _and_ $$p$$ to be positive, the volume $$dV$$ includes the negative. For a reversible process, the energy equation is:

$$ dE = dQ_{rev} + f dX $$ 

where $$f$$ is some generalized force. Plugging this into the equation for the change in entropy:

$$ds = \bigg( \frac{\pd S}{\pd E} \bigg)_{X} (dQ + f\cdot dX) + \bigg( \frac{\pd S}{\pd E} \bigg)_{E} dX$$ 

$$ = \bigg( \frac{\pd S}{\pd E} \bigg)_{X} dQ + \bigg[ \bigg( \frac{\pd S}{\pd E} \bigg)_{X} f + \bigg( \frac{\pd S}{\pd E} \bigg)_{E} \bigg] dX$$ 

Since the process is reversible and adiabatic, $$ dS = 0$$ and $$ dQ = 0$$, which leaves:

$$dS = \bigg[ \bigg( \frac{\pd S}{\pd E} \bigg)_{X} f + \bigg( \frac{\pd S}{\pd E} \bigg)_{E} \bigg] dX = 0 $$

Reexpressing the equation in terms of temperature,

$$\bigg(\frac{1}{T}\bigg) f = \bigg( \frac{\pd S}{\pd X} \bigg) E $$

In other words, this is a description of temperature derived from mechanical work of on a system.
 

The entropy of an ideal gas contained in some volume $$V$$ is:

$$ S = N k \ln{(V)} + f(E,N) $$

Recall that (to contextualized this to arbitrary state variables, $$X$$ will be taking the place of $$V$$ for now): 

$$ dS = \bigg( \frac{\pd S}{\pd E} \bigg)_{X} dE + \bigg( \frac{\pd S}{\pd E} \bigg)_{E} dX $$ 

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

# Statistical Mechanics Applied to Ensembles

## Ensemble Average of the Microcanonical (N,V,E) Ensemble 
Since the complexity of calculating the equation of motion is proportional to the number of particles in a system, In the case of a condensed matter system, where one is dealing with something like $$N=10^{23}$$, this becomes unfeasable. Fortunately, this can be dealt with by introducing the **ensemble average**.

For the micro-canonical ensemble, that is, an $$(N,V,E)$$ system, we can quantify the number of time the number of times a particular state is visited. If $$\Omega$$ represent the total number of microstates available. Naturally, selecting _one_ microstate is simply,

$$ P_{v} = \frac{1}{\Omega} $$ 

## Ensemble Average of the Canonical (N,V,T) Ensemble 

Now suppose you have a system that can exchange energy with an **isolated** heat bath. The probability of find one particular state in this path is roughly:

$$ P_{v} ~ \Omega(E - E_{v}) $$ 

Applying the princple of equal weights, the probability is understood as:

$$ P_{v} = e^{\ln(\Omega (E - E_{v}))} $$

Applying a Taylor expansion for $$E_{V} \ll E$$

$$ ln\Omega(E) + \frac{\pd \Omega}{\pd E} (-\Delta E) $$

















$$ <E> = \frac{1}{L} \int E(v,r) dv dr $$ 

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

$$ s_{i} s_{j} = m (s_{j} + s_{i}) - m^{2} = m (s_{j} + $$







# Some Useful Integrals

Gaussian integrals are all over the place in statistical mechanics (and quantum mechanics). Here are some shortcuts:

$$ \int_{-\infty}^{\infty} e^{-\alpha x^{2}} dx = \sqrt{\frac{\pi}{\alpha}}$$

$$ \int_{-\infty}^{\infty} x e^{-x^{2}} dx = -\frac{1}{2} e^{-x^{2}} \bigg|_{-\infty}^{\infty} = 0 $$

$$ \int_{-\infty}^{\infty} x^{2} e^{-x^{2}} dx = \frac{\sqrt{\pi}}{2}$$

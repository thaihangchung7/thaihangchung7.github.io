---
layout: notes
title: Positron Annihilation Spectroscopy 
category: notes 
---

The focus of these notes is to provide a comprehensive summary on positron annihilation spectroscopy and its applications as well as concepts that are important to PAS. 

# What and Why of Positrons?

## Introduction
A non-destructive technique called Positron Annihilation Lifetime Spectroscopy (PALS or interchangably PAS) can provide information regarding a solid material:

+ Variations in density
+ Defects
+ Displacements
+ Voids
+ Size
+ Concentration
+ Chemical Environment

In the context of Fundamental Understanding of Transport Under Reactor Extremes (FUTURE), a LANL research center, the application is to better understand materials properties when exposed to radiation damage, corrosive enviroments, high stresses and high temperatures which plays a role in nuclear energy research.  

Solids such as metals and semiconductors contain free electrons which annihilate with positrons. This interaction produces gamma rays which can be detected to measure the positron lifetime from its emmision to detection. Below is a figure describing positron annihilation spectroscopy:

<img src="/assets/pastheory.png" class="center">

PAS stands on the principle that positrons can be trapped within defects or vacancies. With a diffusion length of 100nm, the positron then loses its kinetic energy as it travels through the lattice through a process called [thermalization](https://en.wikipedia.org/wiki/Thermalisation). As a result of the repulsive forces from neighboring positively charged nuclei, the positron is trapped in a region of lesser local electron density or where an atom is missing from the lattice. 

Below is a comparison of techniques for resolved defect size.
<img src="/assets/defecttechniques.png" class="center">

Below (Fig 1.) is a Feynman Diagram of $$ e^{+} , e^{-} $$ annihilation emitting a photon. These interactions typically radiate two (three?)(para and ortho positronium?) photons. 

Techniques have been developed to collect quantaties of interest from the annihilation site such as time, energy and angular spectra. 

The energy and momentum of an annihilation are conserved. In other words, the energy of each photon should be equal to the rest mass energy of the $$ e^{+} $$ or $$ e^{-}$$ <span style="color:red"> check wording? </span>, plus or minus the energy due to Doppler Shifting, given by the equation below: 

$$ \Delta E = P_{z} c / 2 $$ 

$$P_{z}$$ is defined as the momentum component of the propagation direction of the photon. The two photons are emitted in oposite directions, plus or minus some angle $$ \Delta \theta $$ defined below:

$$ \Delta \theta_{x,y} = P_{x,y} / m_{o} c $$

where $$ P_{x,y} $$ is the momentum component perpendicular to the direction of propogation. 

Using these both $$ \Delta E $$ and $$ \Delta \theta $$, we can find the the net momentum from the annihilating pair. Below is a list of how different techniques utilize $$ \Delta E $$ and $$ \Delta \theta $$ quantities:

+ DBS (Doppler Broadening Spectroscopy) 
  - An energy distribution is detected with a 511keV Doppler Broadening peak detected. This reflects the longitudinal momenta of the electrons moving in the direction of the detector.

+ ACAR (Angular Correlation Annihilation Radiation) 
  - Momenta in the transverse direction is given by the angular distribution of 511keV.

+ PALS 
  - The lifetime of the positron is measured from the moment the positron enters the medium to its annihilation. 

### Expanding on Lifetime Spectroscopy

The positron lifetime is given by:

  $$ \lambda = \frac{1}{\tau} = \pi r_{o} c^{2} \int |\psi (r) |^{2} n(r) \gamma dr  $$
  
  where $$r_{o}$$ is the electron radius, $$c$$ is the speed of light, $$ r $$ is the position vector, $$ \| \psi (r) \|^{2}$$ is the positron probability density, $$ n(r) $$ is the electron density, and $$ \gamma $$ is an enchancement factor related to the coulombic interactions between positrons and electrons in a local electron density. 

  Positron lifetime is a function of electron density at the annihilation site. The equation below describes the measured lifetime spectrum as the sum of components correspoding to each annihilation site: 

  $$ N(t) = \sum_{i = 1}^{k+1} \frac{I_{i}}{\tau_{i}} e^{- t/ \tau_{i}}$$

where $$ tau $$ is the lifetime and $$ I $$ is the intensity of the $$i$$-th component in the spectrum. 


# Doppler Broadening Techniques

## Doppler Broadening

In spectroscopy, the spectral line are broadened due to the distribution of velocities of atoms. This phenomenon is called Dopper broadening. When annihilating, the $$ e^{+} e^{-} $$ pair decays into two $$ \gamma $$-rays. The Doppler Broadening of the radiation is measured along with the Positron lifetime technique to study defects.   

## Doppler Broadening Spectroscopy
Doppler Broadening spectroscopy peaks are characterized by $$ S $$ and $$ P $$ parameters. The $$\gamma$$-ray spectrum contains the sum total of the contributions from annihilations with different electron states. The shape of the spectrum correspond to the electron momentum distribution during annihilations. Delocalized, weakly bound valence electrons contribute to low momentum distributions, whereas tightly bound core electrons contribute to high momentum distributions. 

## Coincidence DBS

<img src="/assets/cdbs.png" style="width: 70%; height: 70%" class="center">


In traditional DBS, the line-shape variations of the spectrum for high momentum core electrons are not easily measured. To alleviate this, a coincidence measurement of $$ \gamma $$-ray energies using two detectors improves the signal to background ratio ([up to four orders of magnitude](https://journals.aps.org/prb/pdf/10.1103/PhysRevB.61.10092)). 

## S and W Parameters
<img src="/assets/SWparam.png" class="center" >



# $$\gamma$$-Induced PAS 
One technique of PAS utilizes high energy gamma rays to generate positrons via pair production within the material. The advantage being that there is no need for a positron source. Although this technique is not an alternative to standard radioactive or positron beam based apparatuses, it can extend PAS to study materials and defects, such as neutron irradiated materials and structural reactor materials. 


The beam energy needs to be at 1.02 MeV to create $$e^{+} e^{-} $$ pairs but no greater than 15 MeV to avoid unwanted radiation or [atom recoils](https://en.wikipedia.org/wiki/Atomic_recoil).  



# Appendix

## Pair Production and Annihilation

Consider the reaction:

$$ e^{+} + e^{-} \rightarrow p \gamma $$

where $$ p $$ is the order of the process. 

Due to conservation of energy, at least two photons must be produced. Combined at the p verticies:

$$ e^{+} + e^{-} \rightarrow \gamma + \gamma $$ 

<img src="/assets/e_diagram.png" class="center"> 

The Feynman diagram above is an example of an $$ e^{+} e^{-} $$ interaction. The order of the is $$ p = 2 $$ (count the number of verticies in the diagram).
Thus, the associated probability is of order $$ \alpha^{p} $$ ($$ \alpha $$ is the fine structure constant).

# Trapping Model and Defect Calculations

## Defect Calculations from PALS Data

The trapping model assumes that the positron exists in one state out of the two; the "Bulk" or Bloch state or the defect trapped state.

The model is described by a set of coupled differential equations:

$$ \frac{d n_{b}}{dt} = - n_{b} \lambda_{b} - n_{b} k_{t} $$

$$ \frac{d n_{t}}{dt} = + n_{b} k_{t} - n_{t} \lambda_{t} $$

where $$ \lambda_{b} $$ and $$ \lambda_{d} $$ are the positron annihilation rates in bulk and defect trapped states. The annihilation rates is inversely proportional to the positron lifetime, in other words, $$ \tau_{b} \equiv \lambda_{b}^{-1} $$ and $$ \tau_{d} \equiv \lambda_{d}^{-1} $$. $$ k_{t} $$ is the total transition or trapping rate from the positron bulk state to trapping state. 

We can now define the fraction of positrons present within the system at time $$ t $$:

$$ N(t) = n_{b} (t) + n_{t} (t) = (1 - I_{2}) e^{-\Lambda_{1} t} + I_{2} e^{-\Lambda_{2} t}$$ 

Positron trapping rate, $$K_{d}$$ is calculated as

$$ K_{d} = \frac{I_{2}}{I_{1}} ( \frac{1}{\tau_{b}} - \frac{1}{\tau_{d}} ) $$

where $$ \tau_{b} $$ and $$ \tau_{d} $$ are the bulk and defect lifetimes, respectively. $$ I_{2} $$ and $$ I_{1} $$ are the measured intensities.

The trapping rate ($$K_{d}$$) can be used to calculate defect densities ($$ \rho_{d} $$) using:

$$ \rho_{d} = \frac{K_{d}}{\eta_{0}}$$

where $$\eta_{0}$$ is the trapping coefficient, that can be determined theoretically or experimentally and is specific to each defect type.
## Tao-Eldrup Model

-To be added


## Band Gaps

- To be added

## Bremsstrahlung

- To be added

# References

[1] [F.A.Selim, Positron annihilation spectroscopy of defects in nuclear and irradiated materials- a review](https://www.sciencedirect.com/science/article/pii/S1044580321000826#bb0215)

[2] [R. W Siegel Positron Annihilation Spectroscopy](https://www.annualreviews.org/doi/pdf/10.1146/annurev.ms.10.080180.002141) 

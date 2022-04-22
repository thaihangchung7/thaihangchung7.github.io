---
layout: notes
title: Radiation & Nuclear Physics 
category: RadPhy
---

Table of Contents
=================

# Material Irradiation
    
## Elementary Displacement Theory

Damage rate equation or the rate of displacement is given by:

$$ R_{d} = N \int_{\breve{E}}^{\hat{E}} \phi(E_{i}) \sigma_{D} (E_{i}) dE_{i} $$

where $$N$$ is the lattice atom density, $$\phi(E_{i})$$ is the energy dependent particle flux and typically has units of per $$\text{cm}^{2}$$ per second,
, $$\sigma(E_{i})$$ is the energy dependent cross section of the incident particle. 

From here, the displacement per atom (dpa) can be written in terms of the Damage rate,

$$ dpa = \frac{R_{d} t}{N} $$

The energy dependent displacement cross section can be fully defined as:

$$\sigma_{D} (E_{i}) = \int_{\breve{T}}^{\hat{T}} \sigma(E_{i},T) \nu(T) dT $$

where $$\sigma(E_{i}, T)$$ is the probability that a particle of energy $$E_{i}$$ will implant recoil energy $$T$$ to a struck lattice atom, and $$\nu(T)$$ is the number of displacement atoms of a collision resulting from a primary recoil atom of energy $$T$$ 

The simplified displacement probability for the simple case can can be approximated as a step function,

$$ P_{d} (T) = \begin{cases}

0 & T < E_{d} \\
1 & T > E_{d} 

\end{cases}

$$

However, a more realistic model can be modeled after, 

$$ P_{d} (T) \begin{cases}

=0 &  T < E_{d min} \\
=f(T) &  E_{d min} < T < E_{d max} \\
=1 &  T <E_{d max}

\end{cases}
$$

Displacement threshold energies ($$E_{d}$$) for different materials are as follows:

| Element | Cu | Al | Au | Pt | Ni | Fe | Mo |
|---------|----|----|----|----|----|----|----|
|$$E_{d}$$ ($$eV$$) | 22 | 16 | 36 | 37 | 24 | 24 | 37 |

since things need to be accounted for...

### Kinchin-Pease Damage Model

The following assumptions are made for the average number of displaced atoms initially created by a PKA of energy T:

+ The cascade is created at two body elastic collisions between atoms
+ Diplsacements occurs at $$P_{d} (T) = 1$$ for $$T \geq E_{d}$$ 

In accordance to the Kinchin-Pease Model, $$\nu (T)$$ is defined as,

$$ \nu (T) = \frac{T}{2 E_{d}}$$


## Point Defect Formation and Diffusion

### Frenkel Pairs

# Ion Beam Analysis 

## Rutherford Backscattering

Rutherford Backscattering Spectrometry (RBS) describes a technique commonly used for surface layer analysis of solids such as composition analysis, stoichiometry, and depth profiling for films less than 1 $$\mu$$m thin. 

Using high energy $$He^{2+}$$ ions or $$\alpha$$ particles beams up to 2 MeV, the energy of the recoiled ion at a given angle is measured.  Much like its namesake, RBS involves elastic hard sphere scattering using a high energy incident particles or beam (in this case, an ion beam).

The energy of the backscatted particle $$E_{1}$$ at a scattering angle $$\theta_{1}$$ relative to the observer is written in terms of the energy of the incident particle $$E_{0}$$ as:

$$E_{1} = k E_{0}$$

where $$k$$ is the kinematical factor, which can be expanded:

$$k = \bigg( \frac{m_{1} \cos(\theta_{1}) \pm \sqrt{m_{2}^{2} - m_{1}^{2} (\sin(\theta_{1})^{2}} }{ m_{1} + m_{2} } \bigg)^{2} $$

The probability of scattering is proportional to the atomic numbers of both the incident and target particle, written with a center-of-mass reference fram in mind:

$$\frac{d\omega}{d\Omega} = \bigg( \frac{Z_{1} Z_{2}}{4 E_{0}} \bigg)^{2}  \frac{1}{(\sin\theta/2)^{2}}$$

### Spectrum Analysis

Below is an example of an RBS spectrum comparing two Tantalum-Silicon (TaSi) thin films of different thickness at an ion beam of 2.2 MeV. As shown below, the peaks appear at a lower energy than the initial beam energy ($$E_0$$) as the backscatted ions lose energy as they scatter and travel through the sample. Note that the silicon peaks have been multiplied by 5 to distinguish its features. 

<img src='/assets/rbs_tasi.png' class='center'>

The tantalum peak appears at a much higher energy since it has a larger cross section than silicon. The leading edge of each energy peak corresponds to the backscattering of each element at the surface.  
 
Furthermore, the thickness of the TaSi sample can be measured via the width of the energy peaks. Dividing the energy width 

<img src='/assets/rbs_thick.png' class='center'>

The wider energy peak belongs to the thicker 590 nm sample since the backscattered ions have more material to travel through. 

The trailing edge of the energy peaks corresponds to scattering at the interface of the Ta. The 230 nm layer film has an energy of ~1.9 MeV while the 590 nm layer has an energy of ~1.5 MeV.

## Faraday Cups

<img src='/assets/faradaycup.png' class='center'>

Faraday cups are charge particle detectors are typically used to tune ion beams. In the figure above, ions enters the Faraday cup, a current $$I$$ is induced as ions neutralize on the metal cup. By measuring this charge $$I$$, the number of charges carried by the ions in vaccuum can be calculated as: 

$$\frac{N}{t} = \frac{I}{e}$$



### Sputtering

<img src="/assets/sputtering.png" class="center">

# References

[1] [Mayer RBS Lecture](http://users.ictp.it/~pub_off/lectures/lns022/Mayer_1/Mayer_1.pdf)

[2] [EAG RBS](https://www.eag.com/resources/tutorials/rbs-tutorial-theory/)

[3] [Chem Libretexts](https://chem.libretexts.org/Bookshelves/Analytical_Chemistry/Physical_Methods_in_Chemistry_and_Nano_Science_(Barron)/01%3A_El

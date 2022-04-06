---
layout: notes
title: Radiation & Nuclear Physics 
category: RadPhy
---

Table of Contents
=================

# Material Irradiation
    
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

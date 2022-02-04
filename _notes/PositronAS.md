---
layout: notes
title: Positron Annihilation Spectroscopy 
category: notes 
---

The focus of these notes is to provide a comprehensive summary on positron annihilation spectroscopy and its applications as well as concepts that are important to PAS. 

# The What and Why of Positrons?

## Introduction

A non-destructive technique called Positron Annihilation Spectroscopy (PAS) can provide information regarding a solid material:

+ Variations in density
+ Defects
+ Displacements
+ Voids
+ Size
+ Concentration
+ Chemical Environment

In the context of Fundamental Understanding of Transport Under Reactor Extremes (FUTURE), a LANL research center, the application is to better understand materials properties when exposed to radiation damage, corrosive enviroments, high stresses and high temperatures which plays a role in nuclear energy research.  

The principle behind PAS hinges on the fact that solids such as metals and semiconductors contain free electrons that can annihilate with positrons. This interaction produces gamma rays which can be detected to measure the positron lifetime from its emmision to detection. Below is a figure describing positron annihilation spectroscopy:

<img src="/assets/pastheory.png" class="center">

Moreover, positrons can be trapped within defects or vacancies. With a diffusion length of 100nm, the positron then loses its kinetic energy as it travels through the lattice through a process called [thermalization](https://en.wikipedia.org/wiki/Thermalisation). As a result of the repulsive forces from neighboring positively charged nuclei, the positron is trapped in a region of lesser local electron density or where an atom is missing from the lattice. 

Below is a comparison of techniques for resolved defect size.
<img src="/assets/defecttechniques.png" class="center">

Below (Fig 1.) is a Feynmann Diagram of $$ e^{+} , e^{-} $$ annihilation emitting a photon. These interactions typically radiate two (three?)(para and ortho positronium?) photons. 

<img src="/assets/e_diagram.png" class="center">

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

# Gamma Annihilation Spectrum

In gamma radiation spectroscopy, the spectrum is a result of two back to back emissions of gamma photons for a given radioactive source. Much like optical spectroscopy, the spectrum has identifiable peaks (or lines) that can be used for determining the detector resolution and calibration.

$$ 
\begin{array}
\hline
{Isotope}        & {Barium-133} & {Cobalt-60} & {Sodium-22} & {Cesium-137} \\ \hline
{Energies (keV)} & {80.997}     & {1173.228}  & {511}       & {661.657}    \\ \hline
& {160.612}    & {1332.492}  & {1274.537}  & {} \\ \hline
& {383.849}    & {}          & {}          & {} \\ \hline
& 437.012                         &                                &                                &  
\end{array}
$$

An example of a full gamma spectrum with the sources listed in the table above is shown below:

<img src='/assets/fullspec.png' class='center'>

Consider Na$$^{22}$$, a radioactive isotope with a half-life of 2.6 years. 


For a Na$$_{22}$$ source, there is a characteristic $$511$$ keV peak. 

# Positron Annihilation Lifetime Spectroscopy

In the introduction, positrons lose kinetic energy through the ionization process. A typical interaction in PALS positron production and annihilation is:

$$ e^{+} + e^{-} \rightarrow 2\gamma $$

During measurement the lifetime of the positron is taken as the time of photon detection to the time of the "stop photon" or signal. The spectra is typically deconvoluted to into it's several exponential components, and fitted to some time constant denoted by $$ \tau_{i}$$

Positron lifetime is a function of electron density at the annihilation site. The equation below describes the measured lifetime spectrum as the sum of components correspoding to each annihilation site: 

  $$ N(t) = \sum_{i = 1}^{k+1} \frac{I_{i}}{\tau_{i}} e^{- t/ \tau_{i}}$$

where $$ tau $$ is the lifetime and $$ I $$ is the intensity of the $$i$$-th component in the spectrum. 

More explicitly, the positron lifetime spectra follows an exponential decay. The theoretical contributions (representing ideal scenarios) is given by:

$$ C_{theory} (t) = \Delta t \bigg[ C_{tot} \sum_{i} \frac{I_{i}}{\tau_{i}} e^{-t / \tau} \bigg] = \Delta t \bigg[ C_{tot} \sum_{i} \lambda_{i} I_{i} e^{-\lambda_{i} t + B }\bigg]$$

where $$ C_{tot} = \int_{0}^{\infty} C(t) dt $$ such that $$ \sum_{i} I_{i} = 1 $$. However, in order to correct for experimental spectra, contributions from the $$e^{+}$$ source (source correction) and background signals from random start-stop coincidences need to be taken into account.

The lambda term is simply the recipricol of the time constant, expanded below for completeness:

$$ \lambda = \frac{1}{\tau} = \pi r_{o} c^{2} \int |\psi (r) |^{2} n(r) \gamma dr  $$
  
where $$r_{o}$$ is the electron radius, $$c$$ is the speed of light, $$ r $$ is the position vector, $$ \| \psi (r) \|^{2}$$ is the positron probability density, $$ n(r) $$ is the electron density, and $$ \gamma $$ is an enchancement factor related to the coulombic interactions between positrons and electrons in a local electron density. 

All together, the total number of positron annihilations registered (in a multichannel analyzer) is:

$$ C_{exp} (t) = \int_{-\infty}^{\infty} \big[ C_{theory} (\tau) + C_{source} (\tau)  \big] f_{res} (t - \tau) d\tau + C_{bg} $$ 

where $$ C_{bg} $$ represents the background contributions and $$f_{res} $$ is the time resolution function, for cases where the "start" and "stop" photon enter simultaneously. 

# Doppler Broadening Techniques

[See page on DB Spectra software]()

## Doppler Broadening of Annihilation Radiation (DBAR) 

In spectroscopy, the spectral line are broadened due to the distribution of velocities of atoms. This phenomenon is called Dopper broadening. When annihilating, the $$ e^{+} e^{-} $$ pair decays into two $$ \gamma $$-rays, with shifts in the photon energy $$ mc^{2} = 511 keV $$. Using energy and momentum conservation:

$$ E_{2} = c p_{2} \approx mc^{2} - \frac{E_{b}}{2} + \frac{cp_{z}}{2} $$ 



Doppler Broadening spectroscopy peaks are characterized by $$ S $$ and $$ W $$ parameters. The $$\gamma$$-ray spectrum contains the sum total of the contributions from annihilations with different electron states. The shape of the spectrum correspond to the electron momentum distribution during annihilations. Delocalized, weakly bound valence electrons contribute to low momentum distributions, whereas tightly bound core electrons contribute to high momentum distributions. 


<img src="/assets/SWparam.png" class="center" >
The typical values for defect parameters are: 

A: $$ 511.8 \text{keV} \geq A \geq 510.2 \text{keV} $$ 

C: $$509.3 \text{keV} \geq C \geq 507.8 \text{keV} \cup 514.8\text{keV} \geq C \geq 512.7 \text{keV}$$ 


Here in the spectrum, the $$ S $$ parameter shows the annihilation fraction with the _low momentum_ electrons and the $$ W $$ parameter is the the annihilation fraction with the _high momentum_ with the core electrons. Therefore, the $$ S $$ parameter is proportional to the defect content in the lattice since positrons are more likely to annihilate with valence electrons at the defect site. 



## Coincidence Doppler Broadening Spectroscopy

<img src="/assets/cdbs.png" style="width: 70%; height: 70%" class="center">


In traditional DBS, the line-shape variations of the spectrum for high momentum core electrons are not easily measured. To alleviate this, a coincidence measurement of $$ \gamma $$-ray energies using two detectors improves the signal to background ratio ([up to four orders of magnitude](https://journals.aps.org/prb/pdf/10.1103/PhysRevB.61.10092)). 

In modern detectors, the two photons radiated are detected within a 100ns time window. The two dimensional spectrum is transformed to a one dimension. From here, the $$z$$ component of the $$e^{+}$$ $$e^{-}$$ annihilation pair is calculated as the difference in energy of the two photons. We can express the spherically symmetric CDB spectrum as:

$$ C(\Delta) \propto \int n(\vec{p}) \delta(\Delta - cp_{z}) d^{3} p $$

where $$ \Delta = E_{1} - E_{2} = c p_{z}$$, with $$ p_{z}$$ being the momentum $$z$$ component. 

## Slow Positrons

Two common mechanisms produce positrons, radioactive decay and pair production. As a result, positrons are produced with a wide energy spectrum and are not "fine tuned". Such positrons can only be used for bulk studies. 

For the purposes of performing depth-resolved (monitoring defects as a function of depth) studies on surfaces, interfaces, thin films, and defects induced by ion irradiation, we require tunable monoenergetic slow positron beams via moderation. (see [Positron Source Moderation](#positron-source-moderation) section)

### (Makhovian) Implantation Profile


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

## Positron Source Moderation

<img src='/assets/Moderation.png' class='center'> The figure above shows the positron emission spectrum of an $$ ^{22}Na $$ source. $$ dN_{+}/dE $$ is the number of positrons per energy channel. The energy distribution is centered at $$3eV$$ after moderation in tungsten. 

A thin moderator foil with a high atomic number is placed on top of the source capsule. High atomic numbers are favorable since it is proportional to the ratio of the mean diffusion length to the thermalization distance (the larger, the better). Typically, the foil (maybe tungsten) is about a few $$\mu m$$ thick, much smaller than the mean penetration depth, such that only a small fraction of positrons thermalize and diffuses in the foil.  

<img src='/assets/moderationtrans.png' class='center'>
This figure shows the fraction of positrons that leave the moderation foil. "If the surface is reached during diffusion, the positrons are spontaneously emitted from the moderator foil with a kinetic energy equal to the thermally bordened work function, $$ \Phi_{+} $$." 

Although the fraction of slow positrons is much smaller than fast positrons, a guidance system further down the beam line is used to separate the unmoderated positrons.

# Pulse Positron Beamline

## Beam Bunching

The buncher is comprised of three stages, the prebuncher, the chopper, and the main buncher. Cylindrical electrodes inside the buncher hold a static potentials and are connected to a grounding bar through $$0.1 \mu F$$ capacitors, doing so minimizes heating of the beam and amplitude of the RF pickup on the electrodes.

The prebuncher and chopper RF electrodes are driven at potentials of $$\|V \| < \pm 30 V $$ with an arbitrary wave generator (AWG), and operate at about $$ 40 MHz$$. Channel 1 of the AWG is amplified 

## Target Chamber

For implantation energies between $$ 10 $$ keV - $$ 30 $$ keV, an Fe target will backscatter about $$15\%$$ of the incident positrons. The fraction of backscattered positrons will increase with atomic number $$Z$$, for example Au$$^{35-37}$$ will backscatter about $$40\%$$ of the incident positrons.

# HPGe Doppler Broadening Spectrometer Experimental Setup

## HPGe Detector Apparatus

Germanium detectors provide the highest gamma ray energy resolution. For this particular setup  the FWHM is documented at $$\leq 1.8 keV$$  

Two standard coaxial high purity germanium detectors manufactured by Mirion Technologies (formerly Canberra) are used to detect gamma radiation. Contained in metal casing, the semiconductor is made of an $$0.5 mm$$ thick n-type diffused lithium contact and the p-type contact is $$0.3\mu m$$ thick well. 

"The germanium has a net impurity of about $$10^{10}$$ atoms/cc so that with moderate reverse bias, the entire volume between electrodes is depleted, and the electric field extends across this active region".


To prevent impurities from forming, the germanium detectors are attached to 8-liter Dewar flasks filled with liquid nitrogen. During high voltage operations, the liquid nitrogen prevents excessive thermally generated leakage current. 

- Lower discriminator level must be in between the [Compton edge](https://en.wikipedia.org/wiki/Compton_edge) and annihilation peak

- The upper discriminator level is set to be symmetrical to the lower level with respect to the photopeak.

- After setting the discriminator levels, acquire individual energy spectra from every analyzer in PHA mode

### Lynx Multichannel Analyzers (MCA)

Produced by Canberra, the (each?) digital MCA supports a maximum of 32678 analyzer bins. Two power supplies are built into the MCAs, the low energy power supply proivdes a range between $$-200V$$ to $$+200V$$. A high voltage power supply provides $$200V$$ to $$5000V$$ with $$\pm$$ polarity. The MCAs were built to support different experimental setups such as x-ray and alpha spectroscopies, however, for the purposes of doppler broadening spectroscopies, the two acquisition modes are listed below:

+ Pulse Height Analysis (PHA): This mode is used for single detector acquisition and builds a cumalative spectrum of counts binned over time. 

+ Time-Stamped List Mode (TLIST): This is used for coincidence experiments for two-dimensional energy spectrum. Based on the MCA's timing resolution (with a maximum of $$100ns$$), each coicidence event is stored with a corresponding energy and timestamp.  

### Detector deadtime


HPGe detectors have a relatively poor timing resolution compared to other detectors, for reference, $$BaF2_{2}$$ scintillation detectors have a timing resolution of $$20\mu s$$.

## Coincidence Mode vs Single Detector Setup

To monitor coincidence count rate, the two single channel analyzers are connected to an ORTEC 414A Fast Coincidence unit, with an coincidence window set to the maximum, $$110ns$$ or the maximum timing resolution of the Lynx MCAs. With a BNC splitter, the unit is connected to a signal counter displaying coincidence events.

## Tao-Eldrup Model

-To be added

# References

[1] [F.A.Selim, Positron annihilation spectroscopy of defects in nuclear and irradiated materials- a review](https://www.sciencedirect.com/science/article/pii/S1044580321000826#bb0215)

[2] [R. W Siegel Positron Annihilation Spectroscopy](https://www.annualreviews.org/doi/pdf/10.1146/annurev.ms.10.080180.002141) 

[3] [P. Stepanov, New developments in positron annihilation spectroscopy techniques: from experimental setups to advanced processing software](https://petrstepanov.com/static/petr-stepanov-dissertation-bgsu-2020.pdf)

[4] [Slow Positron Beam Techniques](http://www.positronannihilation.net/index_files/Positron%20Beam.pdf)

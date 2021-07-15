---
layout: notes
title: DUNE & Neutrinos
category: DUNE
---

Some of the notes and talking points for my presentation on DUNE.

## Introduction to DUNE

The Deep Underground Neutrino observatory (DUNE) comes packaged with a couple of facilities. The main ones being: FermiLab (FNAL), the Sanford Underground Research Facility (SURF), and the Long Baseline Neutrino Facility (LBNL). 

The experiment begins at PIP-II, Fermilab's linear accelerator. A mega-watt (up to 1.2 MW) class proton beam is produced, moving the protons through a series of boosters at 8 GeV where they reach the main injector at 120 GeV, eventually accelerated close to c. 

The main injector ring smashes the protons into a fixed 1.5m target, producing Pions and Kaons. Focusing horns along the injector can be switched to focus Pions and Kaons of the opposite charge to produce a beam of antineutrinos. 

Thereby producing a high intensity beam of neutrinos and anti neutrinos of the muon flavor

## Physics of DUNE (Far Detector at least)
Experimental measurements were made by the Super Kamiokande Observatory (Super-K) in 1998 and the Sudbury Neutrino Observatory (SNO) in 2001. The 2015 Nobel Prize for "the discovery of neutrino oscillations, which shows that neutrinos have mass" was awarded to Takaaki Kajita and Arthur B. McDonald. The theoretical prediction was provided by Bruno Pontecorvo way back in 1957.

Recall that neutrinos only interact via the standard model charged current and neutral current weak interactions. Charged current refers to an interaction where a charged weak force carrier \\((W^+ \\) or \\(W^-)\\) are exchanged. Whereas neutral current refers to interactions with a neutrally charged weak force carrier $$(Z^{0})$$.

We look at the matrix that describes the mixing between mass and weak eigenstates of the neutrino, the Pontecorvo-Maki-Nakagawa-Sakata (PMNS) Matrix:
$$ \begin{pmatrix}
\nu_{e}\\ 
\nu_{\mu}\\ 
\nu_{\tau}
\end{pmatrix}=
\begin{pmatrix}
U_{e1} & U_{e2} & U_{e3}\\ 
U_{e1} & U_{e2} & U_{e3}\\ 
U_{e1} & U_{e2} & U_{e3}
\end{pmatrix}\begin{pmatrix}
\nu_{1}\\ 
\nu_{2}\\ 
\nu_{3}
\end{pmatrix}$$

## Neutrino Oscillations
Consider two weak flavor eigenstates, defined as $$\nu_{1}$$ and $$\nu_{2}$$ with masses $$m_{1}$$ and $$m_{2}$$. 


The probability of Oscillation is given by:
$$P_{Oscillation} (\nu_{\mu} \rightarrow \nu_{e}) = \left |  \left \langle \nu_{e} | \nu_{\mu} (t) \right \rangle\right |^{2} = \sin^{2} 2\theta_{12} \sin^{2} ( 1.27 \Delta m^{2}_{21} \frac{L}{E})$$

where $$\theta$$ is the magnitude of oscillation, $$\Delta m^{2}$$ is the period, $$L$$ is the distance from the source to the detector and $$E$$ is the neutrino energy.

## DUNE DAQ

### The WIB
The heart of of the DUNE data acquisition infastructure is the Warm Interface Board (WIB), which is responsible for controlling and configuring the front end electronics (namely the FEMB, mo re on that in a bit) and transfers massive amounts of data (over 40Gb/s!) via optical links to the data acquisition system. Eventually, the WIBs will be installed in a Warm Interface Electronics Crate (WIEC), each crate containing four WIBs.

Designed around a Xilinx Zynq Ultrascale+ FPGA, this allows for programmable logic gates and processing systems at a lower level than a CPU which allows for rapid prototyping.

Connected to the WIB are front end electronics, otherwise knownas Front End MotherBoards (FEMB), that are dunked in Liquid Ar gon (LAr). Whenever an ionized electron from an interaction is produced the signal is passed through LAr Application Specific Integrated Circuits (ASICs) low noise amplifiers eventually making its way though another set of Analog to Digital Converter ( ADC) ASICs.

### The FELIX Board
Originally developed for the LHC ATLAS experiment, the FPGA based FELIX Board is a "Front Link eXchange" readout data acquisition board. 

Installed on a Wupper compatitable motherboard (Wupper is PCIe firmware designed to interface the Xilinx PCIe Gen3 hardblock via Direct Access Memory), the board communicates to the CPU via a PCI-E 16x slot.

The cmem_rcc driver allocates large buffers of contiguous memory.

The FELIX board can be configured to support two modes, GBT or FULL. 

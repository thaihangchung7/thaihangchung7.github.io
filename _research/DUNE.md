---
layout: notes
title: DUNE 
category: DUNE
---

Table of Contents
=================
   
   * [Introduction to DUNE](#introduction-to-dune)
   * [Physics of DUNE (Far Detector at least)](#physics-of-dune-far-detector-at-least)
      * [Neutrino Oscillations](#neutrino-oscillations)
      * [Proton Decay](#proton-decay)
   * [DUNE Data Aquisition](#dune-data-aquisition)
      * [Single-Phase Time Projection Chamber Technology](#single-phase-time-projection-chamber-technology)
      * [The WIB/WIEC](#the-wibwiec)
      * [The FELIX Board](#the-felix-board)
      * [Timing the Data](#timing-the-data)
      * [For Reference](#for-reference)
      * [TODO](#todo)

## Introduction to DUNE

<img src="/assets/DUNEwTPC.png" class="center">

The Deep Underground Neutrino Experiment (DUNE) is comprised of multiple facilities. The main ones being: FermiLab (FNAL), the Sanford Underground Research Facility (SURF), and the Long Baseline Neutrino Facility (LBNL). 

The experiment begins at PIP-II, Fermilab's linear accelerator. A mega-watt (up to 1.2 MW) class proton beam is produced, moving the protons through a series of boosters at 8 GeV where they reach the main injector at 60 GeV (120 GeV once the beam is fully commissioned), eventually accelerated close to c. 

The main injector ring smashes the protons into a fixed 1.5m target, producing Pions and Kaons. Focusing horns along the injector can be switched to focus the opposite charge of said particles to produce a beam of antineutrinos, thereby allowing physicists to study both modes.

Over at SURF, four fiducial tanks (a total of about 17,000 tons of LAr) chilled to about 300 degrees below 0F listen for particle interactions, 1.5km (a little less then 5,000 ft) below the surface.  

A near detector is located 574 meters from the target, 60 meters below the surface. Although it can append to the physics program of DUNE (boosted dark matter, sterile neutrinos, millicharged particles), it's mainly there to control for any biases in the energy scale or resolution, essentially to monitor the neutrino beam.

## Physics of DUNE (Far Detector at least)
Experimental measurements were made by the Super Kamiokande Observatory (Super-K) in 1998 and the Sudbury Neutrino Observatory (SNO) in 2001. The 2015 Nobel Prize for "the discovery of neutrino oscillations, which shows that neutrinos have mass" (or at least a upper limit was placed) was awarded to Takaaki Kajita and Arthur B. McDonald. The theoretical prediction was provided by Bruno Pontecorvo way back in 1957.

Recall that neutrinos only interact via the standard model charged current and neutral current weak interactions. Charged current refers to an interaction where a charged weak force carrier \\((W^+ \\) or \\(W^-)\\) are exchanged. Whereas neutral current refers to interactions with a neutrally charged weak force carrier $$(Z^{0})$$.

The Standard Model postulates three generations of neutrinos that oscillate between three neutrino mass eigenvalues. 

The Pontecorvo-Maki-Nakagawa-Sakata (PMNS) matrix describes the mixing between mass and weak eigenstates of the neutrino:

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
 

### Neutrino Oscillations
The harmonic oscillator introduced in first sememster quantum mechanics is a good analog for neutrino oscillations. Neutrinos interact via the Weak force and travel as a mixture of electron, muon and tau states.

Shown below are the decay of charged current bosons into neutrinos:

$$
W^{+}\rightarrow l^{+}+ \nu_{l} 
$$

Where $$l = e, \mu, \nu$$, the flavors of a neutrino.



Consider two weak flavor eigenstates, defined as $$\nu_{1}$$ and $$\nu_{2}$$ with masses $$m_{1}$$ and $$m_{2}$$. 

[insert example of two neutrinos mixing here]



In the context of long baseline physics, the probability of oscillation is given by:
$$P_{Oscillation} (\nu_{\mu} \rightarrow \nu_{e}) = \left |  \left \langle \nu_{e} | \nu_{\mu} (t) \right \rangle\right |^{2} = \sin^{2} 2\theta_{12} \sin^{2} ( 1.27 \Delta m^{2}_{21} \frac{L}{E})$$

where $$\theta$$ is the magnitude of oscillation, $$\Delta m^{2}$$ is the period, $$L$$ is the distance from the source to the detector and $$E$$ is the neutrino energy.

### Proton Decay
Since the detector is centered around liquid argon, one of the studies that comes for free is proton decay. It turns out liquid argon scintillation is particularly sensitive to certain $$K^+$$ modes favored by SUSY models. 

Here is a feynman diagram of an absurd interaction that is proposed in one of the many SUSY models.

<img src="/assets/ProtonDecay.png" class="center"> 

## DUNE Data Aquisition

### Single-Phase Time Projection Chamber Technology

<img src="/assets/protoDUNE_SPTPC.png" class="center"> 

So what happens when a high energy neutrino enters a tank? Suppose we had a neutrino interaction like the one shown in the Feynmann diagrams below:

<img src="/assets/nu_e_W.png" class="center">

The final state electron takes most of the transferred energy from the incoming neutrino. This ionizes the electrons in the neutrino path and the electrons drifts along an electric field, and collected by an APA. which provides the spatial reconstruction of the event in the drift coordinate or the horizontal and transverse direction) 

<img src="/assets/protoDUNE_trackreconstruction.png" class="center"> 

In addition to ionizied electrons, lined within the APAs, are PMTs which collects the scintillating photons produced by electrons that were bumped into a higher energy level. Or rather, when the electrons are on their way back to their ground state. This method of detection provides a time measurement from $$t_0$$.

### The WIB/WIEC
The heart of of the DUNE data acquisition infastructure is the Warm Interface Board (WIB), which acts as an interface from the front end electronics (FEMB) to the DAQ with shielding and real-time diagnostics. The WIB multiplexes data from  4 FEMBs with a payload of 3.6 GB/s per FEMB. 

The WIB communicates with the DAQ system via optical links. The WIBs are installed in a Warm Interface Electronics Crate (WIEC), each crate containing four WIBs. The ICEBERG teststand located at FermiLabs is currently using this setup.

<img src="/assets/WIEC.png" class="center">

Designed around a Xilinx Zynq Ultrascale+ FPGA, this provides programmable logic gates and processing systems at a lower level than a CPU which allows for rapid prototyping.

Connected to the WIB are front end electronics, otherwise known as Front End MotherBoards (FEMB), that are dunked in Liquid Argon (LAr). Whenever an ionized electron from an interaction is produced the signal is passed through LAr Application Specific Integrated Circuits (ASICs) low noise amplifiers eventually making its way though another set of Analog to Digital Converter (ADC) ASICs. 

The data collected is sent to the FELIX board which communicates with the host server via PCIe.  

### The FELIX Board

<img src="/assets/BNL712.png" class="center">

Originally developed for the LHC ATLAS experiment, the FPGA based FELIX Board is a "FrontEnd Link eXchange" readout data acquisition board. Installed on a Wupper compatitable motherboard, the board communicates to the host computer via a PCI-E 16x slot.

In the context of ProtoDUNE, each FELIX board is linked to one APA streaming 10x 1GB/s readouts. To put it simply the FELIX board acts as a data funnel.

The FELIX board can be configured to support two modes, GBT (Gigabit Transceiver) or FULL (full bandwidth). In the context of DUNE, the FELIX board will be operating in FULL mode which supports a line transmission rate of 9.6GB/s. Support for 48 channel optical links are enabled by the four MiniPOD Tx/Rx Transceiver pairs located on either side of the FPGA.

Using cmem_rcc, a driver from the ATLAS TDAQ project, allows the software to allocate buffers of contiguous memory. Low-level tools, namely ```fdaq```, receives data from FELIX and allows you to set the DMA memory buffer size on the host server. For certain test stands, like the one at UF, it is only possible to run ```fdaq``` in FULL mode for a couple seconds before it exceeds the maximum rate at which you can write to disc (or crash the host). For some perspective, a typical SSD's write to disc limit is about 300MB/s.

### Timing the Data

In order to accurately timestamp the particle physics data. All detector components are synchronized to a 62.5 MHz master clock with a precision of 1 ns. The timestamps come from a 1PPS GPS signal. As an example, to sample the analog digital converter signals on the FEMB, the master clock is divided by 32, and input data is converted every 500 ns. 

### For Reference

[ABC's of DUNE](https://abc.dunescience.org/) - DUNE List of Acronyms

[Introduction to Neutrino Physics](https://cds.cern.ch/record/677618/files/p115.pdf)

TTC: Timing Trigger Control

### TODO
-neutrinos are the only neutral fermions, it could be that they are their very own anti particles

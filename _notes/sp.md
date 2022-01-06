---
layout: notes
title: Signal Processing for DAQs
category: notes 
---

Front end data acquisition (DAQ) systems are first thing a physics interaction sees when encountering an experiment. The electronic components on different experiments come in varying forms, however, all DAQ systems share a common theme: Signal processing. Acquiring electrical signals, energy and timing measurements, signal-to-noise optimization, event rates, are some functions a DAQ is tasked with. To highlight some common features of the front end readout system of a detector, consider the figure below:

Incident radiation is collected by a sensor, converting the energy of a particle or a photon into an electrical signal. This signal generally comes in the form of a pulse. The signals collected are usually quite weak and is passed through a preamplifier to boost the signal with a high input impedance and a low output impedance, such that the signal-to-noise ratio (SNR) is preserved. 

The signal then makes it way through the main amplifier. Much like the preamplifier, the fidelity of the signal information is kept intact. While the main amplifier's duty is in the name, it serves another purpose. That is to shape the pulse into a form that can be used for further processing. In pulse shaping, the bandwidth of the system is controlled to improve the SNR, and by extension, setting the overall noise contribution of the system, also limiting the maximum signal rate.

Finally, this low level analog pulse fed into an Analog-to-Digital Converter (ADC), quantizing the signal. In other words, sampling continuous or varying signals into discrete packets in the form of a bit pattern. Once converted into a discrete-amplitude digital signal, the signal is set for storage, further processing, and eventually, data analysis.

## Units of a Signal Processing Chain

This section should provide a quick summary of common units throughout the signal processing chain. 

### Analog-to-Digital Converters
As stated before, ADCs samples continuous waveforms into discrete bit logic patterns that are unique to the input information. A simple ADC design is shown in Figure [pf].

[adc.png]

Through a series of voltage dividers, the input signal travels through a several comparators (a gate that compares voltages) with increasing threshold conditions. The encoder translates the output pattern of the comparators to provide a binary interpretation of the input signal.

### Discriminators
Discriminators are devices or circuits that trigger an output logic pulse when a certain threshold is reached. For the purposes of signal processing, discriminators fall into a few categories (see section on Timing Techniques), however, their common purpose is to decide if the input is interesting. 

### Time-to-Digital Converters
In the case of particle interactions or measurements, where events are few and far between (such as time-of-flight and lifetime measurements), Time-to-Digital Converters (TDC) are used to timestamp pulse data through some form of counter or clock. 

The simplest form of a TDC involves a counter that enumerates clock pulses with a start and stop signal. However, counters fall short on resolution ($$\approx$$ 1 ns) due to limitations on clock frequency \cite{spieler}.

High resolution digitization can be done using analog techniques, also known as ramp interpolation. Using a current source, $$I_{T}$$, time intervals are translated into voltages via a capacitor. Mathematically, 

$$ V = \frac{I_{T} (t_{stop} - t_{start})}{C} $$ 

Compared to the counter technique, ramp interpolation resolution is on the order of picoseconds. 

### (Pre)Amplifiers
Aptly named, amplifiers increase the power of an incident time varying signal. There are three three different basic types of amplifiers, or rather, amplifiers can operate in different mode based on the ratio of input resistance and source resistance.The time response of will affect the measured pulse shape, as a result, all amplifiers contribute to the pulse shape.

The input signal voltage for *voltage sensitive amplifiers* is 

$$V_{i} = \frac{R_{i}}{R_{s} + R_{i}}V_{s}. $$  

Input resistance $R_{i}$ needs to much larger than the source impedance. When acting as an integrator, the capacitance of the detector and any input capacitance must be summed over (see section on Integrating Circuits).

*Current sensitive amplifiers* are another mode of amplifier operation and and are commonly used in timing applications, where the signal is fed into a discriminator. The input current $$i_{s}$$ is given by

$$ i_{i} = \frac{R_{s}}{R_{s} + R_{i} i_{s}}.$$ 

Inverting the conditions for a voltage sensitive configuration, the input resistance needs to be much smaller than the source impedance. 

Last but not least are *charge sensitive amplifiers* which integrates charge on a feedback capacitor and can be used to control gain and input resistances. These find uses in energy spectroscopy where charge and time of an event is of interest.

### The NIM Standard
The Nuclear Instrumentation Module (NIM) standard refers to the set of application specific electronic modules (Figure \ref{nimmodules}) that sit in standardized bins (Figure \ref{nimbin}). Each of these modules can be purposed with implementing basic logic operations, take the role of an amplifier or discriminator, and any of the other signal processing components. The back of each module are standardized by the Department of Energy \cite{wikipedia_2021}. The advantage is in the idea a modular system where electronic instrumentation can be interchange for rapid prototyping or updating the electronic design.

### Signal Acquisition

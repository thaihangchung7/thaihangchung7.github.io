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

### Constant Fraction Discriminators

An alternative and more efficient method of dealing with amplitude variations is constant fraction triggering. The idea is to find the maximum of the pulse using the point at which the slope is $$0$$. The pulse is divided into the components, delay time ($$t_{d}$$) and rise time ($$t_{r}$$) and a comparator is used to determine which voltage is let through.

Consider a pulse with linear leading edge with conditions regarding the rise time $$t_{r}$$. For $$t \leq t_{r}$$,

\begin{equation}
    V(t) = \frac{t}{t_{r}},  
\end{equation}

The signal at the comparator input is

\begin{equation}
    V(t) = \frac{t-t_{d}}{t_{r}} V_{0}
\end{equation}

It can be shown that when the signal crosses the threshold $$t>t_{r}$$, where $$V(t) = V_{0}$$, the time at which the comparator gives an output signal is

\begin{equation}
    t = f_{a} t_{r} + t_{d}
\end{equation}

provided that $$t_{d} > t_{r}$$. From here the constant fraction $$f_{a}$$ independent of the peak amplitude is obtained. Note that $$f_{a}$$ is the attenuation factor of a the input signal, $$\textit{not}$$ a frequency.

Moreover, reducing the delay time such that $$t_{d} < (1-f_{a}) t_{r}$$, produces an equation that is independent of both the amplitude and rise time,

\begin{equation}
    t = \frac{t_{d}}{1-f}
\end{equation}

where $$t_{d} = t_{r} (1-f_{a})$$. Relating this back to the trigger voltage, the maximum threshold signal $$V_{T} = f_{a} V_{0}$$ In other words, signal that passes through and attenuated by the factor $$f_{a}$$ of the original amplitude.

Simply put, constant fraction discriminators elimate timing jitter. An incoming pulse is split into two pulses $$A$$ and $$B$$. Suppose there are resistances in the two wires, making pulse $$A$$ larger than pulse $$B$$. Pulse $$A$$'s wire is extended so that it lags behind pulse $$B$$, meanwhile, pulse $$B$$ is inverted, giving a positive pulse. When these two pulses are added together, a bipolar pulse is created such that there is a zero crossing. This zero crossing point is independent of the pulse amplitude and (timing jitter)?

### The NIM Standard
The Nuclear Instrumentation Module (NIM) standard refers to the set of application specific electronic modules (Figure \ref{nimmodules}) that sit in standardized bins (Figure \ref{nimbin}). Each of these modules can be purposed with implementing basic logic operations, take the role of an amplifier or discriminator, and any of the other signal processing components. The back of each module are standardized by the Department of Energy \cite{wikipedia_2021}. The advantage is in the idea a modular system where electronic instrumentation can be interchange for rapid prototyping or updating the electronic design.

### Signal Acquisition


# Bit-Operations and Registers

For reference, here a truth table containing bitwise operations for AND, OR, NAND, NOR, XOR, Conditionals,and Biconditionals.

$$
\begin{array}[]
\hline
P & Q & AND & OR & NAND & NOR & XOR & Conditional & Biconditional \\ \hline
1 & 1 & 1   & 1  & 0    & 0   & 0   &             &               \\ \hline
1 & 0 & 0   & 1  & 1    & 0   & 1   &             &               \\ \hline
0 & 1 & 0   & 1  & 1    & 0   & 1   &             &               \\ \hline
0 & 0 & 0   & 0  & 1    & 1   & 0   &             &               \\ \hline
\end{array}
$$

Given $$P$$ and $$Q$$ inputs, the outputs are as follows:

+ AND: the output is true iff both inputs are true
+ OR: the output is true any of the two inputs are true
+ NAND/NOR: Negates AND/OR respectively
+ XOR: the output is true if exactly *one* input (but not both) is true 

## Binary and Bit-wise operations

In order to indicate to the compiler to evaluate a binary number, the number prefixed with $$0b$$. For instance, the number $$10$$ in 8-bit binary can be written as:

$$0b00001010$$

One can "flip" a bit by applying/masking the binary with another by referring to the truth table above. For instance an AND operation on an 8-bit binary would look like:

$$0b00001010$$ AND $$0b00000010$$ = $$0b00000010$$ 

An OR operation:

$$0b00001010$$ OR $$0b00000100$$ = $$0b00001110$$

The NOT operator, usually denoted by a ~ preceeding the binary number, can be applied to flip each bit to its opposite value:

$$0b1010$$

$$\tilde{}0b0101$$



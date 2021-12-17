---
layout: notes
title: Signal Processing for DAQs
category: notes 
---

Data acquisition systems (DAQ) are integral to any front-end data acquisition system. The electronic components on different experiments can take varying forms. However, all these DAQ devices share a common theme: Signal processing. Acquiring electrical signals, energy and timing measurements, signal-to-noise optimization, event rates, are some functions a DAQ is tasked with. 





# Pulse Signal in Nuclear Electronics

Before processing a signal, it is important to introduce some terminology that characterizes a pulse signal. Suppose we have an square pulse as shown in the figure below.

<img src="/assets/pulse.png" class="center"> 

Beginning with the **baseline**, this is the "null" or "ground state" of the pulse. In the figure it is shown as zero, but this can vary due to pulse shape or count rate. The **pulse height** is taken as the instantaneous maximum of the pulse signal, measured from the baseline. The **pulse width** is measured as the full width half max (FWHM), which defines the bandwidth of the signal. The **leading** and **falling edge** corresponds to the section of the pulse seen at $$t_{0}$$ and when the full pulse as passed, respectively. The **rise time** ($$t_{r}$$) refers to the section the signal rises from $$10\%$$ to $$90\%$$ of the max amplitude. Similarly, **fall time** is the section of the pulse that drops from $$90\%$$ to $$10\%$$ of the pulse height. 

Pulse sigals can also be categorized into **unipolar** or **bipolar**. The former describes a pulse that occurs on one side of the baseline and the latter describes a signal that continues onto the other side of the baseline. 

# Analogue vs Digital Signal Processing

# NIM Standard

# Discrete Fourier Transforms

# Z-Transforms

# References

---
layout: notes
title: DB Spectra Analysis 
category: notes 
---

Some notes regarding the setup and operation of Doppler Broadening Spectroscopy software

# ProSpect

ProSpect is the data acquisition software used to collect the energy spectra via the Lynx Multi Channel Analyzers (MCA) for doppler broadening experiments. 

## Establishing a Connection to the Lynx MCAs

1) Click on 'Connect to Device' on the bottom bar

2) In the window that pops up, select or type the local IP address of **ONE** MCA device. Then, check the 'Take Over' box and click connect.  

*Note*: This field may be autofilled with both the IP address and a port number or a name following the address, however, the IP address should be sufficent to connect the devices. 

3) Repeat step two to connect the second MCA device.

4) Click on the 'Datasources' tab at the bottom of the window. Both HPGe Detectors should be labeled along with their IP addresses with empty spectrum graphs. A blue background (of the window (not an actual spectrum) should indicates that both analyzers are connected. 

5) If there is an error (indicated by an orange background), SHIFT + doubleclick on the yellow circle at the top left will prompt you to clear the device fault. Select 'Yes' and check if the error persists.

## Ramping Voltage

The detector preamplifiers need to operate at $$4400 V$$ the software will *automatically* ramp the voltage, the reading voltage should reach ~$$4000 V$$, this is when the detectors reach operational status.



## SW-Calculator
- Need to install Root

- '''source ./thisroot.sh'''

- run make in sw-calculator directory

- make install?

## Obtaining Doppler Broadening Spectrum from PHA 

See python script for plotting from CSV file (link repo here) 

# References

[1] [F.A.Selim, Positron annihilation spectroscopy of defects in nuclear and irradiated materials- a review](https://www.sciencedirect.com/science/article/pii/S1044580321000826#bb0215)

[2] [R. W Siegel Positron Annihilation Spectroscopy](https://www.annualreviews.org/doi/pdf/10.1146/annurev.ms.10.080180.002141) 

[3] [P. Stepanov, New developments in positron annihilation spectroscopy techniques: from experimental setups to advanced processing software](https://petrstepanov.com/static/petr-stepanov-dissertation-bgsu-2020.pdf)

[4] [Slow Positron Beam Techniques](http://www.positronannihilation.net/index_files/Positron%20Beam.pdf)

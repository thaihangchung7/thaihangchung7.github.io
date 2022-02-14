---
layout: notes
title: VEPFIT 
category: notes 
---

# Pre-Requisites

The data analysis software (VEPFIT) can only run on Windows 98 for now. Rather than installing the ancient OS on your drive, we get around this through [Virtual Box](https://www.virtualbox.org/).

# Readable File Formats

- Set VirtualBox Network setting to "Bridged Adapter"

# Transferring Data Between VM and Host 

## Creating the Virtual Hard Disk

1) In VirtualBox, create a new virtual hard disk (vhd), don't make it too large, I found that 100mb works. 

<img src="/assets/createvhd.png" class="center">

2) In the Windows 98 VM, open up the MS-DOS prompt and type ```fdisk```.

2.5) If you are asked to enable large disk support, just enter yes.

3) Select option 5 in the "Change current fixed disk drive".

<img src="/assets/fdisk5.png" class="center">

4) You will be prompted to "Enter a fixed drive number". The vhd will not display exactly 100mb (maybe 91mb). Hit enter.

5) With the vhd selected, create an extended DOS partition (option 2).

<img src="/assets/extdos.png" class="center">

6) When you get to the screen below, just verify that the maximum space to allocate is 100%. Hit enter.

<img src="/assets/createdvhddos.png" class="center">

7) The file explorer in Windows 98 should display a "D:" drive now (if you don't see this, restart the VM). However, you need to format this D: drive in order to use it.

8) Open up the MS-DOS prompt again and type ```format d:```

## Moving the VHD to host machine

9) Copy any files or data you need to transfer into the D: drive and **MAKE SURE YOU SHUT THE VM OFF BEFORE TRANSFERING**.

10) Locate the .vhd (usually in the same folder as the Win98 .vhd, or where ever you specified in step 1). You can view the contents and extract them using 7zip.  


# References

[1] [Analysis of positron profiling data by means of ‘‘VEPFIT’’](https://aip.scitation.org/doi/pdf/10.1063/1.40182) 

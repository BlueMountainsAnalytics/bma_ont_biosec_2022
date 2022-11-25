# Overview

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](index.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](VM.md)

This course is intended to give an overview and good working knowledge for anyone who wants to get into bioinformatics for long-read sequencing data analysis. As an introduction it won't cover advanced tool use or workflows.It will introduce the main steps and standard tools used for long-read data analysis and raise awareness for potential problems and pitfalls.

The general workflow of long-read whole genome sequence analysis can sometimes be iterative, i.e., the assembly process may have to be repeated using different assemblers to find the best possible genome assembly. 

<center>
<img src="figures/WF.png" width="500px">
</center>


## Course environments

Bioinformatics is mostly done using a *command-line interface*on on linux-based systems, e.g., Ubuntu Linux and MACOS. Windows users have several possibilities to set-up a linux-like system, eg., the *Windows Sub-system for Linux* provided on current Windows versions. However, in this course we will use a *virtual machine* with Ubuntu installed in it which will provide a linux standardised linux system for all users. 

### Windows users

To use the virtual machine image you will have to install [VirtualBox](https://virtualbox.org), which requires administrator rights. For installation instructions please see the [VirtualBox Installation](VM.md) page.


### Linux / MACOS (Intel) users

Linux users and MACOS users (Intel based processors) can choose to use their pre-installed *terminal* apps. Please see [Course data and resources](DATA.md) for a list of tools, dependencies, and data needed for this tutorial.

### MACOS users (M1/M2/ARM)

New Mac computers with the M1/M2 chips are not supported for this tutorial. The main reason being that many of the bioinformatics packages are not yet available for these architectures on package manager Conda (Mamba) and have to be compiled manually. Additionally, some tools don't support these architectures yet at all. 


## Tools, dependencies and course data

A complete list of the tools, dependencies, and links to the data and conda environment files can be found [here](TOOLS.md)

<p align="right"><a href="https://bluemountainsanalytics.github.io/BMA_CLI-tutorial/VM.html">CONTINUE -></a>
</p>

~                                                                                                                                                                                              
~                                                                                                                                                                                              
~                                                                                                                                                                                              
~                                                                                                                                                                                              
~                             

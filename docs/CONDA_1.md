# Package Managers Conda and Mamba

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](INTRO_4.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](CONDA_2.md)

## An Introduction to Package Managers

Installing new apps/softwares and all the things required, the *dependencies*, on a GUI such as Windows requires only a double-click on the installer program.

On the command-line, it usually requires several commands to install a new tool and, in contrast GUI installers, often the dependencies for a tools will have to be manually installed before the installation of the tool that needs them. To further complicate the installation on the command-line, the dependencies of some tools may conflict with other tools. For example, if tool A requires the programming language Python version 2.2 but another program, tool B, requires Python version 3.3 as dependencies then the user will first find a solution for the conflicting dependencies before tools A and B can both be installed on the system.

**Package Managers** are collections of scripts and programs that helps users to decomplicate the installation of tools on the command-line and manage their dependencies. Most linux distributions come with their own package managers installed, e.g. aptitude for Ubuntu and zypper for Suse. A very popular *cross-platform* pacakge manager, i.e., it can be used on most/all computer "platforms", is the package manager **Conda**. Conda provides not only a user-friendly way of installing tools and packages including it's dependencies but creates so called *environments* in which the packages are installed into minimising the potential for conflicts between packages. 

<p align="right"><a href="https://bluemountainsanalytics.github.io/BMA_CLI-tutorial/CONDA_2.html">CONTINUE -></a>
</p>

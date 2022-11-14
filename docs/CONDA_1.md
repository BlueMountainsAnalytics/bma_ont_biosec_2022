# Package Managers Conda and Mamba

## An Introduction to Package Managers

Installing new apps/softwares and all the things required, the *dependencies*, on a GUI such as Windows requires only a double-click on the installer program.

On the command-line, it usually requires several commands to install a new tool and, in contrast GUI installers, often the dependencies for a tools will have to be manually installed before the installation of the tool that needs them. To further complicate the installation on the command-line, the dependencies of some tools may conflict with other tools. For example, if tool A requires the programming language Python version 2.2 but another program, tool B, requires Python version 3.3 as dependencies then the user will first find a solution for the conflicting dependencies before tools A and B can both be installed on the system.

**Package Managers** are collections of scripts and programs that helps users to decomplicate the installation of tools on the command-line and manage their dependencies. Most linux distributions come with their own package managers installed, e.g. aptitude for Ubuntu and zypper for Suse. A very popular *cross-platform* pacakge manager, i.e., it can be used on most/all computer "platforms", is the package manager **Conda**.

## Introduction to Conda

Conda is a package manager that automates the installation of scripts, pacakges and dependencies in a user-friendly way. Conda uses *environments* that are independent from each other and don't interact with other Conda environments and thus limiting the possibility of dependency conlficts.

A usual conda installation works as follows:
  <ul>
    <li>Create a new conda environment</li>
    <li>Activate the new environment</li>
    <li>Install tools, packages, and dependencies</li>
    <li>Use the tools installed in the environment</li>
    <li>De-activate the environment<li>
  </ul>

Once a conda environment is created you can activate or de-activate the environment as many times as you want, the tools etc installed inside the environment won't disappear, e.g., when you re-start the computer or log out. 

### Installing Conda

For this tutorials, Conda is already installed on the AWS instances. You can confirm this either with the **which** command from the CLI tutorial to see where conda is installed, or you can check it by asking conda for the version installed on your system:

    john> conda --version
    conda 4.14.4

However, in case your system does not have conda installed you will see something similar to this which means you would need to install conda.

    john> conda --version
    -bash: conda: command not found

Several implementations of Conda exist, e.g., Anaconda and Miniconda, which differ only in the amount of pre-installed tools and packages. As the name implies, Miniconda is a light-weight implementation of Anaconda and is much quicker to install.

To install Miniconda, go to the miniconda download page [here](https://docs.conda.io/en/latest/miniconda.html) to get the latest version of the miniconda installer. Here, we assume you would like to install *Miniconda3 Linux 64-bit* which will work for most linux computers. First, download the installer using the **wget** command:

    john> wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
    --2022-11-14 12:22:06--  https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
    Resolving repo.anaconda.com (repo.anaconda.com)... 2606:4700::6810:8203, 2606:4700::6810:8303, 104.16.130.3, ...
    Connecting to repo.anaconda.com (repo.anaconda.com)|2606:4700::6810:8203|:443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 76607678 (73M) [application/x-sh]
    Saving to: 'Miniconda3-latest-Linux-x86_64.sh’
    
    Miniconda3-latest-Linux-x86_64.sh               100%[=======================================================================================================>]  73.06M  3.02MB/s    in 23s     

    2022-11-14 12:22:29 (3.15 MB/s) - 'Miniconda3-latest-Linux-x86_64.sh’ saved [76607678/76607678]

The output above should be very close to what you will see when downloading the installer. You can check that the file was downloaded using the **ll** command:

    john> ll
    drwxrwxrwt 19 root    root       20480 Nov 14 12:22 ./
    drwxr-xr-x 21 root    root        4096 Nov  4 10:41 ../
    -rw-rw-r--  1 john john 76607678 May 17 06:01 Miniconda3-latest-Linux-x86_64.sh

Next, we will need to run the installer on the command line simply by typing the name and pressing Enter. The installer will then guide you through the installation process.

    john> Miniconda3-latest-Linux-x86_64.sh
    
    Welcome to Miniconda3 py39_4.12.0

    In order to continue the installation process, please review the license
    agreement.
    Please, press ENTER to continue
    >>> 

When you come to the *License Agreement* you will ahve to press *Space* several times until you are at the end of the agreement. When asked if you agree (and in case you do) type *yes* and press enter

    Do you accept the license terms? [yes|no]
    [no] >>> yes

When you're asked about the installation path just got with the default unless you know what you're going and simply press Enter which will start the installtion.
When asked if you want to *run conda init* type *yes* and press Enter again. Now conda should be installed.

If you knwo type *conda --version* you should see the version of the installed conda on the command-line

    john> conda --version
    conda 4.14.4



    
    


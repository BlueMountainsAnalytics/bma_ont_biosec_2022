# Conda package manager

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](CONDA_1.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](CONDA_3.md)

## Installing Conda

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


<p align="right"><a href="https://bluemountainsanalytics.github.io/BMA_CLI-tutorial/CONDA_3.html">CONTINUE -></a>
</p>    
    


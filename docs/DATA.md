# Tools, dependencies and course data

[{% octicon home height:32 class:"right left" aria-label:hi %}](index.md)

## List of Bioinformatic Tools used
* [Minimap](https://github.com/lh3/minimap2)
* [Miniasm](https://github.com/lh3/miniasm)
* [Flye](https://github.com/fenderglass/Flye)
* [NanoPlot](https://github.com/wdecoster/nanopack)
* [NanoFilt](https://github.com/wdecoster/nanopack)
* [Assembler-Stats](https://github.com/sanger-pathogens/assembly-stats)
* [BASTA](https://github.com/timkahlke/BASTA)
* [Mummer](https://github.com/mummer4/mummer)
* [Samtools](http://www.htslib.org/)
* [Bedtools](https://bedtools.readthedocs.io/en/latest/)

## Conda environment file

A conda *environment.yml* file to build the course environment and install all tools into it can be found inside the biosec_course.tar.gz file that can be found [here](https://drive.google.com/drive/folders/1qvpQ2fwCogx39klaP22JcVYVEwXxf50g?usp=share_link).

Untar the file in your home directory using

    course_user> tar -xzvf biosec_course.tar.gz

The environment files can be foudn in biosec_course/misc/install_files.

Create the course environment with the following commands:

    course_user> conda env create -f environment.yaml
    course_user> conda env create -f environment.busco.yaml
    course_user> conda env create -f environment.artic.yaml
    course_user> install.sh
    course_user> basta.sh


## Course VM account

Account details to login/unlock the screen are

login: course_user

passwd: course_user

## Course data

All course data will be provided with the VirtualBox image. However, a zipped version of the course data and directory structure can be found [here](https://drive.google.com/drive/folders/1qvpQ2fwCogx39klaP22JcVYVEwXxf50g?usp=share_link) inside the *nbiosec_course.tar.gz* file.

## Dependencies

### Developer tools

Linux and MACOS users will need developer tools installed.

Ubuntu users will need to install build-essentials

    course_user> sudo apt-get install build-essential

MACOS users will need to install XCode available from the App Store and install *command-line tools* on the terminal using

    course_user> sudo sudo xcode-select --install

### Conda / Mamba

The tutorial provides a primer for package managers Conda & Mamba, i.e., a conda implementation will have to be installed 


#### Miniconda installation

Several implementations of Conda exist, e.g., Anaconda and Miniconda, which differ only in the amount of pre-installed tools and packages. As the name implies, Miniconda is a light-weight implementation of Anaconda and is much quicker to install.

To install Miniconda, go to the miniconda download page [here](https://docs.conda.io/en/latest/miniconda.html) to get the latest version of the miniconda installer. Here, we assume you would like to install *Miniconda3 Linux 64-bit* which will work for most linux computers. First, download the installer using the **wget** command:

    course_user> wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
    --2022-11-14 12:22:06--  https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
    Resolving repo.anaconda.com (repo.anaconda.com)... 2606:4700::6810:8203, 2606:4700::6810:8303, 104.16.130.3, ...
    Connecting to repo.anaconda.com (repo.anaconda.com)|2606:4700::6810:8203|:443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 76607678 (73M) [application/x-sh]
    Saving to: 'Miniconda3-latest-Linux-x86_64.sh’
    
    Miniconda3-latest-Linux-x86_64.sh               100%[=======================================================================================================>]  73.06M  3.02MB/s    in 23s     

    2022-11-14 12:22:29 (3.15 MB/s) - 'Miniconda3-latest-Linux-x86_64.sh’ saved [76607678/76607678]

The output above should be very close to what you will see when downloading the installer. You can check that the file was downloaded using the **ll** command:

    course_user> ll
    drwxrwxrwt 19 root    root       20480 Nov 14 12:22 ./
    drwxr-xr-x 21 root    root        4096 Nov  4 10:41 ../
    -rw-rw-r--  1 course_user course_user 76607678 May 17 06:01 Miniconda3-latest-Linux-x86_64.sh

Next, we will need to run the installer on the command line simply by typing the name and pressing Enter. The installer will then guide you through the installation process.

    course_user> Miniconda3-latest-Linux-x86_64.sh
    
    Welcome to Miniconda3 py39_4.12.0

    In order to continue the installation process, please review the license
    agreement.
    Please, press ENTER to continue
    >>> 

When you come to the *License Agreement* you will have to press *Space* several times until you are at the end of the agreement. When asked if you agree (and in case you do) type *yes* and press enter

    Do you accept the license terms? [yes|no]
    [no] >>> yes

When you're asked about the installation path just go with the default unless you know what you're doing, i.e., simply press Enter which will start the installtion.
When asked if you want to *run conda init* type *yes* and press Enter again. Now conda should be ready to use.

If you now type *conda --version* you should see the conda version printed to the command-line

    course_user> conda --version
    conda 4.14.4

Conda can now be used on your system.



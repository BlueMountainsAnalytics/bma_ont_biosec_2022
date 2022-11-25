# Conda vs Mamba 

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](CONDA_3.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](QC.md)

## Mamba ... the better snake?

As you have seen when you created the environments in the previous tutorials, conda can be a little slow when it tries to install tools. Especially the *Solving dependencies* step can take several minutes and sometimes even get stuck in a loop.

Mamba is a re-implementation, i.e., a re-write, of the Conda package manager using another programming language (C++ to be exact) that offers higher speed and more reliable dependency and environment resolution. It *understands* basically all conda commands and can even be installed inside an existing conda installation.


### Install Mamba

To get Mamba we simply install it into the *base* environment of our existing conda installation using the following command

    course_user> conda  install mamba --name base -c conda-forge

Once the installation is finished let's create another conda environment *ont_mamba* and install *python 3.10* and *porechop* into it. However, this time we use the command *mamba* instead of *conda*

    course_user> mamba create --name ont_mamba python==3.10 porechop

Follow the installation process on the screen, press Enter when asked to proceed.

Once the installation is done you can use the mamba environment exactly like a conda environment. You can even activate it using conda

    course_user> conda activate ont_mamba
    (ont_mamba) course_user>

The main difference is that Mamba is often faster and more reliable than Conda.

Congratulations, you are finally ready to do some Bioinformatics ... but maybe get a tea and a cookie first :)


<p align="right"><a href="https://bluemountainsanalytics.github.io/BMA_CLI-tutorial/QC.html">CONTINUE -></a>
</p>    
    


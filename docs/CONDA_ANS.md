# Conda Tutorial Answers

## Self-Check 1

### How do you list all conda environments already installed?

    john> conda env list

### How would you activate a the conda environment <i>anu_course</i>

    john> conda activate anu_course

### What command would you use if you wanted to install the tool <i>jellybean</i> from channel <i>conda-forge</i>?

    john> conda install -c conda-forge jellybean

### If you deactivate the environment ont_test2 and check the version of porechop, what wll you see? Why?

    (ont_test2) john> conda deactivate
    john> porechop --version

    Command 'porechop' not found, but can be installed with:

    sudo apt install porechop

Your operating system cannot find the tool *porechop* outside of the environment! This is the expected behavior of conda: the packages and tools installed inside a conda environment are only *visible* inside of that environment. As soon as you de-activate your environment your computer does not know where to find them.

<p align="left"><a href="https://bluemountainsanalytics.github.io/BMA_CLI-tutorial/CONDA_3.html">BACK =></a>
</p>

# Conda How-To 

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](CONDA_2.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](CONDA_4.md)

## Introduction to Conda

Conda is a package manager that automates the installation of scripts, packages and dependencies in a user-friendly way. IT uses the concept of *environments* that are independent and don't interact with each other, limiting the possibility of dependency or package conflicts.

A usual conda workflow looks like this:
  <ul>
    <li>Create a new conda environment</li>
    <li>Activate the new environment</li>
    <li>Install tools, packages, and dependencies</li>
    <li>Use the tools installed in the environment</li>
    <li>De-activate the environment<i/li>
  </ul>

Once a conda environment was created it can be activate or de-activate as many times as you want. The tools etc installed inside the environment won't disappear, e.g., when you re-start the computer or log out.


### Create a new Conda environment

To create a new environment use the command *conda create* plus the **--name** flag to set a name for your environment.

Let's create a new environment called ont_test.

    john> conda create --name ont_test

You should see the following output ...

    john> conda create --name ont_test
    Collecting package metadata (current_repodata.json): done
    Solving environment: done

... and after a little while conda will let you know the path it will try to install the new environment to and ask you to proceed. Simply press Enter ...


    ## Package Plan ##

    environment location: /home/john/miniconda3/envs/ont_test



    Proceed ([y]/n)? y

    Preparing transaction: done
    Verifying transaction: done
    Executing transaction: done
    #
    # To activate this environment, use
    #
    #     $ conda activate ont_test
    #
    # To deactivate an active environment, use
    #
    #     $ conda deactivate

    Retrieving notices: ...working... done

Finished. We now have a new conda environment called *ont_test*.

To list all conda environments use the command **conda env list**. If the only environment on oyur system was the one we just installed you would see an output similar to this:

    # conda environments:
    #
    base                  *  /home/john/miniconda3
    ont_test              *  /home/john/miniconda3/ont_test

There it is, in */home/john/miniconda3/ont_test*.

To remove the environment, all one would have to do is to remove the directory using **rm -r**

    john> rm -r /home/john/miniconda3/ont_test
    john> conda env list

    # conda environments:
    #
    base                  *  /home/john/miniconda3



## Activate a conda environment

Now that we have created our new environment we want to be able to use it. To use a conda environment one has to **activate** it, using the **conda activate** command followed by the name of the environment:

    john> conda activate ont_test
    (ont_test) john>

As you can see, after activating the *ont_test* environment, the command-line adds the name of the environment in brackets to our prompt. This shows us that we're inside the conda environment and can start to use it.


To get out of the environment we can use the conda command **deactivate**

    (ont_test) john> conda deactivate
    john> 


## Installing packages using conda

Now that we set up a new clean conda environment we need to install something in it. 

Conda packages can be installed from various so called *channels*. For example, the channel *bioconda* provides packages related to the biomedical research space including packages and tools for Oxford Nanopore data processing. One of these tools is the tools *porechop*, which finds and removes sequencing adapters from Oxford Nanopore reads. 

To install something using conda we use the command **conda install PACKAGE_NAME** where *PACKAGE_NAME* is the name of the tool/package we want to install. To specify a particular *channel* the tool can be found on we use the **-c** flag followed by the channel name. *Also, don't forget to activate your conda environment first!* 

    john> conda activate ont_test
    (ont_test) john> conda install -c bioconda porechop

Once you've hit Enter you will see the *Collecting package metadata* and *Solving environment* messages of conda, followed by a list of packages and dependencies conda will install. Hit Enter again to proceed with the installation process.

    Collecting package metadata (current_repodata.json): done
    Solving environment: done

    ## Package Plan ##

      environment location: /home/john/miniconda3/envs/ont_test

      added / updated specs:
        - porechop


    The following packages will be downloaded:

        package                    |            build
        ---------------------------|-----------------
        porechop-0.2.4             |  py310h30d9df9_3         105 KB  bioconda
        python-3.10.6              |ha86cf86_0_cpython        29.0 MB  conda-forge
        ------------------------------------------------------------
                                           Total:        29.1 MB

    The following NEW packages will be INSTALLED:

      _libgcc_mutex      conda-forge/linux-64::_libgcc_mutex-0.1-conda_forge None
      _openmp_mutex      conda-forge/linux-64::_openmp_mutex-4.5-2_gnu None
      bzip2              conda-forge/linux-64::bzip2-1.0.8-h7f98852_4 None
      ca-certificates    conda-forge/linux-64::ca-certificates-2022.9.24-ha878542_0 None
      ld_impl_linux-64   conda-forge/linux-64::ld_impl_linux-64-2.39-hc81fddc_0 None
      libffi             conda-forge/linux-64::libffi-3.4.2-h7f98852_5 None
      libgcc-ng          conda-forge/linux-64::libgcc-ng-12.2.0-h65d4601_19 None
      libgomp            conda-forge/linux-64::libgomp-12.2.0-h65d4601_19 None
      libnsl             conda-forge/linux-64::libnsl-2.0.0-h7f98852_0 None
      libsqlite          conda-forge/linux-64::libsqlite-3.39.4-h753d276_0 None
      libstdcxx-ng       conda-forge/linux-64::libstdcxx-ng-12.2.0-h46fd767_19 None
      libuuid            conda-forge/linux-64::libuuid-2.32.1-h7f98852_1000 None
      libzlib            conda-forge/linux-64::libzlib-1.2.13-h166bdaf_4 None
      ncurses            conda-forge/linux-64::ncurses-6.3-h27087fc_1 None
      openssl            conda-forge/linux-64::openssl-3.0.7-h166bdaf_0 None
      pip                conda-forge/noarch::pip-22.3.1-pyhd8ed1ab_0 None
      porechop           bioconda/linux-64::porechop-0.2.4-py310h30d9df9_3 None
      python             conda-forge/linux-64::python-3.10.6-ha86cf86_0_cpython None
      python_abi         conda-forge/linux-64::python_abi-3.10-2_cp310 None
      readline           conda-forge/linux-64::readline-8.1.2-h0f457ee_0 None
      setuptools         conda-forge/noarch::setuptools-65.5.1-pyhd8ed1ab_0 None
      tk                 conda-forge/linux-64::tk-8.6.12-h27826a3_0 None
      tzdata             conda-forge/noarch::tzdata-2022f-h191b570_0 None
      wheel              conda-forge/noarch::wheel-0.38.4-pyhd8ed1ab_0 None
      xz                 conda-forge/linux-64::xz-5.2.6-h166bdaf_0 None
    
    
    Proceed ([y]/n)? 
    
    
    
    Downloading and Extracting Packages
    porechop-0.2.4       | 105 KB    | #################################################################################################### | 100% 
    python-3.10.6        | 29.0 MB   | #################################################################################################### | 100% 
    Preparing transaction: done
    Verifying transaction: done
    Executing transaction: done
    Retrieving notices: ...working... done

Done! Now *porechop* is installed in your conda environment. To check that everything went well check the porechop version

    (ont_test) john> porechop --version
    0.2.0



## Creating a conda environment with pre-installed packages

Now we know how to create a conda environment, activate it and install packages and tools in it. However, we can also install packages in environments at the time of creation. We can even set a specific version of the packages and tools we want to install.

The following command will

  <ul>
    <li>Create the conda environment <i>ont_test2</i></li>
    <li>Install python version 3.6 into the environment</li>
    <li>Install the tool <i>porechop</i> into the environment</li>
  </ul>

    john> conda create --name ont_test2 python==3.6 porechop

Once Conda is done with the installation activate the environment *ont_test2* and check the version of python and porechop

    john> conda activate ont_test2
    (ont_test2) john> python --version
    3.6.0
    (ont_test2) john> porechop --version
    0.2.4

Great. Now you have a good basis to work with Conda environments


## Conda Self-Check

  <ol>
    <li>How do you list all conda environments already installed?</li>
    <li>How would you activate a the conda environment <i>anu_course</i>?</li>
    <li>What command would you use if you wanted to install the tool <i>jellybean</i> from channel <i>conda-forge</i>?<\li>
    <li>If you deactivate the environment ont_test2 and check the version of porechop, what wll you see? Why?</li>
  </ol>

[Answers](CONDA_ANS.md)


For a short Conda Cheat-Sheet click [here](CON-CS.md).

<p align="right"><a href="https://bluemountainsanalytics.github.io/BMA_CLI-tutorial/CONDA_4.html">CONTINUE -></a>
</p>    
    


# Conda Cheat Sheet

## Create an environment

    john> conda create -n ENVIRONMENT_NAME

This will create the environment of name ENVIRONMENT_NAME without any pre-installed tools.


## Create a new environment with pre-installed python version 3.8
:
    john> conda create -n MY_ENVIRONMENT python==3.8

## Activate a conda environment

    john> coda activate ENV_NAME

where 

  <ul>
    <li>ENV_NAME is the name of the environment you want to activate</li>
  </ul>

## Deactivate a conda environment

  john> conda deactivate

## Install a package using conda

    john> conda install TOOL_NAME

where 
  <ul>
    <li>TOOL_NAME is the name of the tool you want to install</li>
  </ul>


### Install from a specific channel

    john> conda install -c CHANNEL TOOL_NAME

where

  <ol>
    <li>CHANNEL = the name of the channel<li>
    <li>TOOL_NAME = the name of the tool that should be installed</li>
  </ol>






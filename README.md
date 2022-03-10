# SCG Setup

## Overview

I had a lot of frustration using the [Stanford SCG Informatics Cluster](https://login.scg.stanford.edu/).
In particular, I was using OnDemand, which lets you start up an interactive RStudio Server connected to an interactive job.
It sounds great, but in practice had a lot of issues.

The RStudio version is out of date, and the graphics didn't work right.
The terminal and Git features were incredibly slow and would crash.
I had to pick all my settings each time I logged on.
Installing packages was a big headache using the R module on the server.

I decided it was too much of a drag on productivity.
Now I use a setup with VS Code and Anaconda.

## Setup

I use VS Code locally, with two critical extensions:

- Remote SSH: a Microsoft supported extension for remote development through an SSH connection. Amazing stuff
- vscode-R: an amazing extension for R language features. Requires `jsonlite`, `rlang`, and `languageserver` R packages.

I then use Conda for managing R environment and packages.
Some important steps:

- Downloaded miniconda for linux
- Downloaded `mamba` which is a much faster drop-in replacement for conda
- Had issues until I did a clean install from a YAML file with all dependencies listed using mamba.

Key conda channels are `conda-forge` and `bioconda`.

An important gotcha is that you have to set the `r.term.linux` and `r.path.linux` to the path of the R binary for the conda environment.

For example, `/home/hershe/miniconda3/envs/R_mesa_gxe/bin/R`

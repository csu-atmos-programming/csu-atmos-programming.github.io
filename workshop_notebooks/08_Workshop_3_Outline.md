---
title: "Workshop 3: Command Line, Python Environments, and Development Environments"
date: 2024-09-05
authors:
  - name: JT Thielen
---

In this workshop, we'll be covering all the basics you need to get ready for doing Python programming on *your own* computer, as well as introduce how to use remote computers (like [CSU Engineering's Asha Cluster](https://www.engr.colostate.edu/ets/asha-cluster/)). We'll be going over this content in an interactive/back-and-forth fashion, so this outline below is just that, an outline. A more detailed summary of material will be posted as a reference after-the-fact, based on what we end up covering.

## Outline

- Verify the basics (conda and VS Code) have been installed
- Basics of the command line (structure of a command, viewing and navigating directories, copy/moving files, flags and getting help)
- Intro to conda
    - [This cheat sheet may come in handy!](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf)
    - This will include a basic intro to the python terminal/REPL
    - An important link you may need to copy/paste: `https://csu-atmos-programming.github.io/static/environment.yml` (this will get you a nice environment of packages for atmospheric sciences)
- Intro to JupyterLab
- Intro to VS Code
- Using remote systems (like Asha)

## Extra Reference Materials

### Installing Python on Windows without Admin Permissions

1. Use the prior instructions to install Windows Terminal
1. Install the *windows* version of miniconda from https://docs.anaconda.com/miniconda/#latest-miniconda-installer-links
1. Use the prior instructions to install VS Code
1. Once we both a) set up VS Code with our extensions and b) create a conda environment, we need to select the environment's python interpreter in VS Code to connect the two together.
---
title: "Workshop 3: Ahead-of-Workshop Installation Instructions"
date: 2024-09-05
authors:
  - name: JT Thielen
---

In this set of instructions, we'll be going over the basics of how to install the essential software we'll need for Workshop 3:

- conda (using `miniconda`)
- Visual Studio Code
- (Windows Only) WSL and Windows Terminal

Note that this will not cover installing Python packages in an environment or VS Code extensions (except for the special one needed on Windows), which will instead be covered in the workshop itself.

Each of these steps should be completed in order.

For Windows users, while there are multiple options for how to set things up, these instructions will be based around using WSL (so that macOS/Linux-style terminal commands work just the same), as described in this tutorial: https://learn.microsoft.com/en-us/training/modules/developing-in-wsl/. If you don't want to use this approach, please reach out the either of the programming TAs and we'll help you out with that.

### Installing WSL and Windows Terminal

:::{warning}
These instructions are only for Windows users! Please skip this section if you use macOS or Linux, and instead go to the [Installing miniconda](#installing-miniconda) section.
:::

To use these instructions, you must make sure that you're running Windows 11 or Windows 10 version 2004+ (Build 19041 and higher). If you are not, please contact either of the programming TAs for an alternate set of instructions.

#### Install Windows Terminal

Go to the Microsoft Store and search for "Windows Terminal" (or use this link: https://apps.microsoft.com/detail/9n0dx20hk701). Install this app, and you should be good to go!

#### Enable the Windows Subsystem for Linux:

- Open PowerShell as Administrator (either via start menu or in Windows Terminal) and run: `wsl --install` in the terminal.
    - This command enables the necessary Windows features and installs the Ubuntu distribution by default. You can later choose to install a different Linux Distribution. Given its popularity, we are using Ubuntu.
- Restart Your Computer: A restart is required to complete the installation and apply changes.

#### Set up your Linux distribution:

- Upon restart, open the newly installed Linux distro (Ubuntu) from the Windows Start menu or Windows Terminal app.
- Follow the prompts to create a user account and password for your Linux distro.

After these steps, you should be ready to go!

### Installing `miniconda`

Be sure to select the proper tab for your operating system (macOS, Linux (any distribution), or Windows). These instructions assume you are on a:

- M-series (Apple Silicon) processor if on macOS
- Intel/AMD (x64, not Arm) processor if on Windows or Linux

For more detailed versions of all of these (or if you have an Intel Mac or Arm Linux or Windows system), see the [miniconda installation instructions from the conda documentation](https://docs.anaconda.com/miniconda/#latest-miniconda-installer-links) and/or reach out to one of the programming TAs for more detailed instructions.

::::{tab-set}
:::{tab-item} macOS (M-series)
:sync: mac
These four commands download the latest M-series version of the MacOS installer, rename it to a shorter file name, silently install, and then delete the installer:

```
mkdir -p ~/miniconda3
curl https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh -o ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm ~/miniconda3/miniconda.sh
```

After installing, initialize your newly-installed Miniconda. The following commands initialize for bash and zsh shells (only use one if you only have one of the shells):

```
~/miniconda3/bin/conda init bash
~/miniconda3/bin/conda init zsh
```

Finally, close and re-open your terminal, and it should now indicate that you have conda installed by seeing the `(base)` environment tag in your terminal prompt.

:::
:::{tab-item} Linux (x64)
:sync: linux
These four commands download the 64-bit version of the Linux installer, rename it to a shorter file name, silently install, and then delete the installer:

```
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm ~/miniconda3/miniconda.sh
```

After installing, initialize your newly-installed Miniconda. The following commands initialize for bash and zsh shells (only use one if you only have one of the shells):

```
~/miniconda3/bin/conda init bash
~/miniconda3/bin/conda init zsh
```

Finally, close and re-open your terminal, and it should now indicate that you have conda installed by seeing the `(base)` environment tag in your terminal prompt.

:::
:::{tab-item} Windows
:sync: windows

Open your Ubuntu terminal (from the start menu or in Windows Terminal) to do the following. Do not try running these in the regular command prompt or PowerShell--they will not work.

These four commands download the 64-bit version of the installer, rename it to a shorter file name, silently install, and then delete the installer:

```
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm ~/miniconda3/miniconda.sh
```

After installing, initialize your newly-installed Miniconda. The following commands initialize the bash shell:

```
~/miniconda3/bin/conda init bash
```

Finally, close and re-open your terminal, and it should now indicate that you have conda installed by seeing the `(base)` environment tag in your terminal prompt.
:::
::::

### Installing VS Code

::::{tab-set}
:::{tab-item} macOS
:sync: mac

- Go to https://code.visualstudio.com/Download
- Select and download the appropriate package
- Run the installer

After this, you should be good to go!

:::
:::{tab-item} Linux (x64)
:sync: linux

- Go to https://code.visualstudio.com/Download
- Select and download the appropriate package
- Run the installer

After this, you should be good to go!

:::
:::{tab-item} Windows
:sync: windows

Visit the Microsoft Store and search "Visual Studio Code" (or visit https://apps.microsoft.com/detail/xp9khm4bk9fz7q) and download and install the application.

Open Visual Studio Code, and select Extensions from the side bar (the icon that looks like a stack of boxes with one breaking off of the upper-right). Search for WSL in the Extensions view search bar. Find the extension published by Microsoft. Click the 'Install' button.

Then, once installed, In VS Code, open your Command Palette (Ctrl/CMD+Shift+P) and type in WSL: Connect to WSL. Your VS Code will reload and connect to WSL, and all should be good to go!

If you have issues with these steps, please see https://learn.microsoft.com/en-us/training/modules/developing-in-wsl/4-setting-up-windows-subsystem-linux-extension for more details.
:::
::::
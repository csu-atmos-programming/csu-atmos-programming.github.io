---
title: Getting Started with Python!
---

## 1 - Install python!

Conda or miniconda is highly recommended to manage your python installation. Download and run the installer for either the full conda installer or miniconda <a href="https://www.anaconda.com/download/success?reg=skipped">here</a>. If you plan on using VS Code, miniconda is probably all you need, conda will also include a bunch of GUIs that duplicate what you can already do in VS Code.

- OPTIONAL - Download <a href="static/environment.yml">environment.yml</a>, open a conda prompt and create a new environment "atmos" from this file by running 
```conda create -f environment.yml```
You can activate and use the python install and packages in this environment by activating it with 
``` conda activate atmos```


## 2 - Install your IDE of choice!

An <b>I</b>ntegrated <b>D</b'>evelopment <b>E</b>nvironment combines many, if not all the tools you need to write, check, test, and run code, all in one window/application. <a href="https://code.visualstudio.com/download?_exp_download">VS Code</a> is a very robust IDE for most languages, supports plug ins, and runs on both Mac and Windows!

## 3 - Setup IDE (VS Code)

Since VS Code was suggested earlier, we'll stay on that theme. Plugin support was mentioned before, so let's install the plugins we'll need for python.

### Get extensions
- Click the extension
s button on the sidebar (stacked cubes) and search for python
- Click and install Python Debugger, Python, and Pylance
:::{important}
These plugins are open source, so let's be mindful of the developer that publishes them. Each entry in the list will have three lines: a title, a description, and the publisher. For these, make sure you are installin the Microsoft published extensions!
:::
- Search and install Jupyter plugin

### Setup conda as interpreter

- Type (sequentially all at once): CTRL (or CMD on Mac) + Shift + P
- In the command box that pops up at the top of the screen, type "Python: Select Interpreter" (feel free to click on the result when you see it)
- You should see a list of python environments, including your conda install (if you haven't set up any conda environments yet, it might just be (base))
- Select the environment you want to use

### Setup terminal

- In the top menu bar, click Terminal -> New Terminal
- If your command prompt line does not have you conda environment in paranthesis at the beginnin, we need to init conda by typing
```conda init ```
 then 
 ```conda activate <your env>```


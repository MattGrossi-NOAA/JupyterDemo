---
title: Jupyter Lab and Jupyter Notebook
subtitle: Demonstration of how to configure and use Jupyter Lab and Jupyter Notebooks on a local computer
author: matt.grossi@noaa.gov
date: November 2024
---

Jupyter Notebooks (file extension `.ipynb`) are versitile web-based platform for interactively running computer code (most commonly Python), creating markdown, displaying equations, data visualization, and many other things. Jupyter Lab is a web-based service used to open and run Jupyter Notebooks. Once Jupyter Lab is set up, notebooks are convenient and easy to use, but initial configuration can be tricky. Here are some ways to get up and running with Jupyer Lab on a local computer:

### Method 1: Docker

With [Docker](https://www.docker.com/) installed and running, navigate to the directory containing this file in a terminal window. Then build and launch a Docker container:

```shell
docker-compose build
docker-compose up
```

Navigate to the URL that prints to the screen and open this notebook from the file explorer in the left panel of the Jupyter Lab dashboard that opens.

**When finished:** Spin down the Docker container before closing the Docker application:

```shell
docker-compose down
```

### Method 2: Visual Studio Code with Docker

With [Visual Studio Code](https://code.visualstudio.com/) (VS Code) installed and [Docker](https://www.docker.com/) installed and running, open VS Code and click "Open Folder..." on the Welcome screen or from the File menu. Select the directory containing this notebook and the Docker files and click "Select Folder".

Click the blue button in the bottom left corner of VS Code -- the one that looks like two "L's" -- and then select "Reopen in container..." from the dropdown menu.

::: {.callout-note}

If a development container already exists in this directory, a popup prompt about reopening in a container may appear in the lower right corner of VS Code upon opening the folder. This can be used instead of the blue button.

:::

**First time only:** Respond to the prompts that appear in the command palatte that appears in the top of the window:

* "Add configuration to workspace"
* "From 'Dockerfile'"
* Click "OK" twice

When the container builds and reopens, click the "Extensions" icon in the left menu (looks like four blocks), type "Quarto" in the search box, and click "Install in Dev Container" to add the Quarto extension. This is used for document formatting. When finished, return to the file explorer.

Open this Jupyter notebook from the file explorer and run as normal.

**When finished:** Click the blue "Dev Container" button in the bottom left corner and select "Close Remote Connection" from the dropdown.


### Method 3: pip environment

**First time only:** In a terminal window, navigate to the directory containing this Jupyter notebook and create a Python virtual environment (VE) called `myenv` (or anything you want, but no spaces):

```shell
python -m venv myenv
```

Activate the VE:

```shell
source my_env/bin/activate
```

Install Jupyter and add it to the VE (first time only):

```shell
pip install --user ipykernel
python -m ipykernel install --user --name=myenv

```

Lanuch Jupyter Notebook and, in a web browser, navigate to the URL that prints to the screen:

```shell
jupyter notebook
```

Finally, open this notebook from the file explorer in the left panel of the Jupyter Lab dashboard that opens.

**When finished:** Deactivate the pip environment:

```shell
deactivate
```

### Method 4: Conda environment

Anaconda can be used instead of pip to create virtual environments for Python development. The process is essentially the same as above.

**First time only:** In a terminal window, navigate to the directory containing this Jupyter notebook and create a Python VE called `myenv` (or anything you want, but no spaces):

```shell
conda create -n myenv
```

Activate the VE:

```shell
conda activate myenv
```

Install Jupyter and add it to the VE (first time only):

```shell
conda install --user ipykernel
python -m ipykernel install --user --name=myenv

```

Lanuch Jupyter Notebook and, in a web browser, navigate to the URL that prints to the screen:

```shell
jupyter notebook
```

Finally, open this notebook from the file explorer in the left panel of the Jupyter Lab dashboard that opens.

**When finished:** Deactivate the pip environment:

```shell
conda deactivate
```

<hr>

### Disclaimer

This repository is a scientific product and is not official communication of the National Oceanic and Atmospheric Administration, or the United States Department of Commerce. All NOAA GitHub project content is provided on an ‘as is’ basis and the user assumes responsibility for its use. Any claims against the Department of Commerce or Department of Commerce bureaus stemming from the use of this GitHub project will be governed by all applicable Federal law. Any reference to specific commercial products, processes, or services by service mark, trademark, manufacturer, or otherwise, does not constitute or imply their endorsement, recommendation or favoring by the Department of Commerce. The Department of Commerce seal and logo, or the seal and logo of a DOC bureau, shall not be used in any manner to imply endorsement of any commercial product or activity by DOC or the United States Government.

### License

This content was created by U.S. Government employees as part of their official duties. This content is not subject to copyright in the United States (17 U.S.C. §105) and is in the public domain within the United States of America. Additionally, copyright is waived worldwide through the CC0 1.0 Universal public domain dedication.

<hr>

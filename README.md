# RTutorial: Introduction to R for biomedical physics class

This repository contains study material, data and code samples for a short introductory R tutorial for students of biomedical physics.

## Pre-requisites

For the class, you need to install a few things to start.

### Install R
* Go to https://cloud.r-project.org
* Select the installation package appropriate for your operating system (and package manager)
* Install

### Install RStudio
* Go to https://www.rstudio.com/products/rstudio/download/
* Select "Download" for RStudio Desktop
* Section "Installers for supported platforms", click on RStudio 1.1.383 - Windows Vista/7/8/10
* Install

### Install the tidyverse suite in RStudio
The tidyverse suite of R packages provide a set of R features/functionalities that we will use in this tutorial.
* Open RStudio. If you see any error messages or something looks weird, let me know immediately (peter.kvasnicka@mff.cuni.cz)
* From the top menu, select __Tools/Install Packages__.
* This opens the __Install Packages__ dialogue. Enter __tidyverse__ in the __Packages__ field, leave all else as it is, and click __Install__.
* In the console window, you will see the code that does the job. It should run without errors, if not, let me know.
* Go to the console window and write __library("tidyverse")__ <ENTER>. You should see some warnings about package conflicts, but that is OK. If you see any error messages, let me know.

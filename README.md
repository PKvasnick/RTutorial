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

## GitHub repository of the RTutorial
This is the GitHub repository of the tutorial.
It resides at https://github.com/PKvasnick/RTutorial and you can find all course materials here and download it.

## Your own GitHub repository
To upload your coursework for review, you will need your own GitHub repository.

### Sign up for __GitHub__
* Go to https://www.github.com and sign up.
* Click __Start a project__, make it public, and enter a short description in the __README.md__ file.

Using __GitHub__ is a reasonable way of sharing code and data. The most important feature is that code and data are recorded with their full *_history_*. This is made possible by using a program called __git__, which is the most frequently used *_version control system_*. Version control systems are routinely used by programmers, but are increasingly in use by people in many other areas, such as scientific paper authors.
__git__ takes care about changes made to your code, data, and documentation, helps you recover from undesired changes, co-operate with other people and share your code and data. 

### Manage your __GitHub__ repository
__git__ is a Unix program and there is no natural port to Windows. But there are several solutions that allow you to use __git__ on Windows:
* Use the __Linux console__ provided by Windows Subsystem for Linux, https://msdn.microsoft.com/en-us/commandline/wsl/install-win10. This is the most complete option to manage any git repositories.
* Use __TortoiseGit__, https://tortoisegit.org/
* Use __GitHub Desktop__, https://desktop.github.com/ - this is what I recommend you to start with. You will only have a limited set of __git__ features available, but it is a very practical way to update and service your __GitHub__ repository.

1. Go to https://desktop.github.com, download and install __GitHub Desktop__.
2. Sign-in to GitHub with your credentials.
3. You will see your GitHub repository, and you can download it (*_clone_* in git-speak) to your laptop.

### GitHub Desktop workflow
1. Open __GitHub Desktop__.
2. Top menu __File__/__Clone repository__, select the GitHub repository you want to clone to your hard drive, and enter the destination on your local drive in the __Local Path__ field (or go with the default).
3. You can make changes to your code/data on your laptop. Use any editor or __RStudio__. You will see the changes in the __Changes__ tab in __GitHub Desktop__.
4. Once you've made a meaningful change, you have to __commit__ it - save it to __git__ history: Enter a message describing the change you made in the __Summary__ and __Description__ fields at bottom left of __GitHub Desktop__ widnow, and click the green __Commit to master__ button.
5. Your changes are now saved in __git__ history on your drive. You want to have them safely stashed on the cloud, in your __GitHub__ repo, so that other people can see them and they are safe in case something bad happens to your laptop. For that, got to top menu, __Repository__/__Push__, or just press __Ctrl-P__. You can check in your Internet browser that your changes are on __GitHub__.

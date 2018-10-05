# RTutorial: Introduction to R for biomedical physics class

This repository contains study material, data and code samples for a short introductory R tutorial for students of biomedical physics.

## Pre-requisites

For the class, you need to install a few things to start.

### Install R
* Go to https://cloud.r-project.org
* Select the installation package appropriate for your operating system (and package manager). Install the newest version of R.
* Install. __On Widnows, install to a directory with names without spaces or diacritics__. Some packages wouldn't install in *C:\\Program Files*, in particular the packages *_broom_* and *_hms_* needed for *_tidyverse_*. Use something like *C:\\R* instead.

### Install RStudio
* Go to https://www.rstudio.com/products/rstudio/download/
* Select "Download now" for __RStudio Desktop / Open source__.
* Section "Installers for supported platforms", click on *RStudio 1.1.456 - Windows Vista/7/8/10*.
* Install. __On Windows,__ I advise to use the directory you used to install R, or other directory without spaces or diacritics in the path.
* __On Widnows, allow RStudio through your firewall.__. RStudio package installation guide needs to access Internet, and RStudio needs to launch its own html server to handle previews. None of this will work if your antivirus program's firewall won't let RStudio comms through.

### Install the tidyverse package suite
The *_tidyverse_* suite of R packages provide a set of R features/functionalities that we will use in this tutorial.
* Open RGui. On Windows, this means locate R in your Start menu or click an R icon on the desktop, if you have one created.
* At the prompt, write `install.packages("crayon")`. Check that the installation succeeded.
* Next install the *tidyverse* suite itself, `install.packages('tidyverse')`. Again, you should see the word *DONE* somewhere by the end of the console listing.
* To check, write `library(tidyverse)` at the command prompt and press `<ENTER>`. There should be no errors.
* Open *_RStudio_*. If you don't see the Console right away, double-click at the bottom tab to display it. Again, enter `library(tidyverse)` and press `<ENTER>`.
* Let me (peter.kvasnicka@mff.cuni.cz) know if you don't succeed.


## GitHub repository of the RTutorial
This is the GitHub repository of the tutorial.
It resides at https://github.com/PKvasnick/RTutorial and you can find all course materials here and download it.

__NOTE:__: The R notebooks in the repository have ISO-8859-2 encoding. *RStudio* will try to use ISO-8859-1 encoding (default Windows), and accented characters will display incorrectly. To change this, re-open the file with __File/Reopen with encoing...__. This ensures that you can use national characters in plots and also `knitr` will work correctly and produce correct PDF files. On the other hand, files with ISO-8859-2 may not display correctly in *GitHub Desktop*. Also, the encoding changes automatically if you import an Excel sheet. We will have to live with it.

## Your own GitHub repository
To upload your coursework for review and to learn to manage your own projects, you will need your own GitHub repository. To create one, you may proceed as follows:

### Sign up for __GitHub__
* Go to https://www.github.com and sign up.
* Click __Start a project__, make it public, and enter a short description in the __README.md__ file. To edit `*.md` (*_markdown_*) files, you can use any text editor. I use *_Atom_* (https://atom.io/) on Windows; install the *_Markdown preview_* package for good comfort.

Using __GitHub__ is a reasonable way of sharing code and data. The most important feature is that code and data are recorded with their full *_history_*. This is made possible by using a program called __git__, which is the most frequently used *_version control system_*. Version control systems are routinely used by programmers, but are increasingly in use by people in many other areas, such as scientific paper authors.
__git__ takes care about changes made to your code, data, and documentation, helps you recover from undesired changes or branch your development, co-operate with other people, and share your code and data.

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
5. Your changes are now saved in __git__ history on your drive. You want to have them safely stashed on the cloud, in your __GitHub__ repo, so that other people can see them and they are safe in case something bad happens to your laptop. For that, go to the top menu, __Repository__/__Push__, or just press __Ctrl-P__. You can check in your Internet browser that your changes are on __GitHub__.

# RTutorial: Introduction to R for biomedical physics class

This repository contains study material, data and code samples for a short introductory R tutorial for students of biomedical physics.

## Pre-requisites

For the class, you need to install a few things to start.

### Install R
* Go to https://cloud.r-project.org
* Click on one of _*Download R for*_ ...  items appropriate for your operating system.
* Click _*base*_.
* Select the installation package appropriate for your operating system (and package manager). Currently this is _*Download R 4.0.2 for Windows*_. 
* Confirm to download and save the installation binary.
* Install R (run the installer). Go with default options, except _installation directory_ on Windows - set installation directory such as *C:\\R\\R-4.0.2* (see below).

#### Note:
__On Widnows, install to a directory with names without spaces or diacritics__. Some packages wouldn't install in *C:\\Program Files*, in particular the packages *_broom_* and *_hms_* needed for *_tidyverse_*. Use something like *C:\\R* instead. For more details, see https://www.r-bloggers.com/windows-user-space-issues-with-installing-r-packages/ .

Expect problems, if your Windows username contains spaces or diacritics (such as _*Ján Novák*_).

In case of errors during package installation, browse the error messages for directories that have spaces or diacritics in their names.

If you have problems, let me know, peter.kvasnicka@mff.cuni.cz.

### Install RStudio
* Go to https://www.rstudio.com/products/rstudio/download/
* Select "Download" for __RStudio Desktop / Open source license__.
* Click on the blue button to download the recommended version for your operating system (such as *_RStudio 1.3.1093.exe_* for Windows 10/8/7).
* Install. __On Windows,__ I advise to use the directory you used to install R, such as _*C:\\R*_, or other directory without spaces or diacritics in the path. For example, on my Windows 10 system, I installed R in _*D:\\R\\R-4.0.2*_ and RStudio in _*D:\\R\\RStudio*_.
* __On Widnows, allow RStudio through your firewall__ when the corresponding pop-up window appears. RStudio package installation tool needs Internet access and RStudio needs to launch its own html server to handle help and notebook previews. None of this will work if your antivirus program's firewall won't let RStudio communications through. You will run into the prompt during the next step.

### Install the tidyverse package suite
R is modular. You can select statistical features you wish to use by installing appropriate packages. At this stage, we are going to install a basic set of packages that we are going to use: The *_tidyverse_* suite of R packages provide a set of R features/functionalities that we will use in this tutorial.

#### Method 1
* Open RStudio (Press Windows key and start writing "RStudio" until "RStudio app" appears).
* From RStudio's main menu, select _*Tools/Install packages*_.
* In the middle text field "Packages (separate multiple with space or comma)" write "crayon tidyverse". Make sure the check box next to _*Install dependencies*_ is checked. Click _*Install*_.
* _This is the time_ when your firewall may intercept RStudio's attempt to communicate via Internet and ask what to do. Allow RStudio through the firewall. It will happen at most once.
* The installation takes some time. Watch output to make sure no error messages are displayed. If you see errors, try *Method 2*.
* If everything worked, click into the console window and write `library(tidyverse)` and press Enter. Make sure there are no angry messages. Normal output should look as follows:

~~~~
> library(tidyverse)
-- Attaching packages --------------------------- tidyverse 1.3.0 --
v ggplot2 3.3.2     v purrr   0.3.4
v tibble  3.0.3     v dplyr   1.0.2
v tidyr   1.1.2     v stringr 1.4.0
v readr   1.3.1     v forcats 0.5.0
-- Conflicts ------------------------------ tidyverse_conflicts() --
x dplyr::filter() masks stats::filter()
x dplyr::lag()    masks stats::lag()
>
~~~~

#### Method 2 (use in case Method 1 wouldn't work)

* Open R console, - _*RGui*_. On Windows, this means press Windows key and start writing "RGui" until "R i386 4.0.2" appears, or locate R in your Start menu or click an R icon on the desktop, if you have one created.
* At the prompt, write `install.packages("crayon")`. Check that the installation succeeded.
* Next install the *tidyverse* suite itself, `install.packages('tidyverse')`. Again, you should see the word *DONE* somewhere by the end of the console listing.
* To check, write `library(tidyverse)` at the command prompt and press `<ENTER>`. There should be no errors.
* Open *_RStudio_*. If you don't see the Console right away, double-click at the bottom tab to display it. Again, enter `library(tidyverse)` and press `<ENTER>`.

__Let me (peter.kvasnicka@mff.cuni.cz) know if you don't succeed.__



## GitHub repository of the RTutorial

This is the GitHub repository of the tutorial.
It resides at https://github.com/PKvasnick/RTutorial and you can find all course materials here and download it.

__NOTE:__: The R notebooks in the repository have ISO-8859-2 encoding. *RStudio* will try to use ISO-8859-1 encoding (default Windows), and accented characters will display incorrectly. To change this, re-open the file with __File/Reopen with encoding...__. This ensures that you can use national characters in plots and also `knitr` will work correctly and produce correct PDF files. On the other hand, files with ISO-8859-2 may not display correctly in *GitHub Desktop*. Also, the encoding changes automatically if you import an Excel sheet. We will have to live with it.

## Your own GitHub repository
To upload your coursework for review and to learn to manage your own projects, you will need your own GitHub repository. To create one, you may proceed as follows:

### Sign up for __GitHub__
* Go to https://www.github.com and sign up.
* Click __Start a project__, make it public, and enter a short description in the __README.md__ file. To edit `*.md` (*_markdown_*) files, you can use any text editor.  I use *_Atom_* (https://atom.io/) on Windows; install the *_Markdown preview_* package for good comfort.

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
4. Once you've made a meaningful change, you have to __commit__ it - save it to __git__ history: Enter a message describing the change you made in the __Summary__ and __Description__ fields at bottom left of __GitHub Desktop__ window, and click the green __Commit to master__ button.
5. Your changes are now saved in __git__ history on your drive. You want to have them safely stashed on the cloud, in your __GitHub__ repo, so that other people can see them and they are safe in case something bad happens to your laptop. For that, go to the top menu, __Repository__/__Push__, or just press __Ctrl-P__. You can check in your Internet browser that your changes are on __GitHub__.

### Typora
[Typora](https://typora.io/) is a clean distraction-free Markdown editor for Windows. I recommend using it to write  markdown whenever you need. 
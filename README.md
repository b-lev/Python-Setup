# Introduction
This page provides some general advice on how to set up your local environment to code with Python.

In the examples below, we are going to focus on Python 3.9, and we'll give version numbers for all other tools so that
you can avoid unexpected errors. 

All tools are free. (And I have no relationship with any of the third parties who have made the tools we'll be using.)

# Getting all the tools installed

1. To get started with this tutorial, first make sure you have [Python installed](https://www.python.org/downloads/) and that you can access it from a command line. On windows I suggest you use a PowerShell window. On MacOS and Unix it's best to use a Terminal window. Once you have started the command line, type ```python``` at the prompt. You should see something like this:

    ```
    PS C:\Users\brian> python
    Python 3.9.5 (tags/v3.9.5:0a7dcbd, May  3 2021, 17:13:28) [MSC v.1928 32 bit (Intel)] on win32
    Type "help", "copyright", "credits" or "license" for more information.
    >>>
    ```
    To quit you can type ```exit()``` and hit return. 

    Note that it says "3.9.5". The "3.9" is the important part. If you see anything else, you can try to start python with ```python3.9" instead.

1. Create an account on [github](https://github.com/join). There is no need to sign up for a paid plan. 


1. Download and install [github desktop](https://desktop.github.com). You can use git from a terminal, but this app is way easier.

1. [Download](https://code.visualstudio.com/Download) Visual Studio Code. 

# Create a repository 

There is no excuse for losing your files for a project or assignment. Nope, it's just not acceptable. You should never code such that your files aren't backed up elsewhere. One solution is to use tools that backup hourly or even everything you save a file; these include Apple TimeMachine, or Crashplan, Dropbox, OneDrive, Box, and more. Those solutions are useful, but they are not good enough for software engineering and completing assignments. Instead, we need to use a tool for source control. 

Git is our software of choice for source control. Many other such tools exist. Now in reality, we aren't going to using Git only, we are going to use GitHub, which is Git and cloud backup. (It's worth noting that the Github people didn't create git, but that's a story for another day.) The nice thing about Github is that if your files are destroyed, you can retrieve them from the cloud at any time. If the Github cloud storage facility is destroyed, well then you still have them on your computer.  

Here the steps you should go through for at least each course you are if, if not distinctly for every assignment you complete. 

To start, create a subdirectory for using git from home directory, or your documents directory, or something similar. Call it "github". You need only do this once ever. Now that you did it, do the following.

1. Open Github Desktop and select "New Repository..."

1. 

# Starting the editor

There are many ways to interact with python. We are going to focus on using an editor to save files to your local disk and then running the files from a command line terminal. Some people swear by emacs and vi/vim. Another option is to use ipython. Here we are going to focus on Visual Studio Code (vscode, for short).

You can  It's generally the same for all platform. (The main difference is the shortcut keys used to do things quickly, like save or open files.)

Once you've downloaded and installed vscode, you'll see a screen like this:


Don't use vscode to open a file. Use it open a directory. Select "Open Folder" from the file menu. 

The  most important icon for us right now is on the top left: "Explorer" (two stacked documents). Once you start working on a project with multiple file, you can use "Search" icon to find a string in any of your project's files. But let's focus on the Explorer for now. 

Click it once and the list of files you are working with appear. Click it again, and the little side window goes away. 

# Installing third-party libraries with pip

# Using black to format your code

# Using isort to sort your imports

# Using flake to lint your code

# Advanced Topics

## Managing two projects with different requirements 

Your program will be written based on a specific version of Python. It may use features in, say, version 3.9 that are removed in version 3.10. Similarly, you might use a third-party library that might be upgraded in the future. Another problem is that you may be required to use Python 3.9 in one course and Python 3.6 in another course. In this section, we'll learn to set up separate "environments" for each project that ensure functionality is preserved and isolated. 

## Other linters

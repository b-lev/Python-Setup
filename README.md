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

Before you get stared, make sure you do the following steps, each once ever:
    - Create a subdirectory for using git from home directory, or your documents directory, or something similar. Call it "github". You need only do this once ever. 
    - Link Github Desktop to your GitHub account. To do that, go to "Preferences" and then select "Accounts" and then sign in your Github account. 

Now that you did it, do the following per project.

1. Open Github Desktop and select "New Repository..."

1. Enter the details. 
     - Any short name works. Perhaps for this "tutorial-example". 
     - Description is not important, leave it blank or fill it out. 
     - The *local path* should be the full path to your "github" subdirectory that you created already. 
     - Click the "initialize this repository with a README" because we want one.
     - For the "Git Ignore" dropdown menu, select "Python".
     - For "License" just leave it as "None" as we are going to create a private repository (i.e., one that the world can't access).

1. Publish your repository on github by clicking the "publish repository" button. (If you haven't linked your Github Desktop to your Github account using the preferences->accounts dialog, as I discussed above, this step won't work.)

1. Now a dialog window will show up, and you probably don't need to adjust anything. *Important* Make sure the box for "Keep this code private" is checked. If you are creating a repository for a course assignment, you would be violated academic honesty policies by making your code public.

Success! You should be to see your new repository on Github. 

# Starting the editor

There are many ways to interact with python. We are going to focus on using an editor to save files to your local disk and then running the files from a command line terminal. Some people swear by emacs and vi/vim. Another option is to use ipython. Here, we are going to focus on using Visual Studio Code (vscode, for short). Over time, your choice of editor will be a deep deliberate decision. It's akin to selecting a particular guitar to buy (acoustic or electric? single coil or humbuckers? etc.) in that it's a tool that let's perform at your best. VS Code has advanced features appropriate for professionals, but generally can be used by computer science students who don't need to go crazy with every single setting and plug-ins. 

VSCode generally operates the same for all operating systems. (The main difference is the specific shortcut keys used to do things quickly, like save or open files. And so I'm going to try and not specify the shortcut key press to make something happen. A very small bit of advice though is that as a programmer, you don't want to ever have to use a mouse or trackpad; they'll just slow you down.)

Once you've downloaded and installed vscode, you'll see a screen like this:

You might be tempted to use vscode to open up a new file. Don't use vscode to open a file. Instead, use it open a **directory**. Select "Open Folder" from the file menu and open up the directory containing the repository you've created for this tutorial.

The  most important icon for us right now is on the top left: "Explorer" (two stacked documents). There are some other icons on the left; let's just ignore them for now. 

Click on the Explorer icon once. The list of files you are working with appear. Click it again, and the little side window goes away. We haven't done anything yet, and so almost no files are there. 

This isn't a tutorial on how to program in python. And so I'm going to just give you a little bit of code to play with.  Follow these steps.

- From vscode's "File" menu, select "New File". It should create new tab called "Untitled-1". 
- Copy and paste the code below into the tab and save it to a file called "intro.py" in your repository. There are some weaknesses in this code. We are going to use some other tools to make it a little nicer in a minute.

    ```
    from random_words import RandomEmails
    from random_words import RandomNicknames
    import random, sys
    from pprint import pp
    def main():
        #create a dictionary of random nicknames
        roster = dict()
        random_nicknames = RandomNicknames()
        random_emails = RandomEmails()
        students = random_nicknames.random_nicks(count=10)
        for name in students:
            roster[name] = {"email": random_emails.randomMail(),"exam_score": random.randint(1, 100),"homework_score": random.randint(1, 100)        }

        pp(roster)
    if __name__ == "__main__":
        main()
    ```
Before you get this code to run, you'll need to install the randomwords library It doesn't come with python. 

# Installing third-party library with pip

Python ships with a large set of [standard libraries](https://docs.python.org/3.9/library/index.html). There a ton of high-quality third-party libraries available as well. (The source code for many such third partis is available on github, it turns out.) In the code above, you can see that I've used the random_words library. 

For any good third party library, there are typical two important websites: it's pypi.org page containing documentation and it's homepage. (It turns out that most of the time, the homepage for a library is typically github.) For random_words, they are:
    - documentation: https://pypi.org/project/RandomWords/
    - homepage: https://github.com/tomislater/RandomWords

Try to run our little python program. The intent is to create a Python dictionary of randomly chosen student details. You should get an error when you run it. Open a terminal, and change to the directory containing the repository and saved intro.py file:

```
% cd github/tutorial-example 
% python3.9 intro.py       
Traceback (most recent call last):
  File "/Users/brian/github/tutorial-example/intro.py", line 2, in <module>
    from random_words import RandomEmails
ModuleNotFoundError: No module named 'random_words'
```

I've been calling ```random_words``` a "library" and yet Python is complaining about a missing "module". What's the difference? A library is a loose term describing the project and its collection of files and such that perform some function. A module is a specific set of files that contain the code that instantiate or realize the library's goals. And so here Python is complaining that it can't find the files it needs to import ```random_words```. 

Installation is easy. For all libraries on pypi.org, there is a install command you can copy by clicking the little copy icon.  Paste into your terminal.

```
% pip install RandomWords
Collecting randomwords
  Using cached RandomWords-0.3.0-py3-none-any.whl
Installing collected packages: randomwords
Successfully installed randomwords-0.3.0
```
Note that the install name is different than the module name. Actually the uppercase and lowercase letters don't matter. The removal of the underscore is important. You can't do ```pip install random_words``` successfully. This difference exists for a sizeable number of libraries.

The command above will install the latest version of randomwords. If you want to install a specific version, you can do a double equals and the version number: ```pip install RandomWords==0.3.0```.

Now try to run the code. You should get something like this. Each time you run it, you'll get different output.
```
% python3.9 intro.py       
{'Marisol': {'email': 'irwin@from-europe.com',
             'exam_score': 65,
             'homework_score': 25},
 'Cherie': {'email': 'elena@arcor.de', 'exam_score': 77, 'homework_score': 46},
 'Mat': {'email': 'douglas@brazilmail.com.br',
         'exam_score': 61,
         'homework_score': 71},
 'Vonda': {'email': 'zoe@tropicalstorm.com',
           'exam_score': 27,
           'homework_score': 95},
 'Abbie': {'email': 'dominick@mail2biologist.com',
           'exam_score': 88,
           'homework_score': 10},
 'Edith': {'email': 'carol@mail2victoria.com',
           'exam_score': 40,
           'homework_score': 99},
 'Amber': {'email': 'sonya@levele.hu', 'exam_score': 7, 'homework_score': 74},
 'Rebecca': {'email': 'loretta@mail2composer.com',
             'exam_score': 75,
             'homework_score': 67},
 'Roanne': {'email': 'caoimhe@copacabana.com',
            'exam_score': 7,
            'homework_score': 58},
 'Mohammad': {'email': 'heaven@mail2cardinal.com',
              'exam_score': 67,
              'homework_score': 10}}
```

# Standardizing your source code

It's hard to sight read code. That is, it's hard to just look at code and read it as easily as you might read a book. It takes experience and talent. But even for reading prose books, we expect the presentation to follow certain conventions. Margins, chapter titles, larger and smaller fonts, the use of bold and italics, and separation of paragraphs with vertical space or indentations are helpful for comprehension, even if they aren't strictly part of engish grammar. 

The same is true for code. When we see code formatted in an expected fashion, it improves comprehension for the reader. And comprehension is really important for yourself (so that you don't miss bugs), for your TA (so that they can help you squash a bug), and for your professional colleagues (so that they build on your code and help you squash bugs).


# Using Black to format your code

There are style guides [out there](https://google.github.io/styleguide/pyguide.html) that can help you do that. I used to tell my students that they had to follow one style guide or another during the semester. But they are hard to ingest and incorporate consistently. 

A better way to format your code to ensure it meets a given style is to let a program format it for you. Black is one such formatter that I recommend. Here's it's pypi.org page (you know what to do to install it!): https://pypi.org/project/black/

Once you have it installed, you can run it as 

```
% black intro.py 
reformatted intro.py
All done! ✨ 🍰 ✨
1 file reformatted.

```

Or you can do it to every file in a directory. (Can you figure out how to hit all files in subdirectories too?)

```
% black *.py
```

It's important to note that Black will not reformat your python file if it contains a syntax error. 

Now intro.py should look like this:

```
from random_words import RandomEmails
from random_words import RandomNicknames
import random, sys
from pprint import pp


def main():
    # create a dictionary of random nicknames
    roster = dict()
    random_nicknames = RandomNicknames()
    random_emails = RandomEmails()
    students = random_nicknames.random_nicks(count=10)
    for name in students:
        roster[name] = {
            "email": random_emails.randomMail(),
            "exam_score": random.randint(1, 100),
            "homework_score": random.randint(1, 100),
        }

    pp(roster)


if __name__ == "__main__":
    main()
```

That's much nicer! The lines are not too wide. There is some standard spacing between the imports, functions, and the ```if __name__``` clause at the end. 

There is more we can do.




# Using isort to sort your imports

# Using flake to lint your code

# Advanced Topics

## Managing two projects with different requirements 

Your program will be written based on a specific version of Python. It may use features in, say, version 3.9 that are removed in version 3.10. Similarly, you might use a third-party library that might be upgraded in the future. Another problem is that you may be required to use Python 3.9 in one course and Python 3.6 in another course. In this section, we'll learn to set up separate "environments" for each project that ensure functionality is preserved and isolated. 

## Other linters

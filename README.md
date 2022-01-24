
- [Introduction](#Introduction)
- [Getting all the tools installed](#Getting-all-the-tools-installed)
- [Create a repository](Create-a-repository)
- [Starting the editor](#Starting-the-editor)
--[Installing third-party library with pip](#Installing-third-party-library-with-pip)
- [Add your code to git and pushing it to the cloud](#Add-your-code-to-git-and-pushing-it-to-the-cloud)
- [Standardizing your source code](#Standardizing-your-source-code)
- [Using isort to sort your imports](#Using-isort-to-sort-your-imports)
- [Using flake8 to lint your code](#Using-flake8-to-lint-your-code)
- [Running black, isort, and flake8 in VSCode](#running-black-isort-and-flake8-in-vscode)
- [Other Topics](#Other-Topics)


# Introduction
This page provides some general advice on how to set up your local environment to code proficiently with Python. These instructions are not the simplest way to set up your environment. These instructions are step toward how a professional might set up their environment. It's a foundation: from here you can keep adding new tools as you gain experience. 

In the examples below, we are going to focus on Python 3.9, and we'll give version numbers for all other tools so that you can avoid unexpected errors. 

All tools are free. (And I have no relationship with the third parties who have made the tools.)

## Learning python

There are many resources for learning python for the first time or for sharpening your skills.

- https://pythontutor.com
- https://swcarpentry.github.io/python-novice-inflammation/

# Getting all the tools installed

1. To get started with this tutorial, first make sure you have [Python installed](https://www.python.org/downloads/). Again, here I'm using Python version 3.9. Make sure you can access it from a command line. On windows I suggest you use a PowerShell window. On MacOS and Unix it's best to use a Terminal window. Once you have started the command line, type ```python``` at the prompt. You should see something like this:

    ```
    PS C:\Users\brian> python
    Python 3.9.5 (tags/v3.9.5:0a7dcbd, May  3 2021, 17:13:28) [MSC v.1928 32 bit (Intel)] on win32
    Type "help", "copyright", "credits" or "license" for more information.
    >>>
    ```
    
    Once you get a python prompt of ```>>>```, you are good. To quit you can type ```exit()``` and hit return. 

    The command to run it much be slightly different depending on how you installed it and what OS you are running. For example, on windows I've seen it installed as ```py.exe```. It's important that it says "3.9.5" or something close to that (like 3.9.9). The "3.9" is the important part. If you see anything else (like 2.7 or 3.10), you can try to start python with ```python3.9``` instead for example. 

1. Create an account on [github](https://github.com/join). There is no need to sign up for a paid plan. 


1. Download and install [github desktop](https://desktop.github.com). You can use git from a terminal, but this app is way easier.

1. Download and install [Visual Studio Code](https://code.visualstudio.com/Download) . 

# Create a repository 

There is no excuse for losing your files for a project or assignment. Nope, it's just not acceptable. You should never code such that your files aren't backed up elsewhere. One solution is to use tools that backup hourly or even every time you save a file. You could use Apple TimeMachine, or Crashplan, Dropbox, OneDrive, Box, and many more. Those solutions are useful, but they are not good enough to be used as tools for proper software engineering and completing assignments. Instead, we need to use a tool for *source control*. 

Git will be our software of choice for source control. Many tools for source control exist and git is just one of them. Now in reality, we aren't going to using git only --- we are going to use GitHub, which is Git coupled with cloud storage. (It's worth noting that the Github people didn't create git, but that's a story for another day.) The nice thing about Github is that if your home/computer/disk/files are destroyed, you can retrieve them from the cloud at any time. If the Github cloud storage facility is destroyed, well then you still have them on your computer don't you.

Here the steps you should go through for at least each course you are in, if not separately for every assignment you start. 

Before you get started, make sure you do the following steps, each once ever:

- Create a subdirectory for using git from home directory, or your documents directory, or something similar. Call it "github". You need only do this once ever. 
- Link Github Desktop to your GitHub account. To do that, go to "Preferences" and then select "Accounts" and then sign in your Github account. 

Now you are ready. Do the following per project or assignment that you start.

1. Open Github Desktop and select "New Repository...". You'll see this dialog.

<p align="center"><img src="images/create.jpg?raw=true" width="50%"></p>

1. Enter the details. 
     - Any short name works. For this demonstration use "tutorial-example". 
     - Description is not important, leave it blank or fill it out. 
     - The *local path* should be the full path to your "github" subdirectory that you created already. 
     - Click the box for "initialize this repository with a README" because we want a Readme file.
     - From the "Git Ignore" dropdown menu, select "Python".
     - Leave the  "License" dropdown menu selection as "None". We are going to create a private repository (i.e., one that the world can't access).

1. Publish your repository on github by clicking the "publish repository" button. (If you haven't linked your Github Desktop to your Github account using the preferences->accounts dialog, as I discussed above, this step won't work.)


<p align="center"><img src="images/publish.jpg?raw=true" width="50%"></p>



1. Now a dialog window will show up, and you probably don't need to adjust anything. *Important* Make sure the box for "Keep this code private" is checked. If you are creating a repository for a course assignment, **you would be violating academic honesty policies by making your code public**.

<p align="center"><img src="images/publish-dialog.jpg?raw=true" width="50%"></p>


Success! You should be to see your new repository on Github. Because the repository is private, you have to log in to see it. (But you are probably still logged in.)


# Starting the editor

There are many ways to interact with python. We are going to focus on using an editor to save files to your local disk and then running the files from a command line terminal.  In terms of editors, some people swear by emacs or vim. Another option is to use ipython. Here, we are going to focus on using Visual Studio Code (vscode, for short). Over time, your choice of editor will be a deep, deliberate decision. The choice is akin to selecting a particular guitar  (acoustic or electric? single coil or humbuckers? etc.) in that it's a tool that let's you perform at your best. VSCode has advanced features appropriate for professionals, but generally can be used by new computer science students without going crazy with every single setting and plug-in available. 

VSCode generally operates and looks just about the same for all operating systems. (The main difference is the specific shortcut keys used to do things quickly, for example to  save or open files. And so I'm going to try and not specify the shortcut key pressed to make something happen. But a very small bit of advice  is that as a programmer, you don't want to ever have to use a mouse or trackpad; they just slow you down.)

Once you've downloaded and installed vscode, you'll see a screen like this:

<p align="center"><img src="images/vscode-first-screen.jpg?raw=true" width="75%"></p>

You might be tempted to use vscode to open up a new file. Don't use vscode to open a file. Instead, use it open a **directory**. Select "Open Folder" from the file menu and open up the directory containing the repository you've created for this tutorial.

The  most important icon for us right now is on the top left: "Explorer" (two stacked documents). There are some other icons on the left; let's just ignore them for now. 

Click on the Explorer icon once. The list of files you are working with appear. Click it again, and the little side window goes away. We haven't done anything yet, and so almost no files are there. 

This isn't a tutorial on how to program in python. And so I'm going to just give you a little bit of code to play with and assume that you can basically follow what's going on.  

To get the code into your editor, follow these steps.

- From vscode's "File" menu, select "New File". It should create new tab called "Untitled-1". 
- Copy and paste the code below into the tab and save it to a file called "intro.py" in your repository. There are some weaknesses in this code. We are going to use some other tools to make it a little nicer in a minute.

    ```
    from random_words import RandomEmails
    from random_words import RandomNicknames
    import random, sys
    from pprint import pprint
    def main():
        #create a dictionary of random nicknames
        roster = dict()
        random_nicknames=  RandomNicknames()
        random_emails =RandomEmails()
        students =   random_nicknames.random_nicks(count=10)
        for name in students :
            roster[name] = {"email": random_emails.randomMail(),'exam_score': random.randint(1, 100),"homework_score": random.randint(1, 100)        }

        pprint(roster)
    if __name__ == "__main__":
        main()
    ```

At this point, if vscode asks if you want to install the "python extension", then yes definitely please do it. It might take a minute to install. 

Before you get this code to run, you'll need to install the randomwords library. It doesn't come with python. 

# Installing third-party library with pip

Try to run our little python program. The intent is to create a Python dictionary of randomly chosen student details.  Open a terminal, and change to the directory containing the repository and saved intro.py file. Then call python on the file. You should get an error when you run it.

```
% cd github/tutorial-example 
% python3.9 intro.py       
Traceback (most recent call last):
  File "/Users/brian/github/tutorial-example/intro.py", line 2, in <module>
    from random_words import RandomEmails
ModuleNotFoundError: No module named 'random_words'
```

Python ships with a large set of [standard libraries](https://docs.python.org/3.9/library/index.html). There a ton of high-quality third-party libraries available as well. (The source code for many  third party libraries is often stored  on github, it turns out.) In the code above, you can see that I've used the random_words library, but it's not installed on your computer yet. 

For any good third party library, there are typical two important websites: its pypi.org page containing documentation and its homepage. (It turns out that most of the time, the homepage for a library is typically github.) For random_words, they are:

- documentation: https://pypi.org/project/RandomWords/
- homepage: https://github.com/tomislater/RandomWords


I've been calling ```random_words``` a "library" and yet Python is complaining about a missing "module". What's the difference? A library is a loose term describing the project and its collection of files and such that perform some function. A module is a specific set of files that contain the code that instantiate or realize the library's goals. And so here Python is complaining that it can't find the files it needs to import ```random_words```. 

Installation is easy. For all libraries on pypi.org, there is a install command you can copy by clicking the little copy icon. 

 <p align="center"><img src="images/rw.jpg?raw=true" width="50%"></p>

Paste or type the following into your terminal. ```pip``` is a command that is installed with python. On some computers, you might have many versions of python installed. Just calling pip might install a library for a version of python that you aren't using. So to be safe, you can try using ```pip3.9 install ...```. If that's not installed (often the case on windows) then go ahead and use ```pip install ...```. You can also try ```py -m pip install...``` or ```python3.9 -m pip install...```

```
% pip3.9 install RandomWords
Collecting randomwords
  Using cached RandomWords-0.3.0-py3-none-any.whl
Installing collected packages: randomwords
Successfully installed randomwords-0.3.0
```
Note that the install name is different than the module name. Actually the uppercase and lowercase letters don't matter. The removal of the underscore is important. You can't do ```pip install random_words``` successfully. This difference exists for a sizeable number of libraries. A common pattern is that you would ```import foo``` in your code,  but you need to ```pip install pyfoo``` at the terminal.

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

# Add your code to git and pushing it to the cloud
Git is great because it will help you keep track of revisions to your code. Tracking sequence of revisions is pretty vital when you are coding with even one other person. It's also important when you are coding alone!

One of the most false or synthetic or non-representative parts of learning to code in any course is the typical process for completing an assignment. The instructor hands out an assignment; you spend a relatively short time doing it alone (really just a week or two); you get it to run correctly once; you submit; you never run the code again and you never use the code again.

In real life, projects last months or years. The goals of the project changes over time. The people involved change. You run it again and again and again. And you try to reuse the code in other projects. And there is old joke that for any real project there are always at least two people: yourself, and yourself three months from now. You have to learn to write and structure your code so that you can put it down and make sense of it three months later, as if you are a totally different person. 

Git and tools like it help you in that goal. If the above story isn't convincing, then in the very least, they are a solution to a problem that often comes up for new programmers: "This code worked a few minutes but I made some change, and I don't know what ... those changes broke it... I'm totally lost and I don't know how to get back to the working version."

Lastly, git will help you break your coding up into management micro-goals. When you code, consider the micro-goal you want to achieve. Maybe your goal is to write a method that saves some data to a file. Once the function seems to be working correctly, then tell git about your progress as a *commit* to the repository. To be clear, commit the source code is very different than saving it to your local file system.

To show you how to commit, we are going to commit the code you pasted above into intro.py.

- Open Github Desktop
- Make sure you are in our new repository. It should be listed in the top left of the window.
- You should see intro.py listed with a check box. Make sure it is checked. It should be the only file checked of anything listed. (mac users might see a pesky .DS_store file listed.)
- Github Desktop tries to be helpful here by putting in a comment for us. It won't do that if you check in more than one file.
- Notice the green plus. It's a visual indication that we are adding a file to the list that git will track for us.
- Click the blue "Commit to main" button. 
- Lastly, you need to click the grey "Push origin" button, which means "store this in the cloud".

That's it! You pushed your first commit!

<p align="center"><img src="images/add-intro-py.jpg?raw=true" width="50%"></p>

<p align="center"><img src="images/push.jpg?raw=true" width="50%"></p>


# Standardizing your source code

It's hard to sight read code. That is, it's hard to just look at code and read it as easily as you might read a book. It takes experience and talent. But even for reading prose books, for which we are all experts by now, we expect the presentation to follow certain conventions: reasonably wide margins, chapters numbered with titles and larger fonts, the use of bold and italics for emphasis, and the [separation of paragraphs](images/ducks.jpg?raw=true) with vertical space or indentations are all helpful for comprehension, even if they aren't strictly part of english grammar. 

The same is true for code. When we see code formatted in an expected fashion, it improves comprehension for us as the reader. And comprehension is really important for yourself (so that you don't miss bugs), for your TA (so that they can help you squash a bug), and for your professional colleagues (so that they build on your code and help you squash bugs).


## Using Black to format your code

There are style guides [out there](https://google.github.io/styleguide/pyguide.html) that can help you format your code to common expectations and styles. I used to tell my students that they had to follow one style guide or another during the semester. But they are hard to ingest and incorporate consistently. 

A better way to format your code to ensure it meets a given style is to let a program format it for you. Black is one such formatter that I recommend. Here is its pypi.org page (you know what to do to install it!): https://pypi.org/project/black/

Once you have it installed, you can run it as 

```
% black intro.py 
reformatted intro.py
All done! ✨ 🍰 ✨
1 file reformatted.

```

Or you can do it to every file in a directory. (Can you figure out how to hit all files in subdirectories?)

```
% black *.py
```

It's important to note that Black will not reformat your python file if it contains a syntax error. 

Now intro.py should look like this:

```
from random_words import RandomEmails
from random_words import RandomNicknames
import random, sys
from pprint import pprint


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

    pprint(roster)


if __name__ == "__main__":
    main()
```

That's much nicer! The lines are not too wide. There is some standard spacing between the imports, functions, and the ```if __name__``` clause at the end. It changed the single quotes around ```exam_score``` to use double quotes so that it's consistent with the other lines. It even put a space between ```#``` and the comment. Again, before we had a legit Python program that ran correctly. But now we have source that is equivalent and easier to read.

Black is so useful that I promise you that once you start using it consistently, you'll realize how crazy your life was before. You will get annoyed at code that hasn't been sent through Black, because it's so much more readable after it has been sent through Black. 

There is more we can do to clean up our code, but let's pause for a minute and talk about git/github again. 



# Check in changes to github

Github Desktop has a nice display of the differences you've made to your code with black. That's so very convenient! It's probably obvious that red means "removed" and green means "added". 

<p align="center"><img src="images/after-black.jpg?raw=true" width="100%"></p>

Your view of these differences (which is often called the "diff" after the command that generates this view) may look slightly different. Note that I have these settings configured for Github Desktop: 

<p align="center"><img src="images/github-split.jpg?raw=true" width="50%"></p>

I will caution you that this diff is correct roughly 96.53% of the time. Sometimes the diff is just wrong for complicated changes where code is rearranged heavily. These are pretty straightforward changes and the diff is correct. 

# Using isort to sort your imports

Black doesn't do it all. Look at those import statements. Do you see the problem? Probably not. Let's run our program source code through [isort](https://pypi.org/project/isort/). Please install it with pip, and then do the following.

```
% isort --profile black intro.py
Fixing /Users/brian/github/tutorial-example/intro.py
```
(Notice that I included an argument for ```-profile black``` so that isort is compatible with black.)

Just like black, isort changes the source code only if there isn't a syntax error and it makes changes only if it doesn't change the how the program runs. All isort does is sort and group together imports: imports from Python's standard library are first, then a new line, and then a group of libraries that have been installed with pip (or were locally created). Now our source code looks like so:

```
    import random
    import sys
    from pprint import pprint

    from random_words import RandomEmails, RandomNicknames


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

        pprint(roster)


    if __name__ == "__main__":
        main()
```
You'll notice that isort also separated each import into its own line (before random and sys) were together. And it combined all the imports from random_words into one statement. That's clearer formatting for the reader.

Here's the diff of what isort did. Over time, you'll get pretty good at reading diffs. 

<p align="center"><img src="images/after-isort.jpg?raw=true" width="100%"></p>

## Using flake8 to lint your code

A *linter* is a program that examines your source code for bad style or errors, and it checks for things in a wide range of categories. The first linter was called [lint](https://en.wikipedia.org/wiki/Lint_(software)) and was written in 1978! 

[Flake8](https://pypi.org/project/flake8/) (pronounced "flay-kate") is one such linter. It's pretty aggressive and exacting. And I think especially for a beginning programmer, you'll waste a lot of time trying to get rid of all the flake8 *warnings*. So for now, let's just focus on flake8 *errors*. 

I've installed version 4.0.1. Recall that you can install a specific version like so:

```% pip install flake8==4.0.1
```
After you pip install it, run it with these arguments to show only the errors:

```% flake8 --select=F intro.py
intro.py:2:1: F401 'sys' imported but unused
```

Ah ha! Did you notice that we imported ```sys``` but it wasn't used in our code. That's ugly. Flake8 won't fix that problem --- you need to make the change yourself in vscode to fix it.  If you do that and save the file, you'll note that when you run flake8 again, it won't complain. It doesn't congratulate you for having no errors in the friendly way that Black does. 

Here's the diff from making this change. 
<p align="center"><img src="images/after-flake8.jpg?raw=true" width="100%"></p>

## Looking back and old commits

Did you try switching on the history tab? You should be able to see each commit you've made during the tutorial. For each commit, you can see diff against the previous commit. Notice in this screen grab, my most recent commit has an up arrow --- that means I haven't push to the cloud yet. 

<p align="center"><img src="images/commit.jpg?raw=true" width="50%"></p>

# Running black, isort, and flake8 in VSCode

This is a great set of tools. And you have the option of running them when you are done with a project, intermittently while you code, or as much as possible. It turns out that the best option is to run them as much as possible. But no one wants to save a file and then switch to the terminal, run the three commands, and then switch back to the editor. That's terribly inefficient. 

Let's instead of configure vscode to run the three tools each time we save our source code. Now, VSCode makes this a little intimidating because there isn't a menu option to do it. So we'll need to take a few steps. 

First, if you haven't already, install the "python extension". One way to do that is to visit [this page](https://marketplace.visualstudio.com/items?itemName=ms-python.python) and click the green install button.

There are a few tutorials for doing this online, but I don't know that they are helpful for beginners. If you know what you are doing already, and you are comfortable messing around with JSON, then probably you are experienced enough to find these tutorials. (Just search for "isort black vscode"). Let's get this working without the chance of breaking your installation of vscode. 

One thing you should do to get started is to check that vscode can run python for you. From the "Terminal" menu at the top, select "New Terminal". You should end up with a prompt: a powershell prompt if you are windows, and a terminal prompt if you are on windows or linux. From the prompt, run python just as you did outside of vscode. It should work just the same. (If not, something is wrong. For example, if you opened this terminal and then installed python, perhaps close the vscode terminal and try again.)

Make sure intro.py is open and switch to that tab. Look in the bottom left corner. Do you see Python 3.9 listed? Click whatever text is there. (It may ask you to end the path for python. Enter exactly what you entered to run python in the vscode terminal. and then look again.) If it gives you some specific versions of python to chose from --- that's great --- pick version 3.9 something. Here I've got 3.9.10 selected. 

<p align="center"><img src="images/corner.jpg?raw=true" width="50%"></p>

Next hit the "gear" icon and select "Settings".

<p align="center"><img src="images/settings.jpg?raw=true" width="50%"></p>

In the search bar that comes up, type "python" and then you should see "Python" listed below as something you can select.

<p align="center"><img src="images/python-search.jpg?raw=true" width="75%"></p>

Scroll down until you see "Python Formatting Provider" and select "black" from the drop down menu.
<p align="center"><img src="images/vsc-black.jpg?raw=true" width="75%"></p>

If you after you make this choice, vscode asks you install black, then certainly let it do that. 

Scroll down more until you see the configuration for linting and select these options.
<p align="center"><img src="images/vsc-linting.jpg?raw=true" width="75%"></p>
<p align="center"><img src="images/vsc-flake8.jpg?raw=true" width="75%"></p>
<p align="center"><img src="images/vsc-lint-on-save.jpg?raw=true" width="75%"></p>

# Other Topics

To be written. 

## Debugging with pdb

To be written. 

## Managing two projects with different requirements 

Your program will be written based on a specific version of Python. It may use features in, say, version 3.9 that are removed in version 3.10. Similarly, you might use a third-party library that might be upgraded in the future. Another problem is that you may be required to use Python 3.9 in one course and Python 3.6 in another course. You really need set up separate "environments" for each project that ensure functionality is preserved and isolated. You can do this with virtual environments and ```venv```.

To be written. 

## Other Tools

- [doctest](https://docs.python.org/3/library/doctest.html) The doctest module searches for pieces of text that look like interactive Python sessions, and then executes those sessions to verify that they work exactly as shown.
- [pylint](https://pylint.org) Pylint is a Python static code analysis tool which looks for programming errors, helps enforcing a coding standard, sniffs for code smells and offers simple refactoring suggestions.
- [pydocstyle](https://pypi.org/project/pydocstyle/). pydocstyle is a static analysis tool for checking compliance with Python docstring conventions.
- [pyright](https://github.com/Microsoft/pyright). Pyright is a fast type checker meant for large Python source bases. It can run in a “watch” mode and performs fast incremental updates when files are modified.
- [hypothesis](https://hypothesis.readthedocs.io/en/latest/). A Python library for creating unit tests which are simpler to write and more powerful when run, finding edge cases in your code you wouldn’t have thought to look for.
- [scalene](https://pypi.org/project/scalene/) Scalene is a high-performance CPU, GPU and memory profiler for Python that does a number of things that other Python profilers do not and cannot do. It runs orders of magnitude faster than other profilers while delivering far more detailed information.

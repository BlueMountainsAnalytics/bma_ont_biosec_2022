# CLI Tutorial Answers

## CLI Introduction

### Self-Check 1

#### What does CLI stand for? 

Command-Line Interface

#### What command tells you your current location on the CLI?

Command **pwd** (short for *print working directory*)

#### With what command do you change into another directory?

Command **cd** (short for *change directory*)

#### Can you think of way to change into the parent directory  other than using the command *cd ..*?

In contrast to using the  **relative path** with **..**, which basically means "one directory up from where I am at the moment" you could use the **absolute path**. To do this you could use the command **pwd** to get the current location and remove the last part of the **absolute** bath. 

    john> pwd
    /homes/john/data
    john> cd /homes/john
    john> pwd
    /homes/john


<p align="left"><a href="https://bluemountainsanalytics.github.io/BMA_CLI-tutorial/INTRO_3.html">BACK =></a>
</p>


### Self-Check 2

#### How do you list the content of your current directory?

With command **ll** (short for *long list*).

#### Which column of the **ll** output shows the size of a file ?

Column 6 of the **ll** output shoes the size of the file.

#### How do you create a directory ?

Use the command **mkdir PATH_TO_DIRECTORY** where *PATH_TO_DIRECTORY* is the relative or absolute path to the directory you want to create.

Example using relative paths
    tim$ mkdir my_new_directory

This will create a new directory called *my_new_directory* in my current location

Example using *absolute paths*:
    tim$ mkdir /Users/tim/my_new_directory

This will create the new directory *my_new_directory* in the directory */Users/tim*

#### How do you add a **flag** to a command?

Flags... 

<ol>
  <li>... are added just after the command and before the arguments of the command</li>
  <li>... start with one or sometimes two hyphens</li>
  <li>... sometimes need arguments just like commands themselves</li>
</ol>

#### How to you list the first 5 lines of a file?

Use the command **head** with the **-n** flag to specify the number of lines the command should print

    john> head -n 5 FILE_NAME

<p align="left"><a href="https://bluemountainsanalytics.github.io/BMA_CLI-tutorial/INTRO_4.html">BACK =></a>
</p>

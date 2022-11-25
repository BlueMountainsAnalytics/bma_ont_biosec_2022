# Command Line - Commands 

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](INTRO_3.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](CONDA_1.md)

## Commands, arguments, and flags

We have already used several different command line commands, e.g. **pwd** and **cd**. The difference between these two commands is that **pwd** is run without anything whereas **cd** can have additional, e.g. the name of the directory which we want to change into. Many different command line commands expect arguments, e.g. the command **mkdir** (short for *make directory*) can be used to create a new directory. It expects the *name of the new directory* as an argument:


    course_user> ll
    drwxr-xr-x  2  course_user  staff   68  17  Jul  10:32  Files
    drwxr-xr-x  2  course_user  staff   68   2  Oct   2020  Workshops
    drwxr-xr-x  2  course_user  staff   68  22  Feb  14:02  meeting_notest
    -rw-r--r--  1  course_user  staff  152  17  Jul  10:32  sequences.fasta
    -rw-r--r--  1  course_user  staff 1551  17  Jul  10:32  to-do.txt
    course_user> mkdir ./new_directory
    course_user> ll
    drwxr-xr-x  2  course_user  staff   68  17  Jul  10:32  Files
    drwxr-xr-x  2  course_user  staff   68   2  Oct   2020  Workshops
    drwxr-xr-x  2  course_user  staff   68  22  Feb  14:02  meeting_notest
    drwxr-xr-x  2  course_user  staff   68  30  Nov  11:13  new_directory
    -rw-r--r--  1  course_user  staff  152  17  Jul  10:32  sequences.fasta
    -rw-r--r--  1  course_user  staff 1551  17  Jul  10:32  to-do.txt
   
As you can see in the output of **ll** there is now a new directory called *new_directory*. Similarly, we can remove a directory with the command **rmdir** (short for *remove directory*) and give *the name of the directory to remove* as an argument:

    course_user> ll
    drwxr-xr-x  2  course_user  staff   68  17  Jul  10:32  Files
    drwxr-xr-x  2  course_user  staff   68   2  Oct   2020  Workshops
    drwxr-xr-x  2  course_user  staff   68  22  Feb  14:02  meeting_notest
    drwxr-xr-x  2  course_user  staff   68  30  Nov  11:13  new_directory
    -rw-r--r--  1  course_user  staff  152  17  Jul  10:32  sequences.fasta
    -rw-r--r--  1  course_user  staff 1551  17  Jul  10:32  to-do.txt
    course_user> rmdir ./new_directory
    course_user> ll
    drwxr-xr-x  2  course_user  staff   68  17  Jul  10:32  Files
    drwxr-xr-x  2  course_user  staff   68   2  Oct   2020  Workshops
    drwxr-xr-x  2  course_user  staff   68  22  Feb  14:02  meeting_notest
    -rw-r--r--  1  course_user  staff  152  17  Jul  10:32  sequences.fasta
    -rw-r--r--  1  course_user  staff 1551  17  Jul  10:32  to-do.txt

<div style="background-color:#fcfce5;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon info height:32 class:"right left" aria-label:hi %}
  <b>Command <i>rmdir</i></b><br>
  The command <b>rmdir</b> only removes <i>empty</i> directories! To remove directories that are not empty one would have to first delete all the files in the directory or use the command <b>rm</b> (see below for more on this command)
</div>

Besides arguments the behavior of many commands can be altered by calling them with specific options, also called *flags*. In contrast to arguments, flags start with one or sometimes two hyphens. For example, to remove a file we can use the command **rm**, which expects as argument the relative or absolute path to the file that should be removed. To remove the file *sequences.fasta* in our directory we can type

    course_user> rm ./sequences.fasta
    course_user> ll
    drwxr-xr-x  2  course_user  staff   68  17  Jul  10:32  Files
    drwxr-xr-x  2  course_user  staff   68   2  Oct   2020  Workshops
    drwxr-xr-x  2  course_user  staff   68  22  Feb  14:02  meeting_notest
    drwxr-xr-x  2  course_user  staff   68  30  Nov  11:13  new_directory
    -rw-r--r--  1  course_user  staff 1551  17  Jul  10:32  to-do.txt

However, if we try to remove a directory, e.g., the directory *./Files*, we will get a notice that *Files is a directory*: 

    course_user> rm ./Files
    rm: Files/: is a directory

To remove a directory using the **rm** command we have to add the flag **-r**, which stands for *recursive*. This will first remove all the contents of the directory *recursively*, i.e., one after the other, and then delete the directory itself:

    course_user> rm -r ./Files
    course_user> ll
    drwxr-xr-x  2  course_user  staff   68   2  Oct   2020  Workshops
    drwxr-xr-x  2  course_user  staff   68  22  Feb  14:02  meeting_notest
    drwxr-xr-x  2  course_user  staff   68  30  Nov  11:13  new_directory
    -rw-r--r--  1  course_user  staff 1551  17  Jul  10:32  to-do.txt

<div style="background-color:#fcfce5;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon info height:32 class:"right left" aria-label:hi %}
  <b>Use rm with care!</b><br>
  In contrast to the <i>Move to Recycle Bin</i> option that can be found on Windows, OSX, or the GUI of linux operating systems like Ubuntu, the command-line does not have a Recycle Bin.<br>
  <b><u>Files and directories removed with <i>rm</i> are gone and can't be recovered!!</u></b>
</div>


The **-r** flag of **rm** is used without any arguments, it acts like a switch for the behavior of **rm**. However, some flags also expect arguments. 

Lets have a look at the command **head**. This command can be used to show the first lines of a text file. It expects the path to the file of interest as the argument and if no options are specified, it prints the first 10 lines of the specified file to the command line. Let’s have a look at the first 10 lines of the file *to-do.txt* in our current working directory using **head**:

    course_user> head ./to-do.txt
    - analyse data
    - publish article
    - meeting at 12:00pm
    - write tutorial
    - write emails
    - read papers
    - meeting with Benjamin re Nanopore course
    - save the world
    - have afternoon tea
    - go home

As you can see *course_user* still has a few things to do before they can go home. If we only want to list a specified number of lines using head we can do so by using the *–n* flag of **head** and pass the number of lines we want to be listed as a parameter:

    course_user> head -n 3 ./to-do.txt
    - analyse data
    - publish article
    - meeting at 12:00pm

Thus, a CLI command consists of

<ul>
  <li>the command itself</li>
  <li>zero, one or more flags (optional)</li>
  <li>flag arguments (where applicable)</li>
  <li>arguments (where applicable)</li>
</ul>


<div style="background-color:#cfedfe;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon question height:32 class:"right left" aria-label:hi %}
  <b>Self-Check 2</b>

  <ol>
    <li>How do you list the content of your current directory?</li>
    <li>Which column of the ls output shows the size of a file?</li>
    <li>How do you create a directory?</li>
    <li>How do you add an option to a command?</li>
    <li>How do you list the first 5 lines of a file?</li>
  </ol>
</div>
[Answers](INTRO_ANS.md#self-check-2) 

<p align="right"><a href="https://bluemountainsanalytics.github.io/BMA_CLI-tutorial/CONDA_1.html">CONTINUE -></a></p>

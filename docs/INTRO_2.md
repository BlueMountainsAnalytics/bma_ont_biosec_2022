# Command-line Navigation

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](INTRO_1.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](INTRO_3.md)

When first opening a command-line or *terminal* you will see a screen that looks something like this
 
    course_user> _
    
It shows your login name, *course_user*, as well as maybe the name of the computer you are using followed by some character that indicates where you can start to type commands. In the above example it is the character **>** but it might also be a **$** or **#**. This is followd by a full square or an underscore that indicates where in the line you currently are, i.e., where the next typed character will appear.


## Location, location, location

When working with a command line it is useful to keep in mind that a its purpose is identical to that of a GUI: show the user the different programs, files and directories on a computer and provide an interface to interact with it. The difference is simply how they do it. With a GUI, e.g., on Windows, you start on the *Desktop* with all the different folders and files shown as icons. To find out what directory you are in when using the command line, i.e., to get your current location, one has to type a specific command.

Let’s start with the location. To see in which directory we are in at the moment we can type the command **pwd** (short for print working directory) which prints out the current location:

    course_user> pwd
    /homes/course_user
    course_user>

The command printed our current location, */Users/course_user* followed by a new line where we can type the next command.

On my laptop the same command output looks like this:

<img src="figures/intro_3.png" height="140px">

As you can see in the example above the so called **path** to the current directory is */Users/tim*. The */* symbols in a path denote a directory: thus */Users/tim* indicates that we are in directory */tim* which is a subdirectory of directory */Users*.

<div style="background-color:#fcfce5;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon info height:32 class:"right left" aria-label:hi %}
  <b>Your <i>home</i> directory</b><br>
  The default directory a user starts in after the login is also called the <i>home directory</i> of a user. It is usually named after the user (hence the <i>/tim</i> directory).  On Apple systems all home directories are found in the <i>/Users</i> directory. On Unix-based systems such as Ubuntu the home directories are usually located in  <i>/homes</i>.
</div>

Now that we know where we are lets try to change into another directory. For example, let’s say we know that there is a directory */data* in our home directory. To change into the data directory we use the command **cd** (short for *change directory*) followed by the location of the directory we want to change into. 


    course_user> cd ./niosec_course
    course_user> pwd
    /homes/course_user/biosec_course
    course_user>

The **./** before the **data** tells the command-line to look in our current directory. You could also just type **cd data**, however it is good practice to use explicit "in this directory".

When we use the **pwd** command to check that we actually changed into the *data* directory the output shows */homes/course_user/biosec_course* as our new location. This **path** is called the **absolute path** of the *data* directory. In contrast we only used the **relative path** for the cd  command, i.e., **./data**. Relative paths are given relative to the current working directory, i.e., the directory we are currently in. Additionally, relative paths do NOT start with a *“/”* but either without a slash or using the **./** notation.

In contrast to relative paths **absolute paths** specify a directory regardless of the current working directory. This means that we can change into the *./data* directory from anywhere by using its absolute path. Absolute paths ALWAYS start with a **/** which denotes the lowest possible directory on a computer, the **root directory**. So, instead of using the relative path we could also change into the *./data* directory from anywhere by typing

    course_user> cd /homes/course_user/biosec_course
    course_user> pwd
    course_user> /homes/course_user/biosec_course
    course_user>

However, typing the absolute path whenever you want to change into a directory can be tedious, hence the **./** notation for relative paths. There are three more special ways of how to use the **cd** command:

  <ol>
    <li>cd ..</li>
    <li>cd</li>
    <li>cd -</li>
  </ol>

The first one, **cd ..** uses the dot-notation to change into the directory above this one, the so called **parent directory**, without having to type the absolute path:

    course_user> pwd
    /homes/course_user/biosec_course
    course_user> cd ..
    course_user> pwd
    /homes/course_user

The second one, the **cd** command on its own, will always change into the users home directory, regardless of our current location:

    course_user> pwd
    /homes/course_user/biosec_course/qc_practical
    course_user> cd
    course_user> pwd
    /homes/course_user

The third command, **cd -** will change back to the directory we just came from:

    course_user> pwd
    /homes/course_user/biosec_course/qc_practical
    course_user> cd 
    course_user> pwd
    /homes/course_user
    course_user> cd -
    course_user> pwd
    /homes/course_user/biosec_course/qc_practical




<div style="background-color:#cfedfe;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon question height:32 class:"right left" aria-label:hi %}
  <b>Self-Check 1</b>

  <ol>
    <li>What does CLI stand for?</li>
    <li>What command tells you your current location on the CLI?</li>
    <li>With what command do you change into another directory?</li>
    <li>Can you think of way to change into the parent directory  other than using the command <i>cd ..</i>?</li>
  </ol>
</div>
[Answers](INTRO_ANS.md#selfcheck1)
<p align="right"><a href="https://bluemountainsanalytics.github.io/bma_ont_biosec_2022/INTRO_3.html">CONTINUE -></a>
</p>


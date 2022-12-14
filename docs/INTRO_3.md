# Command Line - Files and Directories

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](INTRO_2.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](INTRO_4.md)


## Where are my files?

Now that we are able to navigate on the command line the next question is: how do I find out what files are in my directory? 
To view the content of a directory use the command **ll** (short for long list, i.e., a long version of the default command **ls** = list) which shows one line per file, program or directory in the specified location:

    course_user> ll
    d rwxr-xr-x  2  course_user  staff   68  17  Jul  10:32  Files
    d rwxr-xr-x  2  course_user  staff   68   2  Oct   2020  Workshops
    d rwxr-xr-x  2  course_user  staff   68  22  Feb  14:02  meeting_notest
    - rw-r--r--  1  course_user  staff  152  17  Jul  10:32  sequences.fasta
    - rw-r--r--  1  course_user  staff 1551  17  Jul  10:32  to-do.txt

Wow, ok, we can see that there are a lot of things in there. Let’s  take a closer look: first of all we see that the output of **ll** consists of ten columns:

    1     2      3   4      5     6   7    8     9     10
    d rwxr-xr-x  2  course_user  staff   68  17  Jul  10:32  Files
    d rwxr-xr-x  2  course_user  staff   68   2  Oct   2020  Workshops
    d rwxr-xr-x  2  course_user  staff   68  22  Feb  14:02  meeting_notest
    - rw-r--r--  1  course_user  staff  152  17  Jul  10:32  sequences.fasta
    - rw-r--r--  1  course_user  staff 1551  17  Jul  10:32  to-do.txt


<div style="background-color:#fcfce5;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon info height:32 class:"right left" aria-label:hi %}
  <b>Explanation of ll output</b>

  <ol>
    <li>Type, d = directory, - = file</li>
    <li>Access rights,ie., who is allowed to read (r), write (w) or execute the file/directory.</li>
    <li>Link Count</li>
    <li>Owner of the file/directory</li>
    <li>Group the file/directory belongs to</li>
    <li>Size in bytes</li>
    <li>Day it was created/last modified</li>
    <li>Month it was created/last modified</li>
    <li>Time (if this year) or year it was created/last modified</li>
    <li>Name of the file/directory</li>
  </ol>
</div>

For beginners, the columns of most importance are usually

  <ul>
    <li>1 - Is it a file or a directory?</li>
    <li>4 - Who does the file belong to?</li>
    <li>6 - How big is a file?</li>
    <li>10 - What is the name of the file/directory?</li>
  </ul>

Many CLIs also distinguish the type of a directory item by colour: directories are shown in blue, files in black. For example, the same directory structure on my laptop looks like this:

<img src="figures/intro_7.png" height="120px">

Also, as you can see, the first two columns often look like one column.

With this knowledge we can now properly interpret the output of ll of our current working directory:

  <ul>
    <li>It contains 3 directories: <i>Files</i>, <i>Workshops</i>, and <i>meeting_notest</i></li>
    <li>It contains 2 files: <i>sequence.fasta</i>, and <i>to-do.txt</i></li>
    <li>All files were created by me  (user <i>tim</i>)</li>
    <li>The file <i>sequences.fasta</i> is 251 bytes and file <i>to-do.txt</i> is of size 1551 bytes</li>
  </ul>

<p align="right"><a href="https://bluemountainsanalytics.github.io/bma_ont_biosec_2022/INTRO_4.html">CONTINUE -></a></p>


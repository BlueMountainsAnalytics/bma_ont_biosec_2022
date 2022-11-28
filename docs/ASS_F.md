# Genome assembly using Flye

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](ASS_M.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](ASS_ERR.md)

Another very popular assembler that can be used for long-reads such as PacBio and Oxford Nanopore is *Flye*. In contrast to the minimap and miniasm pipeline Flye also produces a polished consensus sequence for the assembly which significantly reduces the error rate.

Change into the *flye* directory in the *assembler_practical* folder and run flye on the filtered read fastq file. 

    course_user> flye --nano-raw \
    course_user> ~/biosec_course/qc_practical/filtered.fastq \
    course_user> --genome-size 3m --out-dir ./flye_output

<div style="background-color:#fcfce5;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon info height:32 class:"right left" aria-label:hi %}
  In most cases Flye does not require reads to be pre=processed, i.e., we could use the fasq file of unfiltered reads. However, to make the output of Flye more comparable to Miniasm we use teh same input file for this example.
</div>

As you can see, flye requires the input reads (--nano-raw) as well as an output directory and the (expected) size of the final assembly which, in this case is set to 3 megabases (3,000,000 bases) which we estimate from the *B. fermentans* genome. The output of Flye are several files including the assembly in fasta format.

<div style="background-color:#fcfce5;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon info height:32 class:"right left" aria-label:hi %} 
  Flye takes significantly more time and resources to run. On an average laptop this assembly may take 20 minutes and more. If you don’t want to wait just stop flye (press 'Ctrl-c') and copy the provided result files from directory <i>~/biosec_course/misc/flye_output</i> into the <i>flye_output</i> directory using <br><i>cp ~/biosec_course/misc/flye_output/* ./flye_output</i>.
</div>

When Flye is finished use *assembly-stats*  to get a first overview over the finished assembly.

<div style="background-color:#cfedfe;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon question height:32 class:"right left" aria-label:hi %} 
  <ol>
    <li>Does the assembly differ from the miniasm assembly, e.g., wrt total length, number of contigs and length of the contigs?</li>
  </ol>
 </div>
[Answer](APP_ANS.md#genome-assembly-using-flye)
 
Now change back into the *assembly_practical/flye* directory abd align the flye assembly to the B. fermentans genome using dnadiff
 
    course_user> dnadiff -p flye_dnadiff \
    course_user> ~/biosec_course/misc/assembly_practical/b_fermentans.fna \
    course_user> flye_output/assembly.fasta

Open the flye_dnadiff.report file (e.g. double-click on the file). 

<div style="background-color:#cfedfe;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon question height:32 class:"right left" aria-label:hi %} 
  <ol start="2">
    <li>How many contigs aligned with the reference? What is the error rate?</li>
  </ol>
</div>
[Answer](APP_ANS.md#2-how-many-contigs-aligned-with-the-reference-what-is-the-error-rate) 

<p align="right"><a href="https://bluemountainsanalytics.github.io/bma_ont_biosec_2022/ASS_ERR.html">CONTINUE -></a>
</p>

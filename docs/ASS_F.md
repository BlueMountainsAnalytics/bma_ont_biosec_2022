# Genome assembly using Flye

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](ASS_M.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](ASS_ERR.md)

Another assembler that can be used for long-reads such as PacBio and Oxford Nanopore is Flye. In contrast to the minimap and miniasm pipeline Flye also produces a polished consensus sequence for the assembly which significantly reduces the error rate.

Change into the *flye* directory in the *assembler_practical* folder and run flye on the **unfiltered** read fastq file. 


    flye --nano-raw \
    ~/biosec_course/qc_practical/filtered.fastq \
    --genome-size 3m --out-dir ./flye_output

<div style="background-color:#fcfce5;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon info height:32 class:"right left" aria-label:hi %}
  In most cases Flye does not require reads to be pre=processed, i.e., we could use the fasq file of unfiltered reads. However, to make the output of Flye more comparable to Miniasm we use teh same input file for this example.
</div>

As you can see, flye requires the input reads (--nano-raw) as well as an output directory and the (expected) size of the final assembly which, in this case is set to 3 megabases (3,000,000 bases). The output of flye are several files including the assembly in fasta format.

<div style="background-color:#fcfce5;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon info height:32 class:"right left" aria-label:hi %} 
  Flye takes significantly more time and resources to run. On an average laptop this assembly may take 20 minutes and more. If you don’t want to wait just stop flye (press the 'Ctrl' and 'c' keys at the same time) and copy the provided result files from directory <i>~/biosec_course/misc/flye_output</i> into the *flye_output* directory here.
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
 
    dnadiff -p flye_dnadiff \
    ~/biosec_course/misc/b_fermentans.fna \
    flye_output/assembly.fasta

Open the flye_dnadiff.report file (e.g. double-click on the file). 

<div style="background-color:#cfedfe;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon question height:32 class:"right left" aria-label:hi %} 
  <ol start="2">
    <li>How many contigs aligned with the reference? What is the error rate?</li>
  </ol>
</div>
[Answer](APP_ANS.md#2-how-many-contigs-aligned-with-the-reference-what-is-the-error-rate) 

<p align="right"><a href="https://bluemountainsanalytics.github.io/BMA_CLI-tutorial/ASS_ERR.html">CONTINUE -></a>
</p>

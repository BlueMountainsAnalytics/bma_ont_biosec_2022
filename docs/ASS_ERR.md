# Error Correction using Medaka 

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](ASS_F.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](ASS_BUSC.md)

*Error correction* and *polishing* are methods to reduce the number of errors in your assembly that come from the relatively noise long-read Oxford Nanopore reads. Althouh Oxford Nanopore reads have constantly improved in sequencing quality they still contain more sequencing/basecalling errors than for example Illumina short reads.

Different algorithms exist for error reduction, including signal-based tools like [NanoPolish](https://github.com/jts/nanopolish), and read-based tools like [Racon](https://github.com/isovic/racon) and [Medaka](https://github.com/nanoporetech/medaka). Often several polishing tools are combined, e.g., 3 rounds of Racon and one round of Medaka. 

Here, we will use Medaka on the Miniasm and Flye assemblies and see how they perform. 

## Error correction of the miniasm assembly

Change in the *miniasm-minimap* directory int he *assembler_practical* directory and call the tool *medaka_consensus* on the miniasm.fasta. The read sequences in the  *filtered.fastq* file will be used by medaka to infer sequencing errors to be corrected. In addition to the reads and the assembly medaka requires you to chose the nanopore chemistry and basecalling model the reads were produced on. In our case the reads were produced on a *R10.4* flowcell and basecalled with a *super-accuracy 400bps* model. The output should be written to directory *miniasm_medaka_output*.

    course_user> medaka_consensus -d ./miniasm.fasta -i ../../qc_practical/filtered.fastq -m r1041_e82_400bps_sup_g615 -o miniasm_medaka_output

As with some other steps Medaka is very computationally expensive and will run for a long time. Please stop Medaka pressing *Ctrl-c* and copy the contents of directory *~/biosec_course/misc/assembler_practical/miniasm_medaka_output/* into the *miniasm-medaka-output* directory in this directory:

    course_user> cp ~/biosec_course/misc/assembler_practical/miniasm_medaka_output/* ./miniasm_medaka_output/

In medaka's output directory is the polished sequence called *consensus.fasta*. Compare this file to the *B. fermentans* reference using *dnadiff*:

    course_user> dnadiff -p miniasm_medaka ~/biosec_course/misc/b_fermentans.fna ./miniasm_medaka_output/consensus.fasta

Open the *report* file and have a look at the output

<div style="background-color:#cfedfe;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon question height:32 class:"right left" aria-label:hi %} 
  <ol>
    <li>Did the quality of the assembly change?</li>
  </ol>
</div>
[Answer](APP_ANS.md#miniasm-medaka-error-correction)

## Error correction of the Flye assembly

Now repeat the same process with the Flye assembly. First change into the *assembler_practical/flye* directory and call medaka on the *assembly.fasta* file in the *flye_output* directory:

    course_user> medaka_consensus -d ./flye_output/assembly.fasta -i ../../qc_practical/filtered.fastq -m r1041_e82_400bps_sup_g615 -o flye_medaka_output

As before, in case oyu don't want to wait, stop medaka and copy the contents of *~/biosec_course/misc/assembler_practical/flye_medaka_output* into the *flye_medaka_output* directory here

    course_user> cp ~/biosec_course/misc/assembler_practical/flye_medaka_output/* ./flye_medaka_output/

... and run dnadiff on it

    course_user> dnadiff -p flye_medaka ~/biosec_course/misc/b_fermentans.fna ./flye_medaka_output/consensus.fasta

<div style="background-color:#cfedfe;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon question height:32 class:"right left" aria-label:hi %}
  <ol start=2>
    <li>How did the quality of the assembly change?</li>
  </ol>
</div>
[Answer](APP_ANS.md#flye-medaka-error-correction)

<p align="right"><a href="https://bluemountainsanalytics.github.io/bma_ont_biosec_2022/ASS_BUSC.html">CONTINUE -></a>
</p>

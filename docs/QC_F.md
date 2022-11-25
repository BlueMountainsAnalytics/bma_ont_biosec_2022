# Read Filtering using NanoFilt

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](QC_N.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](ASS.md)

After assessing the quality of a sequncing run one usually wants to remove low-quality reads or short reads. That said, usually, the basecaller already eprformed some kind of quality fitlering.

In the directory *qc_practical/fastq_file* is the fastq file of all the reads the basecaller produced in the sequencing run we just analysed. In the directory *qc_practical* create another directory, e.g. *example_2*. Call NanoPlot again but this time using the fastq file instead of the summary file using the *--fastq* flag and the output directory *example_2*.

    course_user> cd ~/biosec_course/practicals/qc_practical
    course_user> mkdir example_2
    course_user> NanoPlot --fastq ./fastq_file/fastq_runid_2.fastq -o ./example_2
 
Open the NanoPlot_report.html as before. 

<div style="background-color:#cfedfe;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon question height:32 class:"right left" aria-label:hi %}
  <ol start=9>
    <li>What quality cut-off did the basecaller use?</li>
    <li>Was a length cutoff applied?</li>
  </ol>
</div>

Answers](QC_ANS.md)

## Basecalling Oxford Nanopore Data

Oxford Nanopore sequencers produce output files in *fast5* format. This file format is based on the *hierarchical data format* [HDF5](https://en.wikipedia.org/wiki/Hierarchical_Data_Format) which enables storage of large and complex data. The FAST5 output files of oxford nanopore contains all data of a sequencing run in pore-resolution, including the raw pore current signal, which the basecaller "translates" into a sequence. Even the sequence is included in the fast5 files once they are basecalled. Hence, a FAST5 file is very large compared to a simple sequence file.

After basecalling, the read sequences are stored in FASTQ files. The fastq format is the de-facto standard of 2nd generation sequencing technology such as Illumina sequencers. It is similar to the fasta format but in addition to the sequence itself a fastq file also stores quality scores of the sequence. A fastq file stores every sequence in exactly 4 lines:
 1. The name/ID line starting with “@” followed by a sequence identifier
 2. The sequence itself
 3. A line starting with “+” (optionally followed by additional information, e.g., the read names again) which is an artifact that can be ignored nowadays
 4. The quality line with one character per sequence residue encoding the probability of a possible sequencing error ([Phred score](https://github.com/timkahlke/LongRead_tutorials/blob/master/docs/APP_MET.md#phred-score))

    @4e131bcf-f814-485a-b02f-3d133030b06e
    TTGTTATGCCGCTTCGTTCAGTTACGTATTGCTCGACGGTTCCACTTTGAACGTTTGCGTTCAAATACTATAACTAGTTTTGCTCTCGTTTTAATCTTCCCCGTCTCTCCCAAA
    +
    ??????+(+*(%%#()&.67:58D8.10;01.4.8.)(*'(.-,2,?<79C97:?2()((,%()**())'&&IIICCCIIII**(%%#()&.67:58D8.10;01.4.8II?%?



## Filtering fastq files using NanoFilt

Another script included in the NanoPack suite is *NanoFilt*. As already indicated by the name, NanoFilt can be used to filter sequencing files in fastq format based on quality or length. Call NanoFilt with the *-h* flag for *help* to see how to use it.

    course_user> NanoFilt -h

The output of the help message tells us that we can filter sequences by minimum length using the *-l* flag, and that we can specify the input as the last argument for the command. However, NanoFilt does not save the output, i.e., the new fastq file, ina  file but prints the output to the terminal. To *re-direct* and save the output in a new fastq file we will have to use the bigger-than sign (>) followed by a file we want to save the output in. 

Let's try to filter the fastq file in *ac_practial/fastq_file* and remove all sequences smaller than 3,000 nucleotides, and save the output in a new file in the same fastq directory but in a file called *filtered.fastq*.

    course_user> NanoFilt -l 3000 ./fastq_file/fastq_runid_2.fastq > ./fastq_file/filtered.fastq

Once nanoFilt is done we can already see the difference in file size of the two fastq files when we use the *ll* command on the fastq_file directory:

    course_user> ll ./fastq_file
    -rw-r--r-- 1 course_user course_user 36070824 Nov 20 21:43 fastq_runid_2.fastq
    -rw-rw-r-- 1 course_user course_user 33664494 Nov 20 22:46 filtered.fastq

To see a little more ab out the effect of the filtering create a last directory, *example_3*, in the directory and run NanoPlot on the filtered fastq file, and store the output in *example_3*.


    course_user> mkdir example_3
    course_user> NanoPlot --fastq ./fastq_file/filtered.fastq -o ./example_3

Open the *Nanoplot-report.html* file and have a look at the read length and how filtering affected the overall quality of the sequencing output.


<p align="right"><a href="https://bluemountainsanalytics.github.io/BMA_CLI-tutorial/ASS.html">CONTINUE -></a>
</p>

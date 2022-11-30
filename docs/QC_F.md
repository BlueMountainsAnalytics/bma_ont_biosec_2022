# Read Filtering using NanoFilt

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](QC_N.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](ASS.md)

After assessing the quality of a sequencing run one usually wants to remove low-quality reads or short reads. That said most basecallers already apply some kind of quality filtering by default.
In the *qc_practical* is you'll find a sequencing read file in *fastq* format that a basecaller produced. 

In the directory *qc_practical* create another directory, *example_2*. Call NanoPlot again but this time using the fastq file instead of the summary file using the *--fastq* flag and the output directory *example_2*.

    course_user> cd ~/biosec_course/qc_practical
    course_user> mkdir example_2
    course_user> NanoPlot --fastq ./R10-202001.fastq -o ./example_2
 
Open the NanoPlot_report.html as before. 

<div style="background-color:#cfedfe;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon question height:32 class:"right left" aria-label:hi %}
  <ol start=9>
    <li>What quality cut-off did the basecaller use?</li>
    <li>Was a length cutoff applied?</li>
  </ol>
</div>

[Answers](QC_ANS.md)

## Basecalling Oxford Nanopore Data

Oxford Nanopore sequencers produce output files in *fast5* format. This file format is based on the *hierarchical data format* [HDF5](https://en.wikipedia.org/wiki/Hierarchical_Data_Format) which enables storage of large and complex data. The FAST5 output files of oxford nanopore contains all data of a sequencing run in pore-resolution, including the raw pore current signal, which the basecaller "translates" into a sequence. Even the sequence is included in the fast5 files once they are basecalled. Hence, a FAST5 file is very large compared to a simple sequence file.

After basecalling, the read sequences are stored in FASTQ files. The fastq format is the de-facto standard of 2nd generation sequencing technology such as Illumina sequencers. It is similar to the fasta format but in addition to the sequence itself a fastq file also stores quality scores of the sequence. A fastq file stores every sequence in exactly 4 lines:
 1. The name/ID line starting with “@” followed by a sequence identifier
 2. The sequence itself
 3. A line starting with “+” (optionally followed by additional information, e.g., the read names again) which is an artifact that can be ignored nowadays
 4. The quality line with one character per sequence residue encoding the probability of a possible sequencing error. This score is used for plots as well as for filtering of low-quality reads. 

    @4e131bcf-f814-485a-b02f-3d133030b06e
    TTGTTATGCCGCTTCGTTCAGTTACGTATTGCTCGACGGTTCCACTTTGAACGTTTGCGTTCAAATACTATAACTAGTTTTGCTCTCGTTTTAATCTTCCCCGTCTCTCCCAAA
    +
    ??????+(+*(%%#()&.67:58D8.10;01.4.8.)(*'(.-,2,?<79C97:?2()((,%()**())'&&IIICCCIIII**(%%#()&.67:58D8.10;01.4.8II?%?



## Filtering fastq files using NanoFilt

As already indicated by the name, NanoFilt is a tool that is used to filter sequencing files in fastq format based on quality or length. Call NanoFilt with the *-h* flag for *help* to see how to use it.

    course_user> NanoFilt -h

The output of the help message tells us that we can filter sequences by minimum length using the *-l* flag, and that we can specify the input as the last argument for the command. However, NanoFilt does not save the output, i.e., the new fastq file, ina  file but prints the output to the terminal. To *re-direct* and save the output in a new fastq file we will have to use the bigger-than sign (>) followed by a file we want to save the output in. 

Let's try to filter the fastq file in our directory as follows
 * filter all reads shorter than 1,000 nucleotides
 * filter all reads with a Q-score <= 10

Re-direct the output into a file called *filtered.fastq* in the same directory.

    course_user> NanoFilt -l 1000 -q 10 ./R10-202001.fastq > ./filtered.fastq

Once nanoFilt is done we can already see the difference in file size of the two fastq files when we use the *ll* command on the fastq_file directory:

    course_user> ll ./fastq_file
    -rw-r--r-- 1 course_user course_user 951071716 Nov 20 21:43 R10-202001.fastq 
    -rw-rw-r-- 1 course_user course_user 700713867 Nov 20 22:46 filtered.fastq

Take a look at the output, again using Nanoplot. Create a new output directory *example_3* for it.

    course_user> mkdir example_3
    course_user> NanoPlot --fastq ./filtered.fastq -o ./example_3

Open the *Nanoplot-report.html* file and have a look at the read length, how many reads were fitlered out and how filtering affected the overall quality of the sequencing output.


<p align="right"><a href="https://bluemountainsanalytics.github.io/bma_ont_biosec_2022/ASS.html">CONTINUE -></a>
</p>

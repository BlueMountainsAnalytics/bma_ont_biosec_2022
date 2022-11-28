# Community analysis using marker genes

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](ASS_BUSC.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](END.md)

In contrast to *whole genome sequencing* sequencing is more often applied to perform community analyses using marker genes, e.g., 16S rRNA genes, or mitochondrial cytochrome b (cob) genes. However, prior to long-read technologies, often partial marker genes were used for community analyses, e.g. hypervariable regions V1-V4 of the rRNA gene.

With Oxford nanopore sequencing almost complete rRNA genes can be used to infer communities with a much higher phylogenetic resolution and sensitivity. 

This tutorial will give a very brief overview over read-based community analyses similar to that of short read data analysis. Several software frameworsk exist for short-read analysis without assembling the reads into larger fragments, e.g. [Kraken](https://github.com/DerrickWood/kraken). However, many are not capable of using long-reads or support only specific taxonomies/databases. Here we use [BASTA](https://github.com/timkahlke/BASTA) which is capable of identifying any sequence based on sequence comparison to a database although it is not commonly used for community analysis.

First, re-activate the *biosec* conda environment and change into the *its_practical* directory. In it is a fastq file of Oxford Nanopore reads from the *Internal-transcribed-spacer* (ITS) gene that connects the small and the large sub-unit of the rRNA gene. It is a common fungal marker gene.

We will use nucleotide BLAST on the command-line to compare our reads to sequences in the UNITE database, a database of fungal ITS sequences. BLAST needs ts input  sequences in *fasta* format not in *fastq*. We will use the command *reformat.sh* from the BBMAP package to convert our fastq file to fasta format. *Reformat.sh* takes the input with parameter *in=* and an output name given with *out=*

**Note** reformat.sh does not use the usual *-* notation for flags.

    course_user> reformat.sh in=fungal_its.fastq out=fungal_its.fasta

Once it is done check that you have your *fungal_its.fasta* file in your directory. Now use it to blast it against the UNITE database: 

    course_user> blastn -in ./fungal_its.fastq -out fungal_its.vs.unite.out -outfmt 6 \
    course_user> -db ../misc/UNITE/unite.fasta -num_threads 4

The flags needed for blastn (nucleotide blast) are *-in* for the input fasta file, a database given with *-db*, and output file name given with *-out*. Additionally, we specify  that the output should be in tabular format (*-outfmt 6*) and that we want to use 4 threads, i.e., CPU cores. 

In case you don't want to wait, stop blastn with *Ctrl-c* and copy the result file from directory ~/biosec_course/misc/its_prac/fungal_its.vs.unite.out into this directory.

You can have a look at the output using *head*

    course_user> head fungal_its.vs.unite.out

As you can see it is a tab separated file with hit statistics for each sequence in the database that (partly) matches a read in our fastq file. The names of the matchin UNITE sequence are found in the second column. However, this doesn't really tell us anything as it's all very cryptic identifiers.

To get a nicer output we will use [BASTA](https://github.com/timkahlke/BASTA) to resolve the identifiers to taxonomic names and create a Krona plot. Although not the most accurate way of analysing this dataset it will give us an idea on the different species and ratios in our dataset.

We will use BASTA's *sequence* command and specify the blast output file, the name of our basta output file, and the database mapping file for identifiers to the NCBI taxonomy.

    course_user> basta sequence fungal_its.vs.unite.out fungal_basta.out unite

Have a look at the output file. For each read it shows the taxonomy that BASTA inferred based on similar sequences in the UNITE database on their taxonomies. To convert this into a nicer looking graphs call teh script *basta2krona.py*

    course_user> basta2krona.py fungal_basta.out fungal_krona_plot.html

This will create the file *fungal_krona_plot.html*. Navigate to the file and double click it to open it in FireFox.

Investigate the plots. If you clikc a group once, e.g., *Pucciniales* it will show general staistics on the right. You can zoom further in by double-clicking those groups (go back using the small arrows in the upper left).

<div style="background-color:#cfedfe;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon question height:32 class:"right left" aria-label:hi %}
  <ol>
    <li>What are the main groups and their ratios?</li>
  </ol>
</div>
[Answer](ITS_ANS)

<p align="right"><a href="https://bluemountainsanalytics.github.io/bma_ont_biosec_2022/END.html">CONTINUE -></a>
</p>

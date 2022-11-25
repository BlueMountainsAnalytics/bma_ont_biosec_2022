# Assembler practical answers

## Genome Assembly with Minimap2 and Miniasm

### 1. How many unitigs are there and what is the length of the longest one?

The fasta file contains 8 unitigs (n = 8) and the longest unitig is 474,411 nucleotides long.

<img src="figures/A25.png" height="100px">

### 2. How many of the miniasm sequences align with the reference?

5 out of 8

<img src="figures/A26.png" height="80px">

### 3. What is the average %-identity of the miniasm assembly compared to the reference? Would you have expected this %-identity?

Depending of whether you use the <i>1-to-1</i> or the <i>M-to-M</i> statistics the %-identity is either 88.13 or 88.12, respectively.

<img src="figures/A27.png" height="100px">

The low %-identity of the assembly when compared to the "truth" (reference) is expected because miniasm does not perform any kind of error correction or consensus sequence building. Thus, the error rate of the resulting assembly is identical or similar to the error rate of the input reads.

<div style="background-color:#fcfce5;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon info height:32 class:"right left" aria-label:hi %}
  The difference between is that the <i>1-to-1</i> relationship only counts those alignment blocks that are bidirectional, i.e., hits reference->query as well as query->reference. In contrast, the <i>M-to-M</i> option (many-to-many) also counts alignment blocks that are only found in a reference->query or query->reference direction. Thus the M-to-M option is a <i>superset</i> of the 1-to-1 option that maximises the coverage of all alignments at the expense of %-indentity.
</div>

### 4. How many of the miniasm unitigs align with the reference?

Given that the Assemblytics dot-plot is a visualisation of what we already saw int he report file the answer is again "5". However, the Assemblytics dot-plot shows that only 2 of the unitigs align over the majority of the sequence with the reference without (major) disruptions or INDELS: utg00004l and utg00001l. The dot-plots also show two repeat regions in the beginning of the sequence (the red crosses in utg00004l).

<img src="figures/A28.png" height="200px">


### 5. Does the miniasm assembly cover the complete reference?

Overall the assembly covers almost the complete sequence as show in the diagonal line starting at 0/0 (lower right corner) and continuing through utg00004l and utg00001l to the end of Chr17. However, it seems that a small part at the transition between the two unitigs is missing, represented by a break and shift to the right in the diagonal line.

<img src="figures/A29.png" height="200px">

### 6. What could the repetitive region at the end of chromosome 17 be?

One potential explanation could be that the assembly includes a telomere-sequence, repeat sequences at the end of chromosomes that protects the single-strand overlap of the DNA against degradation. A common telomere sequence in eukaryotes is (TTAGGG) * N.

----

### Genome assembly using Flye

### 1. Does the assembly differ from the miniasm assembly, e.g., wrt total length, number of contigs and length of the contigs?

Yes, the Flye assembly results in more than 4 times the number of contigs (33) and the largest contig is also longer than the miniasm assembly (681,342 nucleotides). However, the average length of the contigs is ~20k nucleotides shorter in the Flye assembly (~73k) in comparison to the miniasm assembly (~96k).

<img src="figures/A30.png" height="100px">

### 2. How many contigs aligned with the reference? What is the error rate?

Of the 33 contigs in the Flye assembly 31 aligned to the reference. Interestingly, as can be seen in the <i>Bases</i> statistics only ~30% of all the bases in the Flye assembly aligned to the reference. Thus, the two unaligned contigs seem to be contain ~70% of the bases.

As expected the error rate of the Flye assembly is much lower than the miniasm assembly because Flye also includes a consensus sequence step which decreases the 1-to-1 error rate to <1% and the M-to-M error rate to <2%.

<img src="figures/A31.png" height="200px">

### 3. How many contigs align well with the reference?

Although the report shows 33 contigs that align to a certain degree with the reference the assemblytics dot-plot shows that only one contig alignes significantly with the reference: contig_2.

<img src="figures/A32.png" height="300px">

### 4. Is the Flye assembly more or less fragmented than the miniasm assembly? Why?

The Flye assembly is less fragmented (one contig aligns to the whole reference vs 2 in the miniasm assembly). There are several possible explanations. The most likely one is the fact that miniasm outputs unitigs where Flye outputs contigs. Remember, unitigs are <i>high confidence</i>contigs, i.e., the path in the assembly graph shows no conflicts or ambiguous paths. In contrast, Flye includes several heuristics that resolve conflicts and ambiguities in the assembly graph to output more contiguous sequences (contigs). Another explanation is that Flye's <i>repeat graph</i> approach may be able to resolve repeat regions much better than miniasm.

### 5. Does the alignment differ from the reference, e.g., does the Flye assembly extend the start or stop of the reference? Are there inversions?

If you zoom in on contig_2 (click ont he name) it seems that contig_2 extends the reference (slightly) at the start (the diagonal line starts at >0 on the Y-axis).

<img src="figures/A33.png" height="300px">



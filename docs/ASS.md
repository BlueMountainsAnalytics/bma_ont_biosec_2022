# Genome Assembly

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](QC_F.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](ASS_M.md)

*Genome assembly* is the process of putting together your reads, short-reads, long-reads or both, into long contiguous sequences (contigs). Many different approaches and tools exist to assemble genomes. In the last years an increasing number of assemblers and assembly pipelines has been released that are specifically designed for long-read assemblies, e.g., Canu, Flye, Shasta, and miniasm. 

In this tutorial we will use two different assemblers/assembly pipelines, Flye, and minimap2-miniasm, and compare the results.

<div style="background-color:#fcfce5;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon info height:32 class:"right left" aria-label:hi %} 
  Two common questions about genome assembly and the answers to them:<br><br>
  <b>1. What is the best assembler to use?</b><br>The answer to this question is something like "It depends.". Different assemblers will perform differently for different genomes. Factors such as genome size, repetitiveness, GC content and others can all influence the performance of the assemblers. Best practice is to run multiple assemblers, compare the results and then decide yourself which one to use.<br><br>
  <b>2. When is my assembly done?</b><br>Currently, the answer to this question is <i>Never.</i>. As an example: the Human Genome is the best studied genome in the world with thousands of individuals sequenced and millions (billions?) of dollars spent. Still, until recently up to 20% of the Human Genome remained unassembled and only resent long-read sequencing technologies enabled us to slowly close the gaps on these last 20%. This does not mean you can never finish you project. It means <u>your assembly is done when it can answer the questions you want to ask!</u>
  </div>

<p align="right"><a href="https://bluemountainsanalytics.github.io/bma_ont_biosec_2022/ASS_M.html">CONTINUE -></a>
</p>

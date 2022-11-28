# Completeness analysis using BUSCO

Another method of assessing the quality of a genome assembly is to estimate the *completeness* of the genome in terms of gene sets. 

BUSCO uses sets of lineage-specific single-copy core/conserved genes and searches a genome assembly for these. The output is a table of 

 * Complete BUSCO genes
 * Complete and Single-copy
 * Complete and duplicated
 * Fragmented BUSCO genes
 * Missing BUSCO genes
 * Total BUSCO groups searched

These results give an idea of how complete the genome might be in terms of overall genes, how truncated the assembly is (# of complete/fragmented BUSCO genes), and whether there are eareas that are duplicated, e.g., due to multiple strains, wrongly assembled areas or the like.

To use BUSCO please activate the conda environment busco
 
    course_user> conda activate busco

Change into the *assembly_practical/minimap-miniasm* directory and call BUSCO on the miniasm.fasta. It requires a lineage of the genome (*-l flag*), the assembly (*--in* flag), an output directory (*--out* flag), and we want to analyse a genome, i.e., we will specify the mode as *genome (*-m genome*):

    course_user> busco -m genome\
    course_user> -l bacteria \
    coures_user> --in miniasm.fasta \
    course_user> --out miniasm_busco \
    course_user> -m genome
    
Now repeat the process with the flye assembly.

<div style="background-color:#cfedfe;border-radius:5px;border-style:solid;border-color:gray;padding:5px">
  {% octicon question height:32 class:"right left" aria-label:hi %}
  <ol>
    <li>How complete are the 2 assemblies? What are the differences?</li>
    <li>Overall, which assembly would you prefer?</li>
</div>
[Answer](APP_ANS.md#busco)

As an interesting test you could run busco on the *B. fermentans* genome to get an idea what the maximum BUSCO score for this critter would be.

<p align="right"><a href="https://bluemountainsanalytics.github.io/bma_ont_biosec_2022/ITS.html">CONTINUE -></a>
</p>

# Quality Control (QC) of Oxford Nanopore data

[{% octicon arrow-left height:32 class:"right left" vertical-align:middle aria-label:hi %}](OV.md) [{% octicon home height:32 class:"right left" aria-label:hi %}](index.md) [{% octicon arrow-right height:32 class:"right left" aria-label:hi %}](QC_N.md)

The initial step  of every sequencing project is the quality control step to assess the quality of your sequencing data. It will give oyu an understanding on how successful your sequencing run was based on certain statistics, e.g., length and quality score distributions of your reads, as well as highlight potential problems with your input DNA/RNA, the sequencing run or the data itself.

The quality control step also gives you information for your data filtering and trimming, i.e., removal of those reads that are too short or too low in quality.

An increasing number of tools is available for sequence data QC and filtering, with different strength and applicaton cases. Here, we will use a software suite called [NanoPack](https://github.com/wdecoster/nanopack) written by Wouter de Coster. It includes 6 tools for QC, filtering and trimming of nanopore data. 

**Data directory:** *~/course_data/practicals/qc_practical*

<p align="right"><a href="https://bluemountainsanalytics.github.io/BMA_CLI-tutorial/QC_P.html">CONTINUE -></a>
</p>

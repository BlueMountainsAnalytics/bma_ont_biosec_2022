# Quality Control Answers

## 1. How many reads did the sequencing run yield? How many nucleotides in total?

2,135 reads with a total of 18,916,183 nucleotides.


## 2. What is the median and mean read length? What the read quality?

 * Mean read length: 8,860
 * Median read lenght: 3,334
 * Mean read quality: 9.6
 * Median read quality: 9.9


## 3. What is the N50 of the sequencing run?

22,827 bases


## 4. How many reads have less than 10% error probability?

963 reads are >Q10, hence have less than 10% error probability.


## 5. What is the longest read in the sequencing run and what is its quality score?

109,211 nucleotides with a Q-score of 10.2


## 6. Have a look at the “Read length vs Average read quality”. Is there a link between read length and PHRED score?

In this sequencing run it seems that shorter reads tend to have a lower sequencing quality


## 7. What do you think happened ~5h into the sequencing run?

The increase in read numbers and general yield could be explained by either an increase in the strength of the current in the sequencer or a re-load of DNA into the flowcell.


## 8. What can you say with regards to yield and quality over time? Was this a good sequencing run?

The *Cummulative yield* and *Number of reads over time* plots show that the 50% of the reads and overall yield was reached in the first ~5h of the ~16h sequencing run. 

The violin plots for read length and quality over time indicate that the reads get shorter and have lower quality after ~9h into the sequencing run.

The *Active pores over time* together with the number of *Active Channels* from the top of the page shows that the flowcell had only a very low number of active pores to start with (319), which then deteriorated quickly. After less than one hour most of the active pores were already blocked or completely deactivated.

Overall, this was not a good sequencing run overall. However, the flowcell used should have been dead alread, i.e., we were happy to get an additional 18MB out of it.

<p align="left"><a href="https://bluemountainsanalytics.github.io/bma_ont_biosec_2022/QC_N.html">BACK =></a>

<br>

## 9. What quality cut-off did the basecaller use?

No read were called below Q5.

## 10. Was a length cutoff applied?

It's not 100% obvious but the shortest reads are >=100 nucleotides.

<p align="left"><a href="https://bluemountainsanalytics.github.io/bma_ont_biosec_2022/QC_F.html">BACK =></a>
</p>


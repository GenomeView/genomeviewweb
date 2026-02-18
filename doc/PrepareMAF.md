# Preparing MAF

The best way to create genome alignment data is with a [MAF](https://biopython.org/wiki/Multiple_Alignment_Format) (Multiple Alignment Format) file.

[Here is another specification of the format](https://genome.ucsc.edu/FAQ/FAQformat.html#format5)

> [!WARNING]
> Do not confuse this with the "Aggregated Somatic Mutation" file or the "Mutation Annotation Format" 
> which are also sometimes referred to as MAF file.

<!-- also 
[Details on the MAF format](https://cgwb.nci.nih.gov/goldenPath/help/maf.html)
-->

##  Creating a multiple alignment

* You can use an aligner such as TBA (Threaded Blockset Aligner).  This can be downloaded from http://www.bx.psu.edu/miller_lab/
* [Instructions for using TBA](files/tba_howto.pdf)
* A phylogenetic tree is a required input.
* Three are 3 steps required to run TBA:
    1. Generate a series of pair-wise alignments to “seed” the multiple alignment process.  Example:  `all_bz - "(((((((human chimp) gorilla) baboon) (rat mouse)) (cow pig)) chicken) fugu)" blastz.specs >&all_bz.log`
    1. Generate the multiple alignment Example:  `tba "(((((((human chimp) gorilla) baboon) (rat mouse)) (cow pig)) chicken) fugu)" *.*.maf tba.maf >&tba.log`
    1. "project" the alignment onto a reference sequence.   This will not make it a reference-based alignment; it just allows for visualization. Example:  `maf_project tba.maf chicken > tba_project_chicken.maf`

After preparing the MAF file, you can [load it as MultipleAlignmentTrack](MultipleAlignmentTrack.md)

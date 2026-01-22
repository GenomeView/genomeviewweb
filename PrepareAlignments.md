# Preparing whole genome alignments

##  Creating a multiple alignment

* You can use an aligner such as TBA (Threaded Blockset Aligner).  This can be downloaded from http://www.bx.psu.edu/miller_lab/
* [Instructions for using TBA](files/tba_howto.pdf)
* A phylogenetic tree is a required input.
* Three are 3 steps required to run TBA:
    1. Generate a series of pair-wise alignments to “seed” the multiple alignment process.  Example:  `all_bz - "(((((((human chimp) gorilla) baboon) (rat mouse)) (cow pig)) chicken) fugu)" blastz.specs >&all_bz.log`
    1. Generate the multiple alignment Example:  `tba "(((((((human chimp) gorilla) baboon) (rat mouse)) (cow pig)) chicken) fugu)" *.*.maf tba.maf >&tba.log`
    1. "project" the alignment onto a reference sequence.   This will not make it a reference-based alignment; it just allows for visualization. Example:  `maf_project tba.maf chicken > tba_project_chicken.maf`

## Loading .maf files into GenomeView
Once you have a .maf multiple alignment, projected onto a reference genome, you can load this into GenomeView.

First, verify that all contig ID’s used in the .maf file match the contig ID’s used in your genome sequence and annotation files.  Load the genome sequence, annotation, and .maf file with matching contig ID’s into Genomeview.

In order to view comparative annotations, you need to follow these steps:

* Enable comparative annotations:
    * Under “File”, select “Configuation”.
   * Select the tab for “Comparative track”.
   * Make sure the box for “Enable comparative annotations” is checked.
* Load in one annotation file for each genome in your multiple alignment (checking to make sure all contig ID’s match those used in the .maf file).
* You should now see annotations for each genome in the multiple alignment.

# Preparing reference sequence


To be able to easily handle large reference genomes, it is required that they are indexed. This can be done with the faidx command from the samtools package.

If you are also preparing HTS data sets in the BAM format, this step will also be part of that procedure, so either you move right to the [short read preparation page](PrepareReadData.md) or you can skip the step there whenever you're ready.

To index a fasta file you run

`samtools faidx reference.fasta`

## Attention

If your file was called reference.fasta, GenomeView will search for reference.fasta.fai in the same directory. If you want to be able to load large files, make sure those two files are correctly named and in the same folder.

You can download the [samtools package from Sourceforge](http://samtools.sourceforge.net/). 

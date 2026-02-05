# Preparing FASTA


The FASTA format is a text based format for representing
genome sequences. Usually it is used to improve performance using indexing.

Check [wikipedia](https://en.wikipedia.org/wiki/FASTA_format) for details on the file format.

## Non-Indexed
A sequence begins with a greater-than character (">") followed by a description of the sequence (all in a single line). The lines immediately following the description line are the sequence representation, with one letter per amino acid or nucleic acid, and are typically no more than 80 characters in length. 

example:
```
>MCHU - Calmodulin - Human, rabbit, bovine, rat, and chicken
MADQLTEEQIAEFKEAFSLFDKDGDGTITTKELGTVMRSLGQNPTEAELQDMINEVDADGNGTID
FPEFLTMMARKMKDTDSEEEIREAFRVFDKDGNGYISAAELRHVMTNLGEKLTDEEVDEMIREA
DIDGDGQVNYEEFVQMMTAK*
```


## Indexing

Indexing is used to improve performance, to improve the 
ability of tools to rapidly access random locations of large files.

Indexing of a Fasta file can be done with the `faidx` command from the [samtools](https://www.htslib.org/doc/samtools-faidx.html). 

If you are also preparing HTS data sets in the BAM format, this step will also be part of that procedure, so either you move right to the [short read preparation page](PrepareReadData.md) or you can skip the step there whenever you're ready.

To index a fasta file you run

`samtools faidx reference.fasta`

> [!WARNING]
> If your file was called reference.fasta, GenomeView will search for reference.fasta.fai in the same directory. If you want to be able to load large files, make sure those two files are correctly named and in the same folder.

You can download the [samtools package from Sourceforge](http://samtools.sourceforge.net/). 

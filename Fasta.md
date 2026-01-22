# Fasta

The FASTA format is a text based format for representing
genome sequences. 

A sequence begins with a greater-than character (">") followed by a description of the sequence (all in a single line). The lines immediately following the description line are the sequence representation, with one letter per amino acid or nucleic acid, and are typically no more than 80 characters in length. 

example:
```
>MCHU - Calmodulin - Human, rabbit, bovine, rat, and chicken
MADQLTEEQIAEFKEAFSLFDKDGDGTITTKELGTVMRSLGQNPTEAELQDMINEVDADGNGTID
FPEFLTMMARKMKDTDSEEEIREAFRVFDKDGNGYISAAELRHVMTNLGEKLTDEEVDEMIREA
DIDGDGQVNYEEFVQMMTAK*
```

Check [wikipedia](https://en.wikipedia.org/wiki/FASTA_format) for details on the file format.

## Indexing

Indexing is used to improve performance, to improve the 
ability of tools to rapidly access random locations of large files.

Indexing of a Fasta file can be done with the [samtools](https://www.htslib.org/doc/samtools-faidx.html). Check the [Prepare reference sequence wiki](PrepareReferenceSequence.md) for details.

# Recipe to align reads

This recipe will help you align reads to a reference genome. This is merely an example of one possible protocol with one alignemnt program. There are many more available.

You need:
* a reference genome in FASTA format (reference.fasta)
* read data in FASTQ format (reads_1.fastq and reads_2.fastq)
* [recent version of BWA](http://sourceforge.net/projects/bio-bwa/files/)] (a short read aligner).

At the time of writing the most recent version of BWA is 0.7.5a

## Step by step instructions
These instructions need to be run in a terminal. To the best of our knowledge, BWA is only available for Unix based platforms like OS X and Linux.


Build BWA index for the reference
```
 bwa index reference.fasta
```
Align reads to the reference genome
```
 bwa mem reference.fasta reads_1.fastq reads_2.fastq > alignment.sam
```
Reads_1.fastq and reads_2.fastq indicate the two files that have the first and second read in a pair. If you data is not paired end sequencing the latter command would look like this:
```
 bwa mem reference.fasta reads.fastq > alignment.sam
```

You can visit the [BWA webpage](http://bio-bwa.sourceforge.net/bwa.shtml)  for more information and options.

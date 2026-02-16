# Preparing BAM



The best format to present short read alignments to GenomeView is the SAM/BAM format. You need to have your read data in this format and it has to be aligned to a reference genome. 

## Aligning reads

GenomeView is a visualization tool and does not do the computationally intensive read alignment. There are however dozens of tools already available to do this job.

If you need help aligning your reads, you may want to have a look at the Recipe to align reads to get some ideas. 

## Sorting and indexing

Before you can visualize read data you need to prepare the data. This needs to be done because those files are generally huge and we do not want to read the complete file if we're only looking at a small portion of it.

There are two things to prepare data fresh from the aligner.

1. Sort reads based on genomic coordinates
1. Index sorted reads.

### With Picard (OS independent, recommended)

You need to have a a recent version of Java installed and you need to run these commands on the [command-line](CommandLine.md). There are download links with each program where you can fetch the exact version that these manual pages were tested with. Alternatively, you may want to install a more recent version of [Picard](https://github.com/broadinstitute/picard). 

In this example we have a read alignment in BAM format called 'alignment.sam'. We use the program [SortSam](https://www.genepattern.org/modules/docs/Picard.SortSam/4/) from Picard to sort the file by coordinates. This also works if your aligner gives you a BAM file as output, i.e. 'alignment.bam'

#### Sorting 
The instruction below will sort the SAM file by coordinate. 

`java -Xmx500m -jar picard.jar SortSam -I aligned.sam -O sorted.bam -SO coordinate`


Important:


1.    You may need to put the full path to where the aligned.sam file sits and where you want the sorted.bam file to end up.
1.    You have to make sure to replace 'alignment.sam' with the actual name of you aligned SAM/BAM file.
1.    You have to make sure to replace 'sorted.bam' with the actual name that you want your sorted file to have.

Sanity checks:

1.    Make sure there are no errors reported on the console when running this instruction.
1.    Make sure that you now have a file 'sorted.bam' and that it's not completely empty, i.e. it has a size > 0



#### Indexing 

You can also create an index with SortBam. Add the `--CREATE_INDEX true`  option in your sorting command above.



Sanity checks:

1.    Make sure there are no errors reported on the console when running this instruction.
1.    Make sure that you now have a file 'sorted.bam.bai' and that it's not completely empty, i.e. it has a size > 0. This file will be created in the same directory as the 'sorted.bam' file.


#### Downsampling data

Sometimes you don't want to look at all reads, but just at a fraction. This can be done by downsampling you BAM files before indexing.

`java -Xmx500m -jar picard.jar DownsampleSam  -I sorted.bam -O downsample.bam -P 0.1`



* The I parameter is the input file
* The O parameter is the output file
* The P parameter is the probability that a read is retained, so 0.1 means that 10% of the reads are kept.


## Summary visualizations

### Coverage plots

If you are primarily interested in the read coverage and not in individual reads, you may want to [create coverage plots](PreparingCoveragePlots.md).

### Variants

If you are investigating SNPs or other genetic variants, you also may want to [create variant calls](RecipeVariantCalls.md). 


# Preparing value data

There are three formats supported for value/continuous data. The TDF format is by far the most appropriate and the other formats should be considered legacy support.

TDF is a tiled binary data format which contains the value plot, as well as multiple resolution summaries which allows fast retrieval at any scale.

This format is an alternative to wig and the bigwig formats and is typically used for data that has a value per chromosomal position, like for example coverage data.

You can create TDF files directly from BAM files or from wig files. 

## Creating TDF files (recommended)

* [bam2tdf](Bam2tdf.md): convert read alignment to coverage plot
* [wig2tdf](Wig2tdf.md): convert wig formatted data to tdf formatted data


## SAMTools pileup (includes diversity information, i.e. SNP track)

> [!Note]
> file name extension should contain .pileup The first step to be able to browse a pileup is to generate one from your BAM file.

```
samtools mpileup -f reference.fasta  sorted.bam >sorted.pileup
```

As you run this command, you'll see that the generated file can be huge, even for small BAM files.

To be able to browse it in GenomeView, it needs to be indexed with tabix, a tool that is also available from the SAMtools web page.

```
sort -k1,1 -k2,2n sorted.pileup | bgzip -c > compressed.pileup.bgz
tabix -s 1 -b 2 -e 2 compressed.pileup.bgz
```

### Tab delimited pileup (extension should contain '.swig')

The file should be organized in four columns. The first column holds the identifier of the sequence, the second column contains the genomic position, the third column contains the number of reads on the forward strand, the final column contains the number of reads on the reverse strand.

1.    Identifier
1.    Genomic position (one-based)
1.    number of  forward reads
1.    number of  reverse reads

Example:
```
chr1	11	46	43
chr1	12	47	50
chr1	13	48	61
chr1	14	53	79
```

> [!Note] the white-space between the columns are tabs, one tab between each column.

Once you have such a file, you can again index it for faster access and shorter download times.

```
sort -T . -k1,1 -k2,2n filename | bgzip -c > filename.bgz
tabix -s 1 -b 2 -e 2 filename.bgz
```

It is recommended that you convert this format to TDF with [wig2tdf](Wig2tdf.md).

[samtools](http://sourceforge.net/projects/samtools/files/samtools/%7CDownload) 
[tabix](https://sourceforge.net/projects/samtools/files/tabix/%7CDownload) 

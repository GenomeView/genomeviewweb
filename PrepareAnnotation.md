# Preparing annotation

Large feature files need to be indexed before you can use them properly in GenomeView.

The definition of large is not strict in the sense that it depends on both the real size of the file, as well as the number of features in the file.

### Recommendations

*    Only index feature files that are larger than 5 Mb or even 10 Mb when compressed with GZIP.
*    Only index feature files that do NOT contain composite features, i.e. feature consisting of multiple locations. The prime example are eukaryote genes.
*    Typically the annotation of a genome does not need to be indexed if it just contains genes, mRNA, CDS and exons
*    You should not included multiple types (mRNA,CDS, ...) of annotation in a single file as all features will be loaded in a single track with the file name as label. We suggest you put each type in its own file.

### Instructions 
To index a file, you need to pre-process it with tabix, much like is done with pile-up files.

Tabix can be downloaded from the [tabix download page](https://sourceforge.net/projects/samtools/files/tabix/).

## BED formatted files

```
sort -k1,1 -k2,2n input.bed | bgzip -c > compressed.bed.bgz
tabix -p bed compressed.bed.bgz
```

You will get two new files: (1) a bgz file and (2) a tbi file. Load the bgz file in GenomeView.

>[!NOTE]
> indexing will not work with BED files that have a UCSC header ("track name=blah")


## GFF formatted file

>[!WARNING]
>Compound features will be broken up during indexing of gff files.

```
sort -T /group/tmp -k1,1 -k4,4n input.gff | bgzip -c > compressed.gff.bgz
tabix -p gff compressed.gff.bgz
```
You will get two new files: (1) a bgz file and (2) a tbi file. Load the bgz file in GenomeView.

>[!NOTE]
>The structure of genes and the type of annotation features will be lost when indexing gff files. 


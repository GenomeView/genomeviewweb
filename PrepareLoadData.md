# Preparing and loading data

There are several easy ways to load up data into GenomeView. Before you load your data, you may want to make sure you're using a supported format from the list below. Generally, GenomeView will notify you if it doesn't understand your data. 

## Loading data

You can load your data files in various ways:

* by selecting "work with my data" in the Genome Explorer
* by dragging them onto GenomeView
* by selecting the 'File' menu and then 'Load data...' (tutorial)
* by pressing CTRL+O
* by specifying them as argument on the command-line
* by loading a session file


You can load preloaded data by:

* selecting a genome from the Genome Explorer
* following a link from a GenomeView enabled website

## Data preparation recipe

1. Match identifiers: GenomeView uses the identifiers to link different sources, so make sure that the identifiers match (case-sensitive).
1. Create indices for data files that need it (check table below)
1. Convert file formats to get desired visuals (check table below)
1. Load data (see above)

Why index files? Indexing will create a look-up table for GenomeView to load data on-the-fly. This will will speed up browsing and loading speed, as well as significantly reduce the amount of memory you need. For some file formats we recommend you create indices, for other we do not. See the table below for more details and links to instructions. 

## Recommended file formats

This is a list of file formats that are recommended for different data types. See the full list of data types in the section below. 

|Data type	|Recommended file format  |Instructions|
|---|---|---|
|Reference sequence	|fasta	|[Prepairing Reference Sequence](PrepareReferenceSequence.md)|
|Annotation	|GFF3	|[Preparing Annotation](PrepareAnnotation.md)|
|Read a alignments	|BAM	|Preparing read data|
|Variation	|VCF	|Preparing VCF data|
|Coverage summary - continuous values	|TDF	|Preparing value data|
|Whole genome alignments	|MAF	|Preparing whole genome alignments|
|Genome synteny	|experimental	|Preparing genome synteny|

## Supported data formats
There are supported formats for reference sequences, annotation, Whole genome alignments
, Read alignments, Read coverage summary - continuous value data, 
Genome variation and diversity, Allele diversity


### Reference sequence

<!-- straight copy of original table because special layout -->
<table border="1"><tbody>
<tr><th>Data type</th><th>File format</th><th>Index*</th><th colspan="2">Max size**</th><th>Comments</th></tr>
<tr><th></th><th></th><th></th><th>unindexed***</th><th>indexed</th><th></th></tr>
<tr><td rowspan="2" valign="top">Reference sequence</td><td><b>fasta</b> <sup>¤</sup></td><td>Recommended<br><a href="PrepareReferenceSequence.md" class="mw-redirect" title="Index FASTA">Index FASTA</a></td><td>50 Mb</td><td>unlimited</td><td>GenomeView will query the user create index for you if you don't have one and the file is very large.</td></tr>
<tr><td>embl, genbank</td><td>Not possible</td><td>50 Mb</td><td>--</td><td>EMBL and genbank are mixed file formats that can contain both annotation and reference sequence at the same time.</td></tr>
</tbody></table>

### Annotation

<!-- straight copy of original table because special layout -->
<table border="1"><tbody>
<tr><th>Data type</th><th>File format</th><th>Index*</th><th colspan="2">Max size**</th><th>Comments</th></tr>
<tr><td rowspan="4" valign="top">Annotation</td><td><b>gff</b> <sup>¤</sup></td><td>Not recommended
<a href="PrepareAnnotation.md#gff-formatted-file" class="mw-redirect" title="Index GFF">Index GFF</a></td><td>50 Mb</td><td>unlimited</td><td></td></tr>
<tr><td>embl, genbank</td><td>Not possible</td><td>50 Mb</td><td>--</td><td>EMBL and genbank are mixed file formats that can contain both annotation and reference sequence at the same time.</td></tr>
<tr><td>bed</td><td>Not recommended <a href="PrepareAnnotation.md#bed-formatted-files" class="mw-redirect" title="Index BED">Index BED</a></td><td>50 Mb or less</td><td>unlimited</td><td>By default data from a bed file is added to the CDS track, if you want it in a different track, you have to add a line a the top of the file 'track name=Track_name'. No white-space is allowed in the track name.</td></tr>
<tr><td>ptt, tbl </td><td>Not possible</td><td>50 Mb or less</td><td>--</td><td>Other standard annotation formats GenomeView understands</td></tr>
<tr><td></td><td>various formats</td><td>Not possible</td><td>50 Mb or less</td><td>--</td><td>GenomeView can directly parse the output of the following programs: Blast, GeneMark, TransTermHP, FindPeaks, MaqSNP, tRNA-scan</td></tr>
</tbody></table>

### Whole genome alignments

<!-- straight copy of original table because special layout -->
<table border="1"><tbody>
<tr><th>Data type</th><th>File format</th><th>Index*</th><th colspan="2">Max size**</th><th>Comments</th></tr>
<tr><td rowspan="3" valign="top">Multiple genome alignment</td><td><b>maf</b> <sup>¤</sup></td><td>Recommended</td><td>100 Mb</td><td>unlimited</td><td>GenomeView will prompt you to create a compressed maf file and index it for you, if you're trying to load an unindexed maf file.<br>MAF is the recommended file format for whole genome alignemnt of large/complex genomes</td></tr>
<tr><td><b>multi-fasta</b> <sup>¤</sup></td><td>Not possible</td><td>100 Mb</td><td>--</td><td>Recommended for small/simple genomes with a near 1:1 relationship.</td></tr>
<tr><td>aln, ClustalW</td><td>Not possible</td><td>100 Mb</td><td>--</td></tr>
</tbody></table>

### Read alignments

<!-- straight copy of original table because special layout -->
<table border="1"><tbody>
<tr><th>Data type</th><th>File format</th><th>Index*</th><th colspan="2">Max size**</th><th>Comments</th></tr>
<tr><td rowspan="2" valign="top">Sequence read alignment</td><td><b>bam</b> <sup>¤</sup><br><a href="PrepareReadData.md" title="Preparing read data">Preparing read data</a></td><td>Required</td><td>--</td><td>unlimited</td><td>GenomeView will prompt you if there is no index and will create one for you. GenomeView can not automatically sort BAM files.</td></tr>
<tr><td>MAQ, MapView, BroadSolexa</td><td>Not possible</td><td>100 Mb</td><td>--</td></tr>
</tbody></table>

### Read coverage summary - continuous value data


<!-- straight copy of original table because special layout -->
<table border="1"><tbody>
<tr><th>Data type</th><th>File format</th><th>Index*</th><th colspan="2">Max size**</th><th>Comments</th></tr>
<tr><td rowspan="4" valign="top">Read coverage summary</td><td><b> <a href="PrepareValueData.md" class="mw-redirect" title="Tdf">tdf</a></b> <sup>¤</sup></td><td>Native</td><td>unlimited</td><td>unlimited</td><td><a href="/TDF" class="mw-redirect" title="TDF">TDF</a> files can be created with the <a href="/Bam2tdf" title="Bam2tdf">bam2tdf</a> tool that is available for <a rel="nofollow" class="external text" href="https://sourceforge.net/projects/genomeview/files/TDformat/">download.</a></td></tr>
<tr><td>bigwig</td><td>Native</td><td>unlimited</td><td>unlimited</td><td>This format can be used for any wig file, not just read coverage</td></tr>
<tr><td><a href="Pileup.md" title="Pileup">pileup</a></td><td>Required</td><td>--</td><td>unlimited</td><td>The pileup format becomes slow when you have extreme read depth (&gt;5000 x coverage)</td></tr>
<tr><td>wig</td><td>Not possible</td><td>50 Mb</td><td>--</td><td>We strongly recommend to <a href="Wig2tdf.md" title="Wig2tdf">convert your wig files to TDF</a>. 
GenomeView can automatically convert wig files to TDF. Caveats: 'track' information should all be on a single line, 'browser' lines will be ignored as the are specific to the UCSC Genome Browser. WIG files need to be sorted by chromosome and by genomic coordinate within the chromosome. BedGraph as well as Wiggle_0 format is supported. For the wiggle_0 type, both variableStep and fixedStep should work.</td></tr>
</tbody></table>


###  Genome variation and diversity

<!-- straight copy of original table because special layout -->
<table border="1"><tbody>
<tr><th>Data type</th><th>File format</th><th>Index*</th><th colspan="2">Max size**</th><th>Comments</th></tr>
<tr><td>Genome variation</td><td><b> <a href="PrepareVcfData.md" class="mw-redirect" title="Vcf">vcf</a></b> <sup>¤</sup></td><td>Not recommended</td><td>--</td><td>unlimited</td><td>It is recommended to run <a href="/Reducevcf" title="Reducevcf">reducevcf</a> on VCF prior to loading them, this will speed up the loading time significantly.</td></tr>
</tbody></table>


### Allele diversity

<!-- straight copy of original table because special layout -->
<table border="1"><tbody>
<tr><th>Data type</th><th>File format</th><th>Index*</th><th colspan="2">Max size**</th><th>Comments</th></tr>
<tr><td>Allele diversity summary</td><td><b> <a href="Pileup.md" title="Pileup">pileup</a></b> <sup>¤</sup></td><td>Required</td><td>--</td><td>unlimited</td><td>The pileup format becomes slow when you have extreme read depth (&gt;5000 x coverage)</td></tr>
</tbody></table>


* Indicates whether this file format can/should be indexed. 

** Recommended maximum file size. First value is without index, the second with index. This values are only guidelines. When loading multiple data sets, you should add the sizes.

*** Unindexed data files can be gzip compressed.

¤ Recommended file format for this data type.


## Output formats

(Modified) annotations can be saved as either GFF or EMBL.

All data that is loaded can be exported in their original format. This will not include modifications.


## Converting formats

We offer a few [tools to convert files between formats](/loki).

## Previous documentation pages

[Supported data formats ](http://genomeview.org/content/data-formats)

[Fasta files](http://genomeview.org/content/preparing-fasta-files)

[Feature files](http://genomeview.org/content/preparing-feature-files)

[Read data](http://genomeview.org/content/preparing-short-read-alignments)

[Coverage plots](http://genomeview.org/content/preparing-pileup)


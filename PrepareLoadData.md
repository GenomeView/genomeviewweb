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
# Configuration

The [behaviour of GenomeView](Visualization.md) can be configured in the Configuration panel.
The configure panel is accessed through the menu File/Configuration.

<img src="/img/configure.png" width="60%"/>

The configuration panel has several tabs, discussed in the next sections.

The panel allows a subset of the configuration file values
to be changed. The documentation of the values currently is only in the
[example configuration](https://github.com/GenomeView/genomeview/blob/master/src/main/resources/conf/default.conf) file.

## Structure View
This configures the [Structure Track](GeneStructureTrack.md).

* Show only Methionine as start codon (on)
* Show structure track on start-up (on)
* Height of track in pixels (on)
* Color start codons (on)
* Color stop codons (on)
* Color nucleotides (on)
* Color splice sites (overrides nucleotide coloring)  (on)
* Maximum number of features to display (on)

## AA & nucleotide colors
In this tab you can adjust the colors of the various nucleotides.
The default is that

|Nucleotide|Color|
|---|---|
|A|red|
|T|green|
|G|blue|
|C|yellow|
|N|black|

## Feature Track
This configures the [FeatureTrack](FeatureTrack.md)
* Force labels on features (off)
* Colors of feature types: 
   * color for NORMAL
   * color for  UTILITY 
   * color for POPUP


## Short Reads
This configures the [ShortReadTrack](ShortReadTrack.md).

* height of coverage graph. what is this, number of lines available in the plot? (50)
* Heigth SNP track. Is a "SNP track" a short read? (40)
* Minimum coverage for SNPs to be shown. (10)
* Maximum number of displayed reads. (25000)
* Maximum range in nucleotide to display individual reads (25000)
* Max display depth of stacked reads (50)
* Draw connection between paired reads. (on)
* max number of reads to cache. (500000)
* max distance between paired reads. (2000)
* Color reads mapping to the forward strand for sense transcripts (green)
* Color reads mapping to the reverse strand for sense transcripts (blue)
* Color reads mapping to the forward strand for anti-sense transcripts (orange)
* Color reads mapping to the reverse strand for anti-sense transcripts (cyan)
* Color of line between paired reads (magenta)
* Mate different chromosome (magenta)
* Missing mate (red)
* Splitting color (magenta)
* Splicing color

## Pile Up Tracks
This configures the [Pileup track](PileupTrack.md)

* cross connect the track scaling (off)
* Should all tracks use dynamic range? (off)
* Should all tracks be log scaled  (off)
* Max height of pileup track (1)
* switch from bar chart to line graph at ... (1000000000)

## Comparative track
This configures the [Multiple Alignment Track](MultipleAlignmentTrack.md)

* Enable comparative annotations. (on).
* Annotation type for comparative annotations: (`CDS`)
* Max visible range of comparative annotation: (50000)
* Display extended names (off)

## Miscellaneous
* Max zoom-out size (25000000)
* Monitor network connection (on)
* Enable dual-screen mode (off)
* Allow only one instance of GenomeView (off)
* Enable genetic code selection (off)
* Resolution increase factor (4)
* select preferred language (automatic)
* disable url caching (on)
* reset configuration (click to reset all)
* empty cache



# Edit the config file
You can also [edit the config file directly](ConfigurationOptions.md).

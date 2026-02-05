# Tracks

The tracks pane shows the data of the currently selected chromosome (as selected in the toolbar).

Every imported data file is shown in another track, using a visualizer appropriate for the type of the data. 

<img src="/img/dmelan.png" />
<b>Example: Tracks pane with 5 tracks</b>

### Track List
On the right side of the application window there is an overview of all tracks that available for the currently selected chromosome. 


<img src="/img/track_list.png" width="50%" />
<b>Typical track list pane</b>

You can 
* reorder the tracks by dragging them up and down in this table
* hide a track by clicking the eye icon 
* remove a track with the garbage bin icon.


### Data Types
There are a number of tracks, depending on the type of incoming data.
Click on the track type to get more information on how this type works.

|track type|short description|Jannot Type|typical file|
|---|---|---|---|
|[Gene Structure](GeneStructureTrack.md)|cursor location, zoom level, nucleotides|ReadGroup?|[fasta](PrepareFASTA.md)|
|[Feature](FeatureTrack.md)|annotations|MemoryFeatureAnnotation, GFFWrapper, BEDWrapper|[gff3, bed](PrepareGFF.md)|
|[Short-Read Track](ShortReadTrack.md)|short read alignment|ReadGroup|[bam](https://en.wikipedia.org/wiki/BAM_(file_format)), sam|
|[Pile-Up](PileupTrack.md)|shows coverage, may include SNP|PileupWrapper, SWigWrapper,TDFData, BigWigData|msf, pup, pileup, tdf|
|[Wiggle](WiggleTrack.md)|general numeric data|Graph|wig, bigWig, bed|
|[Multiple Alignment](MultipleAlignmentTrack.md)|alignment file|AlignmentAnnotation, AbstractMAFMultipleAlignment|[maf](PrepareMAF.md)|


Check [our wiki on all supported file types and conversion recommendations](DataTypes.md)

# Tracks

The tracks pane shows the data of the currently selected chromosome (as selected in the toolbar).

All visualizations in GenomeView are organized into tracks. 
A track typically holds on particular type of data or one particular data set. 
There can be multiple tracks of each type.
When loading new data, a new track is added.

<img src="/img/dmelan.png" />
<b>Example: Tracks pane with 5 tracks</b>

### Track List
On the right side of the application window there is an overview of all tracks that available for the currently selected chromosome. 


<img src="/img/track_list.png" width="50%" />
<b>Typical track list pane</b>

You can reorder the tracks by dragging them up and down in this table, hide them by clicking the eye icon or remove them with the garbage bin icon.

### Data Types
There are a number of tracks, each tightly linked with some data type.
Click on the track type to get more information.

|track type|short description|typical file|
|---|---|---|
|[Gene Structure](GeneStructureTrack.md)|cursor location, zoom level, nucleotides|fasta|
|[Feature](FeatureTrack.md)|annotations|gff, bed|
|[Wiggle](WiggleTrack.md)|Unknown|wig, bed|
|[Pile-Up](PileupTrack.md)|shows coverage, may include SNP|msf, pup, pileup,tdf|
|[Multiple Alignment](MultipleAlignmentTrack.md)|maf|

# Tracks

All visualizations in GenomeView are organized into tracks. 
A track typically holds on particular type of data or one particular data set. 
There can be multiple tracks of each type.
When loading new data, a new track is added.

On the right side of the window there is an overview of all tracks that are currently available. 

<img src="/img/track_list.png" />

You can reorder the tracks by dragging them up and down in this table, hide them by clicking the eye icon or remove them with the garbage bin icon.

## Gene structure track

<img src="/img/structure_track_noCDS.png"/>

This tracks shows a number of things, some of which only are visible when you are sufficiently zoomed in. 
Things to know about this track:


* This track is divided into two by a ruler which indicates the current genomic location.
* Within this track, everything above the ruler is on the forward strand, anything below the ruler is on the reverse strand
* Both the forward strand part and the reverse strand part have a nucleotide band and 3 possible translation frame bands.
* In the default configuration, potential donor and acceptor sites will be painted in yellow and blue on the nucleotide band.
* The six reading frames have potential start and stop codons indicated in green and red.
* The light blue rectangles visualizes the structure of a gene in terms of strand and the phase of each exon. 
* The image above also shows (at the top) the extra ruler track. This allows the user to drag the ruler closer to the track thats being studied.

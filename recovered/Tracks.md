# Tracks

All visualizations in GenomeView are organized in tracks. A track typically holds on particular type of data or one particular data set. There can be multiple tracks of each type. Adding tracks for new data types that you load will be automatically done by GenomeView.

On the right side of the window there is an overview of all tracks that are currently available. 

![](/img/tracklist.PNG)

This is the list you will get when you start GenomeView without any preloaded data. 

You can reorder the tracks by dragging them up and down in this table.


## Gene structure track

![](/img/genestructuretrack.png)

This tracks shows a number of things, some of which only are visible when you are sufficiently zoomed in. 

Things to know about this track:

* This track is divided into two by a ruler which indicates the current genomic location.
* Within this track, everything above the rules is on the forward strand, anything below the rules is on the reverse strand
* Both in the forward strand part and the reverse strand part have a nucleotide band and 3 possible translation frame bands.
* In the default configuration, potential donor and acceptor sites will be painted in yellow and blue on the nucleotide band.
* The six potential reading frames have potential start and stop codons indicated in green and red.
* The structure of the gene in terms of strand and the phase of each exon. 
* You can select sequence by pressing the left-mouse button and dragging the mouse along the sequence

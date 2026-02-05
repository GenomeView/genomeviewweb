# Multiple Alignment Track

Recommended File: [MAF](PrepareMAF.md)

## Multi-fasta/ClustalW multiple alignment

<img src="/img/ma.png"/>

The Multiple Alignment Track visualizes alignments of many short-reads, 
showing how they align, and where mismatches are.

## Color keys
The following colors are used. 

|Color|meaning|
|---|---|
|Gray|mismatch with reference|
|Red|gap in alignment|
|Green|Alignment to forward strand|
|Blue|Alignment to reverse strand|
|Yellow|Reference gap|

## Zoom level
The visualization of multiple alignments depends on the zoom level.

### Zoomed widely out
When zoomed out very far, the track will not display alignments because of performance reasons.

### Zoomed out
Shows conservation plots. The alignments are displayed in gray. The more species align to a certain part of the reference sequence, the longer the gray line. Individual species are not displayed.

<img src="/img/maf_zoomC.png"/>

### Medium Zoom
Shows conservation as a gray scale. Gaps in the alignment are displayed in red.
On the middle level, we can still hover the track to see the species. An alignment on the forward strand is drawn in green, one to the reverse strand in blue.

<img src="/img/maf_zoomB.png"/>

### Zoomed in
Shows the individual nucleotides. Reference gaps are in yellow, alignment gaps in red . At the bottom of the track, the [sequence logo for the aligment](https://en.wikipedia.org/wiki/Sequence_logo) is shown.
Mismatches and gaps are shown for each alignment. Hovering over the track displays the names of the species on the left.

<img src="/img/maf_zoomA.png"/>





## Demo video
[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/iHvHLUNjBkU/0.jpg)](https://www.youtube.com/watch?v=iHvHLUNjBkU)





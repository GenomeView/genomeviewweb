# Multiple Alignment Track

Recommended File: [MAF](PrepareMAF.md)

## Multi-fasta/ClustalW multiple alignment

Multi-fasta data can be displayed on three zoom levels.
* Zoomed out: Will show conservation plots.
* Medium zoom: Shows conservation as a gray scale. Gaps in the alignment are displayed in red.
* Zoomed in: Shows the individual nucleotides. Reference gaps are in yellow, alignment gaps in red . At the bottom of the track, the sequence logo for the aligment is shown.


<img src="/img/ma.png"/>

## MAF formatted multiple alignment

[Details on the MAF format](https://cgwb.nci.nih.gov/goldenPath/help/maf.html)

Demo video showing the multiple alignment track.

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/iHvHLUNjBkU/0.jpg)](https://www.youtube.com/watch?v=iHvHLUNjBkU)



Multiple alignments can be displayed in three zoom levels.

* The most detailed level shows mismatches and gaps for each alignment. Hovering over the track displays the names of the species on the left.
<img src="/img/maf_zoomA.png"/>

* On the middle level, we can still hover the track to see the species. An alignment on the forward strand is drawn in green, one to the reverse strand in blue.
<img src="/img/maf_zoomB.png"/>

* When we zoom even further out, the alignments are displayed in gray. The more species align to a certain part of the reference sequence, the longer the gray line. Individual species are not displayed anymore.
<img src="/img/maf_zoomC.png"/>

After this, zooming further out will not display alignments anymore because of performance reasons.

Color key:

|Color|meaning|
|---|---|
|Gray|mismatch with reference|
|Red|gap in alignment|
|Green|Alignment to forward strand|
|Blue|Alignment to reverse strand|



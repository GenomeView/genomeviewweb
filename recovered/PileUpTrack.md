# PileUp Track

The pile up track can consists of to information parts. The first one, the coverage plot, is always present, the second, the SNP plot, is only displayed if the loaded data set has the required information.

Typically coverage-only data files are TDF files, while coverage+SNP files are prepared using samtools pileup. [More information on preparing pile-ups](PreparePileup.md)

![Pile up track overview](/img/pileup.PNG)

![Detailed description of component of the pile up track](/img/pileup2.PNG)


=================== OLDER VERSION
The pile up track is used on two zoom levels.


## Regular View

The regular view actually shows two tracks: the number of matching reads, 
and a detailed view of mismatches by nucleotide. 
The green area represents the number of reads on the forward strand, 
the blue the number of reads on the reverse strand, and the 
yellow plot shows the sum of both.
Hoovering over a position shows you the exact number of matches, mismatches and coverage.

<img src="/img/pileup_zoomin.png"/>

SNP view (Red: A; Blue: G; Yellow: C and Green: T):

<img src="/img/pileup_snpzoom.png"/>


## Zoomed-out view
Zoomed out enough, the view switches to a simpler graph 
that only represents the coverage (same as the yellow plot of 
the zoomed in view) and doesnt allow for hoovering anymore.

<img src="/img/pileup_zoomout.png"/>



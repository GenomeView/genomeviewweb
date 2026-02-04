# PileUp Track

Recommended File: [tdf](PrepareTDF.md)

Legacy Files: msf, pup, pileup

[Configuration Options](Configure.md#pile-up-tracks)

The pile up track can consists of to information parts. The first one, the coverage plot, is always present, the second, the SNP plot (Single-nucleotide polymorphism), is only displayed if the loaded data set has the required information.

Typically coverage-only data files are TDF files, while coverage+SNP files are prepared using samtools pileup. [More information on preparing pile-ups](PrepareTDF.md)

![Pile up track overview](/img/pileup.PNG)
<bPile up track overview</b>


![Detailed description of component of the pile up track](/img/pileup2.PNG)
<b>Detailed description of component of the pile up track</b>


![](/img/strandspecificTDF.PNG)
<b>A strand-specific coverage plots</b>


## Zoom levels

The pile up track is used on two zoom levels.


### Regular View

The regular view actually shows two tracks: 
1. the standard pileup graph with the number of matching reads, 
2. an SNP view with a detailed view of mismatches by nucleotide. 

#### Pile-up
This standard plot shows the number of matching reads with colors
|Color|Meaning|
|---|---|
|green|the number of matching reads on the forward strand|
|blue| the number of matching reads on the reverse strand|
|yellow|the sum of both.|

Hovering over a position shows you the exact number of matches, mismatches and coverage.

<img src="/img/pileup_zoomin.png"/>

#### SNP view
Mismatches by nucleotide
This shows the SNP view using these colors

|Nucleotide|Color|
|---|---|
|A|Red|
|G|Blue
|C|Yellow|
|T|Green|

<img src="/img/pileup_snpzoom.png"/>


### Zoomed-out view
Zoomed out enough, the view switches to a simpler graph 
that only represents the coverage (same as the yellow plot of 
the zoomed in view) and doesn't allow for hovering anymore.

<img src="/img/pileup_zoomout.png"/>



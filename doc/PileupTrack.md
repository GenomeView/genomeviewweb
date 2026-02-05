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

You can also provide strand-specific TDF data:

![](/img/strandspecificTDF.PNG)
<b>A strand-specific coverage plots</b>


## Zoom levels

The pile up track is used on two zoom levels.

### Zoomed-out view: Coverage
Zoomed out enough, the view shows only the coverage plot
 and doesn't allow for hovering.
<!--
<img src="/img/pileup_zoomout.png"/>
-->

<img src="/img/pileup_zoomin.png"/>
Standard coverage plot

This coverage plot shows the number of matching reads with colors

|Color|Meaning|
|---|---|
|green|the number of matching reads on the forward strand|
|blue| the number of matching reads on the reverse strand|
|yellow|the sum of both.|



### Zoomed-in View: Coverage+SNP

When zoomed in, an SNP track is added to the coverage plot,
The SNP track shows mismatches per nucleotide.
Also, Hovering over a position now shows you the exact number of matches, mismatches and coverage.

These colors are used [According to the settings](Configure.md):

|Nucleotide|Color|
|---|---|
|A|Red|
|G|Blue
|C|Yellow|
|T|Green|

<img src="/img/pileup_snpzoom.png"/>
<b>zoomed in: a coverage and an SNP plot</b>



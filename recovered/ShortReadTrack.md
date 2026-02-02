# Short Read Track

In Short Read sequencing, a genome is broken into small but overlapping fragments for analysis and stitched together afterwards.

Short read are displayed in the Short read track as color boxes that are in some cases connected with pink lines. The pictures belows should give you an idea what the meaning is of the various visual clues.

Short read are displayed in the Short read track as short green or blue blocks. There are two different zoom levels.

The zoomed out view gives a high level view of the short reads. From a certain amount of reads at overlapping positions, there is a cutoff for performance reasons (the horizontal read line). The cutoff can be changed in the settings.

<img src="/img/short_reads_single_zoomout.png"/>

Zooming in gives of course a more detailed view. Gaps, insertions and deletions are marked (see color coding below) and the reads themselves are colored darker or lighter according to the read quality. The darker the read, the better it matches the reference sequence. The figure below is zoomed in that far that you can read the mismatched nucleotides. 

<img src="/img/short_reads_single_zoomin.png"/>


Paired end reads are displayed in a similar way. The pairs are connected by a purple line.

Zoomed out:
<img src="/img/paired_end_zoomout.png" />

Zoomed in:
<img src="/img/paired_end_zoomin.png"  />


### Colors
The colors in the default color scheme are as follows.

|Color|Description|
|---|---|
Green|Read mapped to the forward strand from a sense fragment in a PE library or from a single end library|
|Blue|Read mapped to the reverse strand from a sense fragment in a PE library or from a single end library|
|Cyan|Read mapped to the reverse strand from an anti-sense fragment in a PE library|
|Orange|Read mapped to the forward strand from a anti-sense fragment in a PE library|
|Yellow|Mismatch between the read and the reference, the read nucleotide will be shown when zoomed in|
|Red|Gap/deletion in the read|
|Black|Insertion in the read. Hover over them to see inserted bases.|
|Gray|Insertion in the read that is a multiple of 3. Hover over them to see inserted bases.|
|Purple/Pink|Connection between two reads from a paired-end library (thin line), or connection between parts of a single read aligned over a splice junction (thick line). Both the PE connections and splice junctions ones will be shown simultaneously in data sets that have that information.|


=====================
LATEST

Short read are displayed in the Short read track as color boxes that are in some cases connected with pink lines. The pictures belows should give you an idea what the meaning is of the various visual clues.


![Short read track, zooming in from left to right](/img/shortread5.PNG)


<strong>Default color scheme</strong>
<table>
<tr><td><strong>Color</strong></td><td><strong>Description</strong></td></tr>
<tr><td>Green</td><td>Read mapped to the forward strand from a sense fragment in a PE library or from a single end library</td></tr>
<tr><td>Blue</td><td>Read mapped to the reverse strand from a sense fragment in a PE library or from a single end library</td></tr>
<tr><td>Cyan</td><td>Read mapped to the reverse strand from an anti-sense fragment in a PE library</td></tr>
<tr><td>Orange</td><td>Read mapped to the forward strand from a anti-sense fragment in a PE library</td></tr>
<tr><td>Yellow</td><td>Mismatch between the read and the reference, the read nucleotide will be shown when zoomed in</td></tr>
<tr><td>Red</td><td>Gap/deletion in the read</td></tr>
<tr><td>Black</td><td>Insertion in the read. Hover over them to see inserted bases.</td></tr>
<tr><td>Gray</td><td>Insertion in the read that is a multiple of 3. Hover over them to see inserted bases.</td>
<tr><td>Purple/Pink</td><td>Connection between two reads from a paired-end library (thin line), or connection between parts of a single read aligned over a splice junction (thick line). Both the PE connections and splice junctions ones will be shown simultaneously in data sets that have that information.</td>
</tr>
</table>

<em>Note that some older alignment software does not include the correct information in the BAM file and that the color scheme may be off for those files. Use common sense when interpreting results!</em>

![Overview of visual clues in the short read track](/img/readdetails.PNG)

<!--
[img_assist|nid=255|title=Overview of visual clues in the short read track|desc=|link=popup|align=none|width=600|height=384]

[img_assist|nid=258|title=Hovering over reads shows detailed information about the read|desc=|link=popup|align=none|width=600|height=282]

-->

![Hovering over reads shows detailed information about the read](/img/readdetails2.PNG)


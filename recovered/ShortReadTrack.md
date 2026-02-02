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


# Colors
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



---- latest version


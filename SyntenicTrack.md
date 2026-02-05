# Syntenic Track

A syntenic maps aims to show similar blocks of genes in one genome or
between different genomes. 
Study of synteny can show how the genome is 
cut and pasted in the course of evolution

### Fully zoomed out
![](/img/syntenic1.png)
<b>zoomed out entirely, so you see the complete TB genome (~4.5Mb).</b>

This shows whole genome synteny for 14 organisms, the color coding is according to the position in reference strain.

For example the second colored bar shows a bunch of blue at the beginning, which indicates that in the reference genome this sequence was near the end of the genome.

Only syntenic blocks over 1kb are shown.




### Annotation and conservation 

![](/img/syntenic2.png)
<b>zoomed in a bit</b>

This was obtained by zooming in from the previous one. The top blue and orange blocks are regular annotation features, in this case coding sequences. Below those two tracks, there are the synteny tracks that were also shown in the previous screenshot.

Below the synteny tracks, there a line graphs that indicate the pair wise conservation with the reference sequence. These graphs are the high-level view of the underlying multiple alignments.

The bottom track has two line graphs, a blue one and a red one. The red line represents the footprint of the position, i.e. in how many organisms is the nucleotide available. The blue line shows the conservation of each individual nucleotide over all organisms.

### Detailed conservation

![](/img/syntenic3.png)
<b>zoomed in more</b>

This shows as the top graph a detailed view on the gene structure. It still shows two tracks of annotation (blue and orange blocks and has more detailed zoom to multiple alignment.

The detailed gene structure view allows you to see details on the strand a frame of a gene, the presence of start codons (green), stop codons (red) and splice sites (blue-yellow). This is also the panel that can be used to edit the structure of a gene by dragging the edges of a the gene.

The conservation graphs of the multiple alignment have been replaced with a more detailed view to the multiple alignment. The color coded columns indicate conservation of single nucleotides over the loaded organisms. The scale goes from black to white, from perfect conservation (black) over all species to less than 50% conservation (white). The red blocks indicate gaps in the alignment.

### Sequence logo and nucleotide level 

![](/img/syntenic4.png)
<b>fully zoomed in</b>

When zooming in further, one can see the individual nucleotides and amino acids in the gene structure and the multiple alignments. The bottom footprint track has been replaced with a sequence logo for the multiple alignment, showing the relative frequency of all nucleotides in a particular position.

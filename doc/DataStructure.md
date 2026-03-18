# Data Structure

To understand how to format data and how to control and configure your tracks,
it's necessary to understand how GenomeView stores and relates loaded data.

At the top level, GenomeView stores data in an EntrySet, which contains
a set of  Entry's, each associated with a unique EntryID. Typically,
an EntryID is the name of a chromosome / genome / gene.

The Entry itself contains another set of data, each data having its own unique DataID.
Typically the entry data contains the sequence letters (ACGT string), annotations, 
syntenic information, etc, each stored under a different DataID.

It is crucial that your data is consistent about EntryIDs.
The various data types all have their own way of mapping 
into the EntrySet and Entry's. 

How this is done is described on the wiki page for each [data type](DataTypes.md).

For example, you will find that [Fasta files](PrepareFasta.md) load each sequence in its own entry,
using a name extracted from the descriptor line. 

Also you can find that the names in [syntenic files](PrepareSenteny.md) 
refer to EntryID's.

Also you can find three that syntenic files show as [Syntenic Tracks](SyntenicTrack.md)

And there you find that the syntenic track shows information matching the genome/chromosome/gene name
as selected.

So all these work together and bottom line you need to ensure the used EntryIDs in the 
files (`.fasta` and `.syn` in this example) match. 


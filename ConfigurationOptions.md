# Configuration Options

These pages discuss how to configure a number of things using the configuration file.

There are several places from where GenomeView tries to load configuration information. It will look in the specified order.

* Config files specified in the session file
* [Configuration supplied on the command line](CommandLineOptions.md) or start-up URLwith the --config option.
* Personal config file. This can be changed through the menu File -> Configuration.
* The settings in the [Configuration menu](Configuration).
* Default configuration present within the release package


The default configuration file is [here](https://github.com/GenomeView/genomeview/blob/master/src/main/resources/conf/default.conf)
and is primary source of information regarding configuration options. 

## Configuring track order
To configure the order of tracks you can use the `track:weight:XXX` configuration option. This will give a weight to each track and heavier tracks will be placed lower on the screen.

For annotation features you have give the type as XXX. You cannot use the file name method below. For example:

```
 track:weight:gene=1
 track:weight:mRNA=2
 track:weight:CDS=3
```

For any other data type, you have to specify the file file name or URL where the data resides. You cannot use the method described above.

Some examples for remote files:
```
 track:weight:http://www.broadinstitute.org/software/genomeview/demo/idea_challenge/Directional_RNAseq/MCF7_dir100.bam=100
 track:weight:http://www.broadinstitute.org/software/genomeview/demo/idea_challenge/Directional_RNAseq/MCF10_dir75.bam=200
```

This will also work with local files:
```
 track:weight:W:\thomas\rnaseq.bam=400
 track:weight:W:\thomas\chipseq.bam=500
```

Deciding which method to use depends on the type of data: annotation are by type, other data is by file name.

## Configuring track visibility
To configure the initial visibility of tracks you can use the `track:visible:XXX` configuration option. This will tell GenomeView whether the track is initially visible or hidden

For annotation features you give the type as XXX. For example:

```
 track:visible:gene=true
 track:visible:mRNA=false
 track:visible:CDS=true
```

For any other data type, you have to specify the file file name or URL where the data resides. 

Some examples:
```
 track:visible:http://www.broadinstitute.org/software/genomeview/demo/idea_challenge/Directional_RNAseq/MCF7_dir100.bam=true
 track:visible:http://www.broadinstitute.org/software/genomeview/demo/idea_challenge/Directional_RNAseq/MCF10_dir75.bam=false
```

## Configuring track aliases


To change the name that appears next to each track to something that is 
more informative than the fully qualified path name, you can use the 
`track:alias:XXX=ALIAS` configuration option. This will tell GenomeView which 
name it should display

For annotation features you give the type as XXX. For example:
```
 track:alias:gene=All the genes
 track:alias:mRNA=MRNA track
 track:alias:CDS=Coding sequence features
```

For any other data type, you have to specify the file file name or URL where the data resides. 

Some examples:
```
 track:alias:http://www.broadinstitute.org/software/genomeview/demo/idea_challenge/Directional_RNAseq/MCF7_dir100.bam=Directional RNA-seq MCF 7
 track:alias:http://www.broadinstitute.org/software/genomeview/demo/idea_challenge/Directional_RNAseq/MCF10_dir75.bam=Shorter (75) directional RNA-seq for MCF 10
```

Note: Track aliases are unrelated to aliases set up in the session file with the ALIAS command. You can make a track alias in a session file with the OPTION command:
```
 OPTION track:alias:gene=All the genes
``` 

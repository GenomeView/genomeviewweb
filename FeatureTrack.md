# Feature Track

Recommended File: [gff, bed](PrepareAnnotation.md)

The feature track can display a multitude of annotation information. Features like CDS, RNA, SNP, etc. are displayed as rectangles in different colors. A triangle on one side can indicate the strand. When zoomed in enough, feature names are displayed when available.

<img src="/img/feature_track_cds.png"/>
<b>Feature Track</b>


The labels on each of the features are encoded in the input file. The track will look for the following keys to find a label:


* protein_id
* Name
* ID
* gene
* label
* note

If none of these are found, it will display the type with the location.


You need to provide a values for any of these field for any feature you wish to have a label.
Furthermore, labels are only displayed when the box is large enough. 

If you always want them to display, there is a configuration option for that. Either available through the menu or in the config file you make for your instances.

```
track:forceFeatureLabels=true
```



## Feature List
In the main GUI, there is a Feature List shown to the right of the Visualization Tracks.

<img src="/img/featurelist.png" width="30%"/>
<b>Feature List</b>

You can search for and select features 

FIXME HOW?

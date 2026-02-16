# Menu

This page explains the various menu items. The menu is in the top of the GenomeView window.


### File Menu
The file menu deals with loading and saving tracks and general configuration

|File Menu Item|Use|
|---|---|
|[Load Data](LoadData.md)|Open data and add a track. Can be either URL or local file|
|Show Data Explorer|Similar to Load Data but shows also recently used files|
|Save Session|Saves a [GenomeView Session file](SessionFile.md)|
|Load Session|Loads a [GenomeView Session file](SessionFile.md)|
|[Save Annotation](SaveExportData.md#save-annotations)|save your added annotations.|
|[Export Data](SaveExportData.md#save-data)|Export original data you loaded|
|Export Image|Export the Visualization Frame as png|
|Configuration|Opens the [Configuration pane](Configure.md) where you can adjust preferences|
|Unload all data|removes all tracks and opens the data explorer|
|Exit|Closes GenomeView|

### Edit Menu
The edit menu deals with editing sequences and annotations

|Edit Menu Item|Use|
|---|---|
|Copy Sequence|Copy a [selected sequence](MouseShortcuts.md)|
|Clone Selected Feature|Clone feature selected in [Feature List](FeatureTrack.md#Feature-List).|
|Remove Selected Feature|Remove feature selected in [Feature List](FeatureTrack.md#Feature-List).|
|Remove Selected Location|
|Edit Selected Structure|
|Create Feature from Coordinates|Adds feature from coordinates.  Fill in the coordinates of the feature you want to create. One location is defined as two coordinates with two dots (..) between, multiple locations are separated with a comma (,). For example: 100..200,300..400 creates a feature with two locations, one from 100 to 200 and the other from 300 to 400.|
|Create Feature from Selection|Adds feature from [selected range](MouseShortcuts.md#structure-panel-specific-actions)|
|Merge selected Features|?? you can not select multiple features?|
|Split feature between 2 selected locations| ? |
|Extend to next start codon|extend the selected feature|
|Extend to next stop codon|extend the selected feature|


### Navigation Menu
The navigation menu is to search in the tracks
|Navigation Menu Item|Use|
|---|---|
|Go to Position| |
|Go to track| |
|Search| ?|

### Selection Menu
|Selection Menu Item|Use|
|---|---|
|Show DNA or Proteine sequence|shows list of nucleotides in selection. You also have buttons to search the sequence in BLAST databases and export to FASTA |
|Clear Feature Selection| de-selects the selected feature(s)|
|Clear region selection|de-selects the selected region|
|Zoom to selected features|zooms such that the features in the current selection are screen filling. CHECK|
|zoom to feature selection|Zooms such that all features in the current selection are in view. CHECK|
|zoom to location selection|?|

### Plugins
Will be removed


###
|Help Menu Item|Use|
|---|---|
|help|Opens browser at documentation page. |
|Post bug report or feature request|Open browser at github.com/GenomeView/genomeview/issues. You need a github account to post issues here. |
|List of installed modules|will be removed |
|Plugin documentation|will be removed|
|About|shows about box|

# Frequently Asked Questions

If your problem is not addressed here, please mail to 
support@genomeview.org.

> [!TIP]
> If you discover a bug or you have a feature request, please log a ticket on the bug tracker.

In order to help you as quickly as possible, make sure to include the following information:

*    Which version of GV are you running?
*    What operating system? OS X, Windows, ...?
*    Which version of Java are you running?
*    If you have problems with specific files, it is extremely helpful if you can share to files for us to reproduce the problem. Are those files local or remote?
*    Include the log file from the problematic GenomeView run. Instructions to find log files can be found [here](Readme.md#log-files)


### How are display labels of features determined?

GenomeView will use the following feature qualifiers in order to try and find a display name

* protein_id
* Name
* ID
* gene
* label
* note

If none of these are found, it will display the type with the location.

### Why are my edits not being exported?

The bai file needs to have the extension .bam.bai, not just bai.

This will be fixed in a future release, but versions prior to 2170 may have problems with this.


### Can I keep CDS from different files in separate tracks?

The short answer is no. However, there is a simple work-around and there is a good reason why we can't do it.

Workaround:
You can rename your CDS features in one file to CDS_Method1 or CDS_old and have the other file just have the regular CDS, then they will appear in separate tracks.

It was a deliberate decision to distinguish annotation items by type rather then by source.

### How do I create PDF/vector graphics/publication images?

You will want to install the Save2PDF plugin
http://genomeview.org/plugins  DL

Download the zip-file, and extract it.

Copy the jar file to your '.genomeview/plugin' folder.

On Linux, it should be (hidden) in your /home/ directory.
On Windows: C:\Users\\.genomeview\plugin

Next time you start GenomeView, there now should be a menu item under
'Plugins' saying "Export > Export image as PDF...".


### Why are my bam/tdf files not showing?

Oracle made a change in Java7u21 that broke support for BAM files in one of our dependencies.

Upgrading to a recent version (>=2144) of GenomeView resolves this issue.


### Where do I find the log files?
[Please refer to here](README.md#Log-files)


### How do I show annotation on a multiple alignment?
Prerequisite: The multiple alignment needs to be in maf format.

To load a separate annotation onto each genome for a multiple
alignment in Genomeview:

1. Go to "Configuration" under "File". 
2. Click the arrow in the top right until the "Comparative track" menu appears. 
3. Check the box labeled "Enable comparative annotations".


### Why does my multiple alignment load as reference sequences?
This is most likely caused by an index file. If you want to have the multiple alignment visualization for a multi-fasta file, you should not have an index file.

Make sure that there is no file with the extension '.fai' with you fasta file.

If the problem persists, there may be an index file cached by GenomeView. You can remove cached index files by removing all files in the .genomeview/index folder in your home directory.


### Where do I find documentation?
This list does not cover all topics, but should cover the most common ones. The menu on the left with the title 'Documentation' has links to all manual pages.




### I loaded a new file and its not showing
For data to get linked, the identifiers in the files have to match. Very likely if your data is not showing, the identifiers where not the same and they didnt get linked. To diagnose this problem, go to the Entry drop down list near the top of the screen, below the menus and click it. If there are multiple entries there, and you didnt know you loaded multiple, you have mismatching entries. Youll have to correct them in the files.

### Where do I change what I see in the \"gene structure view\"?
On the right there is a "Track list". There you can select which features are displayed on the structure and annotation views.

### I find the tracks too large (too high)...
open the menu `file /configuration`. Choose the Structure View\"
there set the height of the track in pixels [default is 20px]

### Where are the configuration and plugin directory of GenomeView?
The GenomeView configuration directory, this directory is named `.genomeview` and resides in your home directory. On a *nix system your home directory is typically located at `/home/username`. On Window XP it is found at `C:Documents` and Settingsusername.

### I was able to start GenomeView once, but now it wont work anymore
In the configuration directory there is a file named `personal.conf.gz`. Delete this file and try again. If it still doesnt work, file a bug report.


# 2250
There have been a number of changes since the last update that was posted.

First of all, weve switched our versioning system to git, this should make it more straight-forward for more contributors to join.

Weve added some <a href="/manual/Session_files">extra instructions to be used in session files</a>, this should make session files more versatile.

Redesign rendering of read tracks which should speed up rendering significantly.

Added wild cards to motif searches.

Added code automatic plugin installation option in session files.

Weve fixed tons of bugs and glitches in both data handling and graphical display.

Added a synonym naming framework that allows you to use multiple names for the same sequence entry.

Fixed issues introduced by Java 7

Added I18N support, if you want to add a language, get in touch with us.




# 2020
[img_assist|nid=410|title=Revamped save dialog|desc=|link=none|align=left|width=270|height=400]

Changes in GenomeView
- revamped save dialog to be more comprehensive and intuitive
- ghost outline for total coverage is lighter
- comparative annotations show with intron-exon structure
- use synonym service to find a common name for data entries
- remember last loaded data an location for next start-up
- confirm dialog when closing GV
- location and individual config options can be specified in sessions files


Changes in JAnnot
- fixed issue in EMBL parser for valueless keys
- fixed issue in Genbank parser for values containing slash
- GTF parser better handles quotation marks
- Added synonym service as a config file, this will be expanded in the future

# 1983
Biggest novelty over the past few months is the ability to create and visualize strand-specific coverage plots.

[img_assist|nid=383|title=Strand-specific coverage plots|desc=|link=none|align=none|width=500|height=250]

<p>To create these files, you can use the latest version of <a href="/content/preparing-pileup#tdf"> tdformat</a>

Ive started a twitter account to make smaller announcements as they come online, so feel free to follow <a href="https://twitter.com/intent/follow?screen_name=GenomeView">@GenomeView</a> to stay up to date on any new developments.

There have been quite a few smaller improvements between this version and the previous announcement of 1805, which includes quite a few improvements that already made it into the first paper:
- GTF is now supported as a full format with its own parser
- fixed several graphical glitches in the gene structure view
- added a simplified color scheme for NGS reads
- visual indication of reads that have their mate mapping to another chromosome
- added all bacterial genomes from NCBI as a repository
- fixed graphical glitch when reads have soft-clipping at the beginning
- More checks on newly created features so they are not out of bounds of the reference
- User can no longer selection sequence outside the reference range
- Improved display labels on tracks
- Track aliases
- fixed graphical glitches in coverage plots
- File URLs that have an = sign get properly processed
- log-scaling for coverage tracks
- Improved detection of species/contig distinction in multiple alignment to reduce the number of entries.
- support multi-column wig files
- loading files from a session is more suble, no longer a bright green pop-up in the middle of your screen that blocks everything else.
- parser detection also works for sessions files, they can now be loaded as regular files
- tracks now have individual configuration menus
- have to option to automatically normalize by the mean coverage for coverage plots
- fixed one-off in search results on the reverse strand 


Technical improvements:
- more and better logging so its easier to help you when things break
- stream caching so the server is only contacted once per file
- better propagation of javascript instructions when multiple GenomeView instances are running
- made javascript instructions more robust and detect duplicate and garbled instructions 
- fixed some memory leaks of objects that were not released when data unloads



# 1805
The recent releases between 1682 and 1805 have added a number of new feature to GenomeView, a number of improvements to existing features as well as a whole set of bug fixes.

From now on, the bigWig format, thats been in use over at UCS, is supported by GenomeView. bigWig is used to  store large continuous value data files.

The save and export functionality has been expanded to allow more fine grained control of what data has to be saved.

We have significantly improved performance of compressed and indexed multiple alignments to allow bigger whole genome alignments at increased speed and reduced memory usage.

Bug fixes and other improvements:
- fixes issues in GenBank and wig parser
- more user interaction feedback when things go wrong
- fixed several visual glitches in various visualization tracks
- made more long-running actions multi-threaded to improve interactivity
- hacked around around a bunch of Java bugs limitations on Mac
- improved single-instance mode
- entries in drop-down are ordered naturally


# 1682
Release 1682 is again a step forward in making GenomeView as user-friendly as possible.  
Major new features:
<ul>
<li><b>Automagic index creation</b>: If you try loading a file that is not yet indexed, GenomeView will now ask to do it for you.</li>
<li><b>Speed and memory improvements</b>: We have significantly optimized the way annotation feature and sequences are handled so it is easier to load monstrous draft genomes with 65,000 contigs and 500,000 annotation items without needing a gigantic computer.</li>
<li><b>Heartbeat monitor</b>: We have added visual clues to the current memory use and network connectivity to help diagnose problems when GenomeView decides to stop working.</li>
</ul>

As usual a number of smaller changes that fix bugs and minor annoyances:
<ul>
<li>Indexed MAF (multiple alignments) correctly switches to visualization modes, dramatically improving performance when zooming out</li>
<li>Saved session now include all data types, not just sequence and annotation</li>
<li>We have improved the configuration options of the pile-up track. They should be easier to understand now.</li>
</ul>



# 1600
Based on user feedback we have been able to fix another batch of bugs as well as introduce a number of convenient new features. <a href="/support">Keep the reports coming, we appreciate all feedback. </a>

<b>Selected changes</b>
GenomeView now remembers in which order tracks are, and will no longer jumble them if you switch chromosomes or when you restart GenomeView. It also remembers which track you made invisible.

The pileup and formats are now also loaded using background threads, which drastically improves the responsiveness of the GUI.

Fixed a recently introduced bug that made SNPs invisible.

Did some profiling and made a bunch of performance improvements.






# 1578
Based on user feedback a number of bugs have been fixed. Furthermore, we have tried to improve usability with a number of small improvements.

Release 4 of the genome of <i>Rattus norvegicus</i> is now included in the Genome Explorer.





# 1514
In this release of GenomeView the visualization of individual short reads, as well as coverage plots has been significantly improved. 

With directional RNA-seq the read sense is now visually indicated, even for paired-end data. Hovering over individual reads will show detailed information about each read. When reads of a pair overlap, this is visually indicated.

For coverage data, there is now support for the TDF file format. This format is a high-performance file format for coverage data. In the <a href="/content/preparing-pileup">manual</a> you can find instructions how to generate these files from an existing BAM file. This allows GenomeView to offer multiple aggregation functions (mean, min, max, median, percentiles, etc.) for coverage data at low resolution for little cost.

We have added some genomes to the Genome Explorer:
- Mycobacterium smegmatis
- Mouse (mm8 and mm9)

This release also fixes numerous bugs: 
- pile up should only display matches when there is diversity data
- remove tick labels in feature filter, they are often wrong with double values
- pileup tasks properly return immediately when the model wants to exit
- fixed creating features with a new feature type
- changing the type of a feature properly works when typing a new type name
- when a data type is removed, it is properly unloaded from all chromosomes
- Improved stability on OS X
- dont draw SNP track if there is no data for the SNP track
- shortread track cannot be collapsed, so dont check on it
- added more default colors

# 1415
The main new feature we want to highlight in this release is the ability to control the GenomeView applet from the webpage in which it is embedded using JavaScript. The details are laid out in the <a href="/content/integration">integration manual</a>. In short you can use JavaScript to load data and move around in GenomeView. In this context we have also made available a minimal applet that has no menu or side bar. 

Furthermore, several options to alter the appearance of GenomeView on start-up have been added.

Three new genomes were added to the Genome Explorer: M. tuberculosis and two release of the human genome (hg18 and hg19).

Internally some of the threading was redesigned to have GenomeView exit cleanly without having to call System.exit. 

Some bugs were fixed as well:
- global configuration of the pile-up track now works as expected
- paired end reads were able to stack higher than the configured maximum in some cases, this has been corrected
- scroll speed of the vertical scroll bar of the visualization frame has been increased significantly




# 1370
Release 1370 focuses on making the first-time-user experience a lot more agreeable by providing the Genome Explorer.

Genome Explorer is a portal to a set of instances of GenomeView with preloaded data. When you start GenomeView you will now be presented with the Genome Explorer which allows you to load data from a number of genomes. For now, we provide a number of tutorial genomes which illustrate a number of features of GenomeView. 

Furthermore, the Genome Explorer is also be the place where you get direct access to a large number of reference genomes. These genomes will have the reference sequence and gene annotation preloaded so you can start work directly with your data. 

Currently, we offer over 20 plant genomes in collaboration with the <a href="http://bioinformatics.psb.ugent.be/plaza/">Plaza plant comparative genomics project</a>. In the next couple of release we expect to add a number of new genomes from animals and bacteria. 

If you have any requests for genomes we should included, please do <a href="mailto:genomeview-support@lists.sourceforge.net">contact us<a/>.

While the Genome Explorer is the biggest change in this release, we have also revamped the search functionality to work better. You can now also search on chromosome/genome/entry name, not just on features.


# 1320
Release 1320 fixes a number of bugs that prevented <a href="/content/pile-track">pile up tracks </a> from showing up when loading them from a URL. Under the hood, we are also working on getting the indexing done on multiple alignment files, so expect more on that in the next release.


# 1305
In releases 1295 and 1305 we have made some more improvements to the rendering speed of some tracks, in particular when a lot of data is on screen. Furthermore, we have improved the visual clues when not all data can be displayed. Besides improving the speed, we have also fixed a number of bugs and implemented some smaller feature requests:

<ul>
<li>Menu action to extent to the next start codon</li>
<li>Configuration option to have all possible start codons considered, or just ATG</li>
<li>The order species appear in a multiple alignment can now be configured</li>
<li>It is no long possible to create features outside the sequence</li>
<li>Perform better error checking and correction on configuration files, a badly formatted config file will no longer crash the whole application</li>
<li>Fixed bug that would insert some nucleotides at the beginning of the sequence when using indexed data and viewing the first nucleotide</li>
</ul>

# 1255
In release 1255 we have improved the performance and visual representation of the short read track and the pile up track.

The short read track now also displays the connection lines properly for spliced reads when zoomed out.

The pileup track now has a pop-up with detailed information about the read coverage and polymorphisms at a particular site.



# 1227
The latest snapshot of GenomeView has some new features as well as a number of bug fixes.

The main novelty is the improved pile-up tracks. The pile-up track can now show the coverage information from forward and reverse reads separately. This makes inspection of Chip-Seq data easier than ever.






# 1198

We are pleased to announce that we have released a new version of GenomeView which includes a huge number of improvements.

<ul>
<li>Support more file formats</li>
<li>Support for indexed file formats created by SAMtools (tabix, faidx). This required a redesign of the data handling framework.</li>
<li>GenomeView is now also available as Applet and as JComponent for integration in other websites and tools.</li>
<li>Simplified GUI significantly</li>
<li>Asynchronous data fetching for some data types, this will be expanded on in the future</li>
<li>Fixed  a significant number of bugs: 2902516, 2974564, 2947910, 2947908, 2969208, 2957908, 2835050, 2888150, 3053572, 3053564, 3053533, 3053527, 3053516, 3041869, 3009517, 2934863, 2903299, 2902517, 2898589, 3046207, 3053511</li>
</ul>

The new version is available when clicking the orange launch button in the top-right corner. We are currently testing all integration instances to make sure they work with the new version. As soon as testing is done, we will update the start-script as well. 

If you run into any problems please do contact us on the <a href="mailto:genomeview-support@lists.sourceforge.net">mailing list</a> or post a <a href="http://sourceforge.net/tracker/?group_id=208107">support ticket</a>.




# 922
There are two new visual features in GenomeView: 
1) Short read alignments contain now visual clues to the read alignment quality. Reads with a high mapping quality are colored dark, while reads with low mapping quality will be lighter.
<"width="250" src="/img/shadingsnp.PNG" alt="Picture showing shades of mapping quality" />

2) At the top of the short read track there is now also a SNP track shows the frequency of alternative nucleotides for a position. 

3) Major improvements to the visualization of the gene structure track to make it look a lot less clunky.

4) Uniform mouse-functions throughout the visualization tracks.
<!--break-->
Further bug fixes included:
2974564  	 Status bar updates
2969208  	 SNP threshold
2957908  	 configurable read-coverage track
2952768  	 Shift-drag should always select
2950609  	 right arrow broken
2947910  	 AA track layout
2947908  	 DNA line background
2946612  	 Navigation Feel
...

# 894 
GenomeView 894 is a maintenance release, fixing a number of bugs in both JAnnot and GenomeView. No stunning new features have been implemented.

<ul>
<li>Added GC as canonical donor site</li>
<li>Fixed: Short read track jumps - ID: 2916412 </li>
<li>Fixed: cannot center on small features - ID: 2946025</li>
<li>Fixed: genbank files fail to load - ID: 2945788</li>
<li>Fixed: genbank files not shown - ID: 2945787</li>
<li>Fixed: loading multiple sequence alignment - ID: 2945456</li>
<li>Fixed: wiggle parser does not split on spaces - ID: 2945136</li>
<li>Fixed: link to plugins in help menu is wrong - ID: 2940874</li>
</ul>


# 835
During the past week a number new features have been implemented, some improvements have been made and a number of bugs have been fixed.

The major addition for this release is a brand new visualization method for multiple alignments.
<em>Watch video full screen in HD mode for best quality, the video contains no sound</em>
<object width="445" height="364"><param name="movie" value="http://www.youtube.com/v/iHvHLUNjBkU&hl=en_US&fs=1&rel=0&color1=0x2b405b&color2=0x6b8ab6&hd=1&border=1"></param><param name="allowFullScreen" value="true"></param><param name="allowscriptaccess" value="always"></param><embed src="http://www.youtube.com/v/iHvHLUNjBkU&hl=en_US&fs=1&rel=0&color1=0x2b405b&color2=0x6b8ab6&hd=1&border=1" type="application/x-shockwave-flash" allowscriptaccess="always" allowfullscreen="true" width="445" height="364"></embed></object>
<!--break-->
<strong>New features</strong>
<ul>
<li>Parser for MAQ snp data</li>
<li>Parser for MAF multiple alignments</li>
<li>Complete new visualization for MAF formatted multiple alignments</li>
<li>Show insertions in short read alignments with a tooltip that shows the inserted bases.</li>
<li>Parser for TAIR TBL formatted annotation files</li>
</ul>

<strong>Improvements</strong>
<ul>
<li>Improved multiple alignment tooltip</li>
<li>Graphs can now also be displayed as bar charts</li>
<li>Tooltip with the actual value when hovering over a wiggle track</li>
<li>Double the resolution of the wiggle track</li>
<li>Implemented single-instance in a portable non-webstart way</li>
</ul>

<strong>Bug fixes</strong>
<ul>
<li>Syntenic and multiple alignment tracks are properly cleared when using clear entries</li>
<li>Fixed some race condition exceptions when loading multiple files at once</li>
<li>Alignments blocks always stick in the same place between repaints</li>
<li>Fixed missing first nucleotide value in the wiggle track</li>

</ul>


# 773
The main novelty in GenomeView 773 is the ability to properly display spliced short read alignments. Another feature that is worth mentioning before the list of changes is that you can now reorder the tracks in the track overview panel by dragging them.


Furthermore, there were a lot of improvements under the hood and some polishing fixed to the GUI. <ul>
<li>Improved logging of events for easier crash diagnostics</li>
<li>Upgraded to the latest version of SAMtools</li>
<li>Fixed some navigation issues introduced in 687</li>
<li>Made columns in the information panel unmovable</li>
<li>Fixed a couple of bugs in the wiggle track</li>
<li>Improved file type detection</li>
</ul>
<!--break-->



# 678

The development of GenomeView is ongoing. Because of the many releases, the version numbering scheme has changed. The version number will from now on correspond to the revision in the Subversion repository.

This release bring a number of improvements which include:
<ul>
<li>Improvements to the wiggle-track: fixed color coding, added logarithmic scaling, 
<li>Speed improvements: mainly for short read alignments</li>
<li>Lower memory footprint allowing more data to be loaded at once</li>
<li>Added dragn drop support, you can now drag one or multiple files onto GenomeView and it will be loaded</li>
<li>Added an option to run a single instance of GenomeView that will handle all invocations instead of starting a new program every time you click a link.</li>
<li>Fixed a number of bugs</li>
<li>Added an export function to save high resolution images from the visible data</li>
</ul>
<!--break-->




# 1.9999
These sequence of releases focused on improving a number of aspects of GenomeView. First of all support for access to BAM files was added over http, without requiring the whole file to be downloaded. Paired-end reads are now also properly linked together and visual represented as a pair. Editing genes has been made more user friendly and the configurations have been significantly expanded.

<strong>List of changes</strong>
<ul>
<li>Fixed issue with undo-redo queue</li>
<li>Hover window for short-read coverage</li>
<li>Display pairing of paired reads</li>
<li>Bug fixes all around</li>
<li>Improvements to the display of the short-read alignments </li>
<li>BAM/BAI support over http</li>
<li>Extended configuration options</li>
<li>Improved gene editing</li>
<li>Navigator improvements</li>
<li>Mark reference area when selecting a CDS</li>
</ul>


# 1.19992
Release 1.9992 of GenomeView finally provides a way to store sessions and restore them later on. For now the functionality is rather basic and GenomeView only keeps track of what data is loaded and will restore it when loading a session. 

The visualization of short read data has been improved. When hovering over the pile-up plot, you get a pop-up showing the actual number of reads. Also a number of additional constraints and checks have been implemented  to keep GenomeView alive and responsive when browsing data sets that have extreme high coverage (>10,000 stacking depth) in some places. Furthermore, the pile-up graph is now split in forward and reverse strand coverage.

<strong><a href="http://sourceforge.net/projects/genomeview/files/">Download latest version of GenomeView and JAnnot</a></strong><br>
The preferred way to start GenomeView is the web start you find in the top-left corner of the site.<br>
<strong><a href="/jannot/1.98/">JAnnot 1.98 API docs</a></strong>
<!--break-->
<strong>List of changes</strong>
<ul>
<li>Session (re)store (#2560880)</li>
<li>Split pile-up coverage graph in forward and reverse coverage</li>
<li>Improvements to short read representation to keep it more responsive(#2849434)</li>
<li>Fixed navigation bug where all key navigation would be done twice (#2851257)</li>
<li>Implemented pop-up screen that shows the actual read coverage when hovering over the pile-up graph (#2839254)</li>
</ul>

# 1.199
During the past few weeks a lot of features have been added and improved in GenomeView and JAnnot. Most of the intermediate versions have only been made available internally in the SVN, but I think its time for another public release. There are three notable changes from version 1.90. First the GUI is reorganized to be easier to use.  Second, we have added support for short read (RNA-Seq, Chip-Seq, etc.) data Next-generation sequencing can now be visualized with GenomeView. And third, we have added support for authentication and SSL to ensure secure transfer of your data.

<strong><a href="http://sourceforge.net/projects/genomeview/files/"/>Download latest version of GenomeView and JAnnot</a></strong>
The preferred way to launch is still the web start you find in the top-left corner of the site.


<strong><a href="/jannot/1.96/">JAnnot 1.96 API docs</a></strong>

A non-exhaustive list of improvements, changes and new features that found their way into GenomeView in the past few months is provided in the rest of the announcement.
<!--break-->
<strong>GenomeView changes</strong>
<ul>
<li>
<li>Improved search and added overlap search</li>
<li>Improved gene structure track</li>
<li>Improved feature track</li>
<li>Improved multiple alignment track: faster, less memory and better visualized</li>
<li>Improved keyboard navigation</li>
<li>New navigation panel, inspired by Argo2</li>
<li>Multi-threaded track loading</li>
<li>Removed BioMoby support</li>
<li>Removed chromosome view</li>
<li>Major GUI reorganization to accommodate removed and added features</li>
<li>Fixed a bunch of bugs and glitches</li>
<li>Added basic support for Distributed Annotation Servers (DAS)</li>
<li>Added short read support</li>
<li>Added support for authentication and SLL</li>
<li>Added caching to URLSource which makes it more efficient to retrieve data from the network</li>
<li>
</ul>

<strong>JAnnot changes</strong>
<ul>
<li>Added a top-level object called EntrySet</li>
<li>Improved detection of start and stop codons</li>
<li>Fixed bugs in a number of parsers</li>
<li>Added parsers for these formats and programs: PTT, TransTermHP, GeneMark, BroadSolexa, MapView and BAM/SAM</li>
<li>Made Sequence and MultipleAlignment significant more memory efficient</li>
<li>Improved handling of loading multiple sequences at once<li>
<li>Improved multi-threaded behavior</li>
</ul>





# GenomeView 1.90: multiple alignments and syntenic mapping

The latest version of GenomeView has two main new features: support for multiple alignments and the ability to display syntenic blocks

<strong><a href="http://sourceforge.net/projects/genomeview/files/" />Download latest</a></strong>


In the rest of the announcement you find a description of the new features with some screen shots.
<!--break-->
<div style="float: left;"> <a href="/images/1.90-1.png"><"alt="Screenshot 1" width="512" height="394" src="/images/1.90-1.png" /></a></div>
<div style="float: left;"><a href="/images/1.90-2.png"><"alt="Screenshot 2" width="512" height="394" src="/images/1.90-2.png" /></a></div>
<div style="float: left;"><a href="/images/1.90-3.png"><"alt="Screenshot 3" width="512" height="394" src="/images/1.90-3.png" /></a></div>
<div style="float: left;"><a href="/images/1.90-4.png"><"alt="Screenshot 4" width="512" height="394" src="/images/1.90-4.png" /></a></div>
<strong>Synteny</strong>
The first screenshot is zoomed out entirely, so you see the complete TB
genome (~4.5Mb). The following screenshots are gradually zooming in to nucleotide level.

The first screenshot shows whole genome synteny for 14 organisms, the color coding is
according to the position in reference strain.

For example the second colored bar shows a bunch of blue at the beginning, which indicates that in the reference genome this sequence was near the end of the genome.

Only syntenic blocks over 1kb are shown.

<strong>Annotation and conservation</strong>
The second screen shot was obtained by zooming in from the previous one. The top blue and orange blocks are regular annotation features, in this case coding sequences. Below those two tracks, there are the synteny tracks that were also shown in the previous screenshot.

Below the synteny tracks, there a line graphs that indicate the pair wise conservation with the reference sequence.  These graphs are the high-level view of the underlying multiple alignments. 

The bottom track has two line graphs, a blue one and a red one. The red line represents the footprint of the position, i.e. in how many organisms is the nucleotide available. The blue line shows the conservation of each individual nucleotide over all organisms.

<strong>Detailed conservation</strong>
The third screen shot shows as the top graph a detailed view on the gene structure. It still shows two tracks of annotation (blue and orange blocks and has more detailed zoom to multiple alignment.

The detailed gene structure view allows you to see details on the strand a frame of a gene, the presence of start codons (green), stop codons (red) and splice sites (blue-yellow). This is also the panel that can be used to edit the structure of a gene by dragging the edges of a the gene. 

The conservation graphs of the multiple alignment have been replaced with a more detailed view to the multiple alignment. The color coded columns indicate conservation of single nucleotides over the loaded organisms. The scale goes from black to white, from perfect conservation (black) over all species to less than 50% conservation (white). The red blocks indicate gaps in the alignment.

<strong>Sequence logo and nucleotide level</strong>
When zooming in further, as in the fourth screen shot, one can see the individual nucleotides and amino acids in the gene structure and the multiple alignments. The bottom footprint track has been replaced with a sequence logo for the multiple alignment, showing the relative frequency of all nucleotides in a particular position.


#1.8
This releases features a major redesign of the plugin architectures that uses the JPF framework more properly and can account for dependencies between the different plugins. Together with this release we have also released two completely new plugins and we have updated the two plugins that were already available. The two new plugins are for NCBI Blast and for SpliceMachine (a splice site prediction program).

Another big chance is the branching of the JAnnot package. All reusable data handling methods like parsers and data structures for biological sequences now reside in a separate project. 

Weve also done a number of small improvements and bug fixes:
<ul>
<li>You can now query selections at EBI</li>
<li>Upgraded to AJT-1.23 to fix a bug</li>
<li>Improved the help menu</li>
</ul>


# 1.7.7
Version 1.7.7 of GenomeView has been made publicly available. In this released we focused on improving the performance on larger data sets. The goal was to load the entire Arabidopsis thaliana genome with all annotation that is available at TAIR. This is over 120 megabases of sequence and over 530,000 features. To keep the GUI responsive we implemented a number of graceful degradation measures to limit the number of features that should be painted on the screen. Also the number of internal updates has been optimized to improve the speed of the GUI. 

We have also implemented some other new features:
<ul>
<li>Loading multiple files at once from file selection box</li>
<li>Added a parser for Blast -m8 output.</li>
<li>Fixed a bug where selection were not correctly reset when you switched entries</li>
</ul>

# 1.7.6
In release 1.7.6 of GenomeView we have fixed some bugs and added some new features. The two  main features are the more compact GUI resulting in a workable program at lower resolution. Furthermore, we have added dual-screen support. When you have more than one screen attached to your computer, GenomeView will detect this and split the GUI over the two screens. We have added some more configuration options and we have tweaked the GUI in some places.

To fix a bug in the physical property module, we have upgraded to ajt-1.22.

# 1.7.5

In this release we have added support for the GENBANK format, we have fixed some bugs and we have upgraded to AJT version1.21.

<ul>
<li>Support for the genbank file format</li>
<li>Fixed a bug where the parent of features loaded from a GFF files were not set properly</li>
<li>Fixed a bug where loading multiple feature files sometimes crashed the application</li>
<li>Upgraded to AJT-1.21</li>
<li>Fixed bug were the ChromosomeView could not be saved to PNG or JPG</li>
</ul>



# 1.7.4
We have further improved the internals of GenomeView and we have implemented a number of new features in the GUI.
<ul>
<li>CDS panel identifies exons with in-frame stop and missing splice sites graphically</li>
<li>Any keyword in the description of a feature can be queried at Ensembl and NCBI</li>
<li>CDSView now has viewport to show which part is visible in the StructureView</li>
<li>Features are now properly wrapped in the EMBL parser</li>
<li>GenomeView now remembers the last visited directory</li>
<li>Some improvements to the ChromosomeView</li>
<li>Fixed a number of graphical glitches</li>
</ul>


# 1.7.3
GenomeView 1.7.3 fixes a number of bugs to improve to user experience. We also improved to logging mechanism to make it easier to diagnose bugs in the future. 

<ul>
<li>Progress bars are shown for all data sources</li>
<li>Improved the CDS view</li>
<li>Improved logging</li>
<li>Sponsor logo is by default turned off</li>
<li>Show reply of server when saving to URL</li>
<li>About dialog contains information where log and configuration files are stored</li>
</ul>
<!--break-->



# 1.7.2
GenomeView 1.7.2 has been released. 

The main new feature is an extra panel that displays the structure of the last selected CDS. This is useful when editing a gene structure and you want to check what happens with the exons that are outside of your zoom. Besides this new panel we have added additional configuration options including the possibility to configure the colors of the different types of data.

Besides this new feature we have fixed a number of bugs and did a number of improvements that should make the GUI more user friendly.
<ul>
<li>Changing a strand is now properly registered in the undo-redo stack</li>
<li>Display of some undo-redo items is now more human readable</li>
<li>CDS overview list now completely behaves properly</li>
<li>EMBL parser now correctly save description lines</li>
<li>Undo and redo of structural changes will properly update the phase of an exon</li>
<li>A progress box is displayed for all loading and saving events</li>
</ul>
<!--break-->




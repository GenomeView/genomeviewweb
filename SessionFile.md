# Session File

A session file allows you to organize a large number of data files and config options in a single file.


An example session file:

https://raw.githubusercontent.com/GenomeView/genomeviewweb/refs/heads/main/files/mtb_h37rv_v2/session.php


You can use 'View source', or something similar, in your browser to see the actual file structure. It is a plain text file with on each line a file that needs to be loaded.

==File structure ==

===Header===
Make sure the file starts with a line that contains the words 'GenomeView' and 'session'. These two words have to be on the first line!

We recommend:
 ##GenomeView session

This header is used to detect the file format by GenomeView.

=== Body ===

The remainder of the file contains lines that have various instructions to load data, configure GenomeView or load plugins. The table below has an overview of all options.

{|
!Instruction*
!Value
|-
|CONFIG
|URL or local file path to the configuration file. This line should be the first in the session file, otherwise some data may not have the correct configuration file when initializing.
|-
|DATA**	
|URL or local file path for a data file. This file will be loaded. You do not need to specify the index, GenomeView will look for it in the same folder.
|-
|PREFIX	
|URL or local file path prefix. The value of this instructions will be prepended to any DATA, PLUGIN or CONFIG pairs that follow this instruction. A PREFIX values is only valid for subsequent DATA, PLUGIN and CONFIG pairs. This can to simplify loading many files from multiple locations. To reset the PREFIX, you can use an empty value. You can use multiple PREFIX instructions through-out the session, they will each be valid for the following DATA, PLUGIN and CONFIG instructions, until reset with an alternative value.
|-
|OPTION	
|Key=value definition of a single configuration option. This is suited to override a few config options as needed.
|-
|ALIAS	[identifier]=[display name]. 
|Add an additional synonym for an Entry (chromosome). This can be useful if your data has different identifiers for the same sequence in different files. Multiple identifiers names can point to the same display name, in that case the data from all those identifiers will be projected onto a single entry.
|-
|LOCATION
|Set the visible location to the specified location. The location needs to be specified [entry]:[start position]-[end position].
|-
|PLUGIN	
|Allows you to request the user to automatically install a plugin. The plugin needs to be specified as a URL to the zip file. You can use relative names in conjunction with the PREFIX parameter
|}

 ** The legacy keywords C, U and F will continue to work.

Each of the lines should be organized like this:
 instruction[tab, colon or space]value

For example, all of these are valid ways to specify a file
 DATA	http://www.broadinstitute.org/software/genomeview/genomes/mtb_h37rv_v2/MT_H37RV_V2.fasta
 DATA http://www.broadinstitute.org/software/genomeview/genomes/mtb_h37rv_v2/annotation.gff
 DATA:http://www.broadinstitute.org/software/genomeview/genomes/mtb_h37rv_v2/operon.gff

===Example session file===

 ##GenomeView session -- DO NOT DELETE THIS LINE
 CONFIG http://www.broadinstitute.org/software/genomeview/genomes/mtb_h37rv_v2/tbconfig.txt
 ALIAS MT_H37RV_V2=MyTBGenome
 DATA http://www.broadinstitute.org/software/genomeview/genomes/mtb_h37rv_v2/MT_H37RV_V2.fasta
 PREFIX http://www.broadinstitute.org/software/genomeview/genomes/mtb_h37rv_v2/
 DATA annotation.gff
 DATA operon.gff
 DATA sRNA.gff
 DATA rRNA.gff
 PREFIX
 PLUGIN http://www.broadinstitute.org/software/genomeview/resources/save2pdf-1.1.zip

== Starting a session with a launch URL ==

Important: You should use the JNLP file we provide as it will integrate the parameters into the start-up parameters of the webstart application.

The basic set-up to start GenomeView with a [[session file]] is
 <nowiki>http://genomeview.org/start/launch.jnlp?--session <URL to the session file></nowiki>


For example
[http://genomeview.org/start/launch.jnlp?--session%20http://www.broadinstitute.org/software/genomeview/genomes/mtb_h37rv_v2/session.php http://genomeview.org/start/launch.jnlp?--session http://www.broadinstitute.org/software/genomeview/genomes/mtb_h37rv_v2/session.php]

== Hiding the session URL ==
Typically you don't even have to expose this URL and you can use a simple PHP script index.php that redirects to that location.
For example:
 <nowiki>header("Location: http://genomeview.org/start/launch.jnlp?--session http://www.broadinstitute.org/software/genomeview/genomes/mtb_h37rv_v2/session.php");</nowiki>

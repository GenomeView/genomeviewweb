 !<img align="right"src="img/splash.png"/>
 ![GenomeView](img/splash.png#right)
 
# GenomeView

This is the documentation page for [GenomeView](https://github.com/GenomeView/genomeview).

[GenomeView](https://github.com/GenomeView/genomeview) is a stand-alone genome browser and editor initiated in the BEG group at [VIB](https://vib.be/en), then further developed at [Broad Institute](https://www.broadinstitute.org/) and currently maintained at [TU Delft](https://reit.tudelft.nl/). It provides interactive visualization of sequences, annotation, multiple alignments, syntenic mappings, short read alignments and more. Many standard file formats are supported.

## System requirements

Recommended system specs:

* 2 Gb of memory, minimum is 1 Gb
* dual-core or better processor, but GenomeView will work with less.
* To browse online data, it's recommended to have a high-speed, low-latency connection
* Recent version of Windows, *nix or Mac OS
* Recent version of Java 17+. 

    

## Installation

It is assumed that you already have java 17 or higher installed. To install GenomeView, 

* Install java 18 or higher if it's not yet installed. 
    * You can check by running 'java -version' in the commandline.  
    * You can get an installer from http://www.java.com or https://openjdk.org/. 
    * On linux you can `sudo apt install openjdk-17`
    * If you only want to run java you can install the `JRE`, for compilation you should install the `JDK`.
* Go to https://artifactory.ewi.tudelft.nl/ui/native/libs-release/net/sf/genomeview
* Click the version you need, probably the highest version number available.
* download the jar-with-dependencies.jar file.

## Start GenomeView
* Start the app, using one of the following
    * on the commandline with ```java -Xmx4g -jar genomeview.jar```. You can change the '4g' into a bigger number
    if you need more memory in GenomeView.
    * double click on the jar file to start the app. This will run with the default memory.

> [!TIP]
> 'double click to start' may require you to set the jar file to 'executable' and/or 
> setting the default application for 'jar' files. 
> On Linux for example, right click on the jar, "Open with other Application", 
> select "use a custom command" and enter ```java -jar``` in the text box. Then click open.

## Log files
GenomeView log files are in the folder .genomeview (dot genomeview) in your home folder of your local computer.

* On MS Windows versions this is `C:/Users/[username]/.genomeview`
* On Mac and Linux this is `~/.genomeview`

If you can still start GenomeView, you can find the exact location under the 'Help menu' > 'About'

## Manuals

We have several manuals for you

* [Quick Start Guide](StartGuide.md)

* [The User Manual](UserManual.md)

* [The Platform User Manual](PlatformUserManual.md)

* [The Developer Manual](DeveloperManual.md)

## Source code

The source code is available on [http://github.com/genomeview/genomeview](github). .


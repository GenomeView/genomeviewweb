# GenomeView User Manual

Welcome to the GenomeView User manual. These pages aim to explain the GenomeView user interface in depth.

## Introduction
To gain insignt into genomes, they are analysed
by various methods, and the analysis result files need to be visualized
to get more insights.

GenomeViewer unifies the visualization step,
by integrating various analysis result files into a unified visualization,
and by providing means to add annotations.

GenomeViewer can handle many of the existing analysis analysis formats,
and provides standard visualization tools for each of them.

Usually analysis is done with external tools. We provide
recommendations, links and instructions on how to use these tools.


## The User Interface

Below image shows the main user interface.

![Overview of the GenomeView GUI](/img/dualframe.png)

<b>Major components of the user interface and their names</b>

* On the top there are the various [menus](Menu.md).
* Below that is a [toolbar](Toolbar.md) with a.o. the currently selected chromosome
* The main area on the left, bordered red in the image, are the [visualization tracks](Tracks.md)
* On the right you see various information: 
    * [track management](Tracks.md#Track-List) 
    * a [feature list](FeatureTrack.md#Feature-List) 
    * details of the selected features. Clicking on one of the icons launches a query at that search engine.
    * a gene frame structure/CDS details If the selected feature is a coding sequence, this panel will show the features reading frame structure
    

When running two separate instances of GenomeView, eg on a dual screen setup, the information panel will automatically be detached and put on the second screen.

![GenomeView screenshot](/img/full_window2.png)



# Configuration
You can configure the behaviour using the [Configuration panel](Configure.md).

# Interaction
You interact with the views using 
* [the menus](Menu.md)
* [keyboard shortcuts](KeyboardShortcuts.md)
* [mouse shortcuts](MouseShortcuts.md)


# FAQ
Please check the [FAQ wiki](FAQ.md).

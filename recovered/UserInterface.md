# User Interface

This page introduces the different components of GenomeView and explains a number of naming conventions we use throughout the documentation.

## Components of GenomeView
The GenomeView GUI is divided into two columns. The left side is a graphical representation of the data, while on the right side you can find additional information, controllers and options in the form of tables.

When running GenomeView on a dual screen setup, the information panel will automatically be detached and put on the second screen.

![GenomeView screenshot](/img/full_window2.png)


## Left column: graphical representation
The navigator at the top of the screen can be used to quickly navigate over the sequence.

![GenomeView navigator](/img/navigator.png)

Dragging the navigator (the blue box with circular extensions) allows you to move left-right over the sequence. Dragging the left or right edge of the box will enlarge the view in that particular direction. The number indicates the size of the currently visible region.

Below the navigation panel, all tracks are displayed. A track is any set of information that belongs together. A track can contain a number of types of information. See the page about tracks for more details.

![GenomeView right panel](/img/structure_track.png)

## Right column: information and controllers

<img style="width:35%" src="/img/side_panel.png" alt="GenomeView right panel" />

There are four panels in the information panel.

#### Track list

Shows a list of all currently loaded tracks. Toggling the visibility of a track is done by clicking the eye icon. By dragging the entries up or down, you can rearrange the order of the corresponding tracks in the view window.

#### Features

Shows a list of all features of a particular type. See the description of the feature track for more details.

#### Details on selected item

This panel is used to display additional information when you select something. Clicking on one of the icons launches a query at that search engine.

#### CDS details

If the selected feature is a coding sequence, this panel will show the features reading frame structure







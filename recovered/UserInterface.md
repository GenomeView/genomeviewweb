# User Interface

This page will introduce the different components of GenomeView and will explain a number of naming conventions we use throughout the documentation.



### Components of GenomeView

The layout of GenomeView is in two columns. The left side is a graphical representation of the data, while on the right side you can find additional information, controllers and options in the form of tables.

<img style=\"width:100%\" src=\"/sites/default/files/screen3.PNG\" alt=\"GenomeView screenshot\" />

### Left column - graphical representation
<br/>The top part of the screen can be used to quickly navigate over the sequence.

<img style=\"width:100%\" src=\"/sites/default/files/navigator.PNG\" alt=\"GenomeView navigator\" />

Draggin the blue box (or the circular extensions) allows you to move left-right over the sequence. Dragging the left or right edge of the box will enlarge the view in that particular direction. The number indicates the size of the currently visible region.<br/><br/>Below the navigation panel, all tracks are displayed. A track is any set of information that belongs together. A track can contain a number of types of information. See the page about tracks for more details.

<img style=\"width:100%\" src=\"/sites/default/files/tracks.PNG\" alt=\"GenomeView right panel\" />


### Right column - information and controllers

<img style=\"width:25%\" src=\"/sites/default/files/rightpanel.PNG\" alt=\"GenomeView right panel\" />

There are five panels in the right column

##### Data sources
Shows a list of all data sources that are currently loaded. For some track types it is possible to hide the data from a particular source from this table by clicking the green mark

##### Track list
Provides a list of all tracks that are currently available. When loading new data, new tracks will automatically be added to accommodate the new data. This panel can also be used to manipulate the different tracks. The first column controls whether the data from this particular track is also displayed on the structure track. See the description of the tracks for more information. The second column controls whether the track will be displayed and the third column controls whether the track will be drawn fully, or in a collapsed state. The fourth and fifth column can be used to change the order of tracks.

##### Features
Shows a list of all features of a particular type. See the description of the feature track for more details.

##### Details on selected item
This panel is used to display additional information when you select something

##### CDS details
If the selected feature is a coding sequence, this panel will show the features reading frame structure

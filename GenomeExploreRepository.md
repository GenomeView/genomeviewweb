# Setting up a Genome Explorer repository

GenomeView allows you to set up a custom repository of genomes that will be loaded as primary view in the [[Genome Explorer]]

## Recipe

* Set up a repository file
* Set up configuration file 
* Make launch URL 


## Repository file format
The repository file is a tab-delimited file where each column has a special meaning. These should be one row per session, i.e. per data set.

* repository identifier
* display name for session, should be reasonably short and informative people
* display image for session, this should be a URL
* description text for individual session, this can be html code.
* url to the session file.

An example row could be:
| | | | | |
|--|--|--|--|--|
|fusobac|Fusobacterium nucleatum animalis|http://genomeview.org/manual/images/6/69/Gv_logo-96px.png|Fusobacterium nucleatum animalis is from a colon sample.  This strain was sequenced at Baylor College of Medicine. |http://myuniversity.org/fusobacterium/Fuso_animalis.session|


## Setting up the configuration file
In order to work with the new repository file, you need to create a config file that specifies where GenomeView has to look for it.

The key options you need to set are:
```
 # Make sure the Genome Explorer is enabled
 general:enableGenomeExplorer=true
 # Point GenomeView to your repository
 external:repository=<URL>
 # Provide display names for the repository identifier you used in the first column
 external:repository:labels=<repository identifier>:<repository display name>
```
For each repository identifier you also need to fill out the description field:
 external:repository:description:<repository identifier>=<long HTML formatted description>

For example:
```
 <nowiki>external:repository=http://myuniversity.org/my/repository/file.txt</nowiki>
 external:repository:labels=fusobac:Fusobacterium Repository
 external:repository:description:fusobac=Welcome to the Fusobacterium GenomeView portal. Blah blah blah...
```

## Setting up launch URL

The final step is to start GenomeView with this configuration file. Suppose you make the config file available at http://myuniversity.org/my/repository/config.txt, then the launch command would be:
```
java -jar genomeview.jar --config http://myuniversity.org/my/repository/config.txt
```

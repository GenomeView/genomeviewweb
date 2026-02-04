# Programming with GenomeView

GenomeView is completely open-source and this allows you to write program that manipulate GenomeView or re-use parts of GenomeView, in particular the visualization component.

One important thing to remember is that GenomeView is completely multi-threaded and virtually none of the methods is blocking. Unfortunately, this also often means that returned data can be incomplete and developers should implement proper checks or use other tricks to make sure output is sufficiently complete.

## Scripting GenomeView
In this section we explore how to manipulate GenomeView from within your program. In our example well load some data sets, move to each each gene and take a snapshot.

<!-- can't find this back ... -->
<a href=\"http://genomeview.svn.sourceforge.net/viewvc/genomeview/genomeview/test/org/genomeview/test/PictureMaker.java\">The documented source code is available from the code repository</a>.

<h2>Embedding the GenomeView visualization component in other software </h2>

<a href=\"https://github.com/GenomeView/genomeview/blob/master/src/main/java/net/sf/genomeview/ascomponent/GenomeViewAsComponent.java\">Documented source code is available from the code repository</a>.









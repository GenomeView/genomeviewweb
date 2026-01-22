# Command Line Options

After you [installed GenomeView](Readme.md#installation), you have the executable jar file on your machine. 
Add this jar file to the java CLASSPATH if you want GenomeView to be accessible from anywhere on your system. Alternatively you can always start from this directory or you can qualify the full path to the jar-file each time you start GenomeView.

You can start GenomeView by issuing the following command at the prompt
```
 java -jar genomeview.jar
```

## Loading files on start-up
You can instruct GenomeView to load files when it starts. All file names and URLs that are specified will be loaded. There are a few options you can use. Files are loaded concurrently, unless the --file or --url switch is used.



Some examples:
```
 java -jar genomeview-669.jar --file seq.fasta
```
This command will start GenomeView with seq.fasta loaded.
```
 java -Xmx10g -jar genomeview.jar --position 2000:3500 --file seq.fasta feat.embl pred.embl add.embl
```
Will start GenomeView with 10g of main memory available and all the specified files loaded, but seq.fasta will be loaded first and zoomed to the region 2000-3500.





## Available options
Options for use on the command line or with website integration.
| `--file <file>`|Load this file first, all other files will be loaded concurrently after this files has finished| 
| `--url <url>`| Load the data from this url first. After this has finished, all other files will be loaded concurrently| 
| `--session <file or url>`|Load the session from this URL or file. This parameter will override all others.| 
| `--config <file or url>`|Load extra configuration options from this file or URL. This configuration will override default and user configuration. See 
[Configuration](Configuration.md) for more details.| 
| `--position <position>`|Zoom to the supplied position on start-up. You need to use this in conjunction with the `--url` or `--file option`. First that file or url will be loaded and then GenomeView will zoom to the supplied position. The position is in the format `<entry>:<start position>:<end position>` The entry part can be omitted in which case it becomes `<start position>:<end position>`| 
| remaining arguments| Load all remaining files and URLs specified on the command line|

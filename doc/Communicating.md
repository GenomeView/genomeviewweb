It is '''important''' that you set <code>integration:monitorJavaScript=true</code> in your configuration file. Only if you add that line to the configuration file you specify, will communication work.

## Controlling GenomeView using JavaScript (recommended)
Include the GenomeView javascript file into your HTML page
```
<script type="text/javascript" src="http://genomeview.org/start/genomeview.js"></script>
```

By default the instructions will only work with the GenomeView instance that was launched from the same page with launchGV() instruction. To override this behavior you can set the instanceID to 'ALL' or alternatively you can call `setInstructAllInstancesGV()`

```
 <script>instanceID='ALL'</script>
```

| First Header  | Second Header |
| ------------- | ------------- |
| launchGV(command line) | Launch GenomeView with the specified command line options. |
| Content Cell  | Content Cell  |

| Instruction ! Description |
| ----- | ----- |
| launchGV(command line) | Launch GenomeView with the specified command line options. |
| loadGV(url) | Load the data at the specified url |

|unloadGV()| Unload all data that is currently loaded| 
|sessionGV(url)|Load the GenomeView session at the specified URL| 
|positionGV(position)|Move the visible region to the specified location. The position is in the format <code>[entry]:[start position]:[end position]</code> The entry part is optional can be omitted in which case it becomes <code>[start position]:[end position]</code>|
|trackGV(trackname)|Scroll vertically to make sure the named track is visible.| 
|configGV(key=value)|Set a single configuration option.| 
|isAlive(callback)|Check whether a GenomeView instance is alive. <code>callback</code> should be a javascript function that you define that will be called by the script and will have a variable <code>isAlive</code> available that you can use. This could be used to check whether there is already a GenomeView instance launched and based on that information start an instance or load the data into the existing one.| 
|setInstanceID(id)|Set the GenomeView instance ID to be used in the next functions calls to the supplied argument. This is useful to communicate with multiple GenomeView instances at once. See the <a href="http://genomeview.org/jsdemo/testlaunch.html">example</a> for more details.| 
|setInstructAllInstancesGV|Any commands after this function call will be send to all GenomeView instances|

## Examples

### launchGV(command line)





## Controlling GenomeView using a port
The java script is implemented as a local server that listens on port 2223, so you could alternatively directly control GenomeView by sending instructions to that port.

The format of an instruction is 
```
GET /genomeview-ALL/[instruction]/[argument]
```

### Some examples:

* Load the C. elegans demo instance

```GET /genomeview-ALL/session/http://www.broadinstitute.org/software/genomeview/demo/c_elegans/session.php```

* Position the current visible window to 10000-20000

```GET /genomeview-ALL/position/10000:20000```

* Unload all data:

```GET /genomeview-ALL/unload```

* Full working example code in Java

```
Socket gv = new Socket("localhost", 2223);
		PrintWriter pw=new PrintWriter(gv.getOutputStream());
               /*pw.println("GET /genomeview-ALL/session/http://www.broadinstitute.org/software/genomeview/demo/c_elegans/session.php");*/
                //pw.println("GET /genomeview-ALL/unload");
		pw.println("GET /genomeview-ALL/position/10000:20000");
		pw.flush();
		gv.close();
```

### Available instructions:

<table>
<th>Instruction</th><th>Description</th>
<tr><td>GET /genomeview-ALL/load/[URL]</td><td>Load the data at the specified url</td></tr>
<tr><td>GET /genomeview-ALL/unload (no argument)</td><td>Unload all data that is currently loaded</td></tr>
<tr><td>GET /genomeview-ALL/session/[URL]</td><td>Load the GenomeView session at the specified URL</td></tr>
<tr><td>GET /genomeview-ALL/position/[position]</td><td>Move the visible region to the specified location. The position is in the format <code>[entry]:[start position]:[end position]</code> The entry part is optional can be omitted in which case it becomes <code>[start position]:[end position]</code> </td></tr>
</table>

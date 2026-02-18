# Tutorial: MAF

This tutorial will guide you through the required steps to download a 
whole genome multiple alignment from the UCSC genome browser 
and explore it in GenomeView.

1. [Start GenomeView](/README.md#Start-GenomeView)
1. [Load](LoadData.md) D. melanogaster genome from the [Demo Datasets](DemoData.md)
1. Load multiple alignment from UCSC by following the instructions in the next section.

### Load multiple alignment from UCSC
The URL for all multiple alignments for D. melanogaster is:

http://hgdownload.cse.ucsc.edu/goldenPath/dm3/multiz15way/

Copy the URL of one of the MAF files you find there, for example right click on `chr2R.maf.gz`
which allows you to copy the URL to that file.

The full URL to that file is http://hgdownload.cse.ucsc.edu/goldenPath/dm3/multiz15way/chr2R.maf.gz

Make sure you copy this URL somewhere so you dont have to type it in a second.

Next tell GenomeView to load more data using the menu `File / Load data...`. 

![Load data](/img/loaddata.png)

Select URL from the options. 
You now see a text field where you will paste the URL above.

![Give the URL](/img/maftutorial2.PNG)


After you paste the URL, press `OK`

GenomeView will prompt you now whether you want to pre-process this file. You want to do that, so press yes.

![Confirm you want to preprocess the MAF file](/img/maftutorial3.PNG)

GenomeView will now ask where the preprocessed files should be stored. Pick a location anywhere on your computer. If you want to load this multiple alignment in the future, you can directly those files from your local computer and you dont have to go through the steps here.

Once thats done, GenomeView will start processing the files, which can take a couple of minutes. This is a one-time process.

At the end GenomeView will load up the freshly produced multiple alignment.


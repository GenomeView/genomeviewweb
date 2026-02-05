# Bam2tdf

BAM2TDF is a command-line tool that converts BAM files to TDF (coverage) files.

You can download the latest version from the GenomeView nightly builds:

http://genomeview.org/jenkins/bam2tdf-nightly/

Instructions:
```
java -jar bam2tdf.jar [-m <minimumMappingQuality>] <location of your bam file>
```

bam2tdf calculates fragment coverage, not physical coverage

Requirements:

- Java 7+
- BAM file needs to be sorted and indexed

# ReduceVcf

reducevcf is a tool to reduce the size of VCF files.

It will remove all lines where the alternative allele matches the reference allele. In most cases this will reduce the VCF to less than 1% of its original size.

## Download

The latest version of reduce VCF is available for [download](http://www.genomeview.org/jenkins/reducevcf-nightly/) from the GenomeView server.

## Usage

```
 Usage: java -jar reducevcf.jar [options]

 -i <file> | --input <file>
 Input file
 -o <file> | --output <file>
 Output file
 -k | --keep
 Keep ambiguous calls
```

 Example: `java -jar reducevcf.jar -i myLargeVCFFile.vcf -o smallOutputFile.vcf`


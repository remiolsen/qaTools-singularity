# qaTools-singularity
Singularity bootstrap script for [qaTools](https://github.com/vezzi/qaTools)

# Usage
```bash
$ singularity run container.img
Version: 1.5
Contact: Paul Costea <paul.igor.costea@scilifelab.se>

Usage:   qaCompute [options] <in.bam/sam> <output.out>
Options: 
         -m            Also compute median coverage
         -q            Quality threshold. (min quality to consider) [1].
         -d            Print per-chromosome histogram [<output.out>.detail]
         -p [INT]      Print coverage profile at INT window size to bed file [<output.out>.profile] [50000]
         -i            Silent.Don't print too much stuff!
         -s [INT]      Compute 'span coverage' rather than base coverage, limiting insert size to INT. -1 -> consider all!
         -c [INT]      Maximum coverage to consider in histogram [30]
         -h [STR]      Use header from specified file. .sam OR .bam (Header must match the info in your input file. Otherwise, output is meaningless!)

Note: Input file should be sorted
```
Or:
```bash
$ singularity exec container.img qaCompute
$ singularity exec container.img removeUnmapped
$ singularity exec container.img computeInsertSizeHistogram
$ singularity exec container.img doBWAQualTrimming
```

# mock MLST site

This is a mockup of an MLST site for EToKi.

# Files

In the db folder, each scheme has two files.

* `refs.fasta` - reference alleles for each locus
* `etoki.*.csv` 
   * comma separated values: md5sum of the sequence, locus name, allele number
   * Each database has been initialized into chunks of files of at most 500k lines to avoid having huge files
   * These need to be concatenated later at time of use


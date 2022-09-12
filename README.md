# mock MLST site

This is a mockup of an MLST site for EToKi.

# Files

In the db folder, each scheme has two files.

* `refs.fasta` - reference alleles for each locus
* `etoki.*.csv` 
   * comma separated values: md5sum of the sequence, locus name, allele number
   * Each database has been initialized into chunks of files of at most 500k lines to avoid having huge files
   * These need to be concatenated later at time of use

# Initial results and thoughts

* tar.gz file is still huge at 161M.  Might want to make one repo per schema.
* automatic tar.gz files on github would be made with versions/tags
* Might want to exclude allele numbers to help with automated merging. Therefore, some other process would have to have to assign alleles. Alternatively, EToKi would have to be modified to read a database with no allele numbers and with only the hash and locus. Or else, it would have to be a manual process.
* Would need to make good instructions to others on how to accept pull request so that this can be democratized.
* Would need some kind of unit testing for basic sanity checks especially on pull requests.

# Proposed usage

## installing

User would:

1. download the repo
2. concatenate the `csv` files 
3. run `EToKi MLSType` against the database

## contributing

1. clone repo
2. add
   * (alleles) add lines to csv file
   * (loci) add new entry to fasta file. Add new alleles to csv file.
3. pull request
4. (github actions) automated sanity check
5. curator, i.e., MLST stakeholder, accepts pull request or requests revisions from submitter

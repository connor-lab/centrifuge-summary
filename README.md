# centrifuge-summary
Summarise a [Centrifuge](https://ccb.jhu.edu/software/centrifuge/manual.shtml) report for a specific taxon and its sub-taxa

### Dependencies
[taxonkit](https://github.com/shenwei356/taxonkit)

### Usage
`centrifuge-summary --taxon-name "Escherichia coli" --report-file example.centrifuge.report.tab`

also works for other taxonomic levels:

`centrifuge-summary --taxon-name "Enterobacteriaceae" --report-file example.centrifuge.report.tab`

and NCBI taxon IDs:

`centrifuge-summary --taxon-id 561 --report-file example.centrifuge.report.tab`

Report uniquely matching reads (default if neither `-u` or `-a` are supplied):

`centrifuge-summary -u --taxon-id 561 --report-file example.centrifuge.report.tab`

or reads that match at least the target taxon:

`centrifuge-summary -a --taxon-id 561 --report-file example.centrifuge.report.tab`



### Help
usage: centrifuge-summary [-h] (-t TAXONNAME | -i TAXID) [-u | -a] -r
                          REPORTFILE

optional arguments:
  -h, --help            show this help message and exit
  -t TAXONNAME, --taxon-name TAXONNAME
                        Scientific name of the taxon to count reads beneath
                        [e.g. Escherichia]
  -i TAXID, --taxon-id TAXID
                        NCBI taxID to count reads beneath [e.g. 561]
  -u, --unique          Summarize only reads UNIQUELY matching taxon
                        [numUniqueReads column] [DEFAULT]
  -a, --all             Summarize reads matching taxon [numReads column]
  -r REPORTFILE, --report-file REPORTFILE
                        Path to the centrifuge report-file to summarise

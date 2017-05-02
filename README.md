# metablastr
### Perform Local BLAST Searches and Data Analysis on a Metagenomic Scale

The Basic Local Alignment Search Tool (BLAST) finds regions of sequence similarity between a query and a subject sequence or sequence database.

The `metablastr` package provides interface functions between R and the standalone (command line tool) version
of BLAST. The search report generated by BLAST can then be imported into the R session
either as `data.frame/tibble` or as `PostgresSQL` database connection and can be analysed, filtered, or processed with common [R data science](http://r4ds.had.co.nz/) tools such as [dplyr](https://github.com/tidyverse/dplyr), [ggplot2](https://github.com/tidyverse/ggplot2), etc.

The `metablastr::read_blast()` function has a [PostgresSQL database](https://www.postgresql.org/download/) backend, which allows users to generate and store very large BLAST reports
and still process them in R via the [dplyr](https://github.com/tidyverse/dplyr) database interface.

Hence, using `metablastr::read_blast()` in database mode users can use the familiar `dplyr` notation
to analyze large scale BLAST reports. Additional functions such as `blast_nr()`, `blast_pdb_aa()`, `blast_refseq_protein()`, etc.
are designed to perform easy-to-run BLAST searches on a metagenomic scale. The corresponding output can then
be analyzed using specialized `filter_blast_*` functions.

### Install `metablastr`

```r
# install.packages("devtools")

# install the current version of blastr on your system
library(devtools)
install_github("HajkD/metablastr", build_vignettes = TRUE, dependencies = TRUE)
```


## Interfaces implemented in `metablastr`:

### Perform BLAST searches 

- `blast_protein_to_protein()`: Perform Protein to Protein BLAST Searches (BLASTP)
- `blast_nucleotide_to_nucleotide()`: Perform Nucleotide to Nucleotide BLAST Searches (BLASTN)
- `blast_nucleotide_to_protein()`: Perform Nucleotide to Protein BLAST Searches (BLASTX)
- `read_blast()`: 

### BLAST against common NCBI databases 

- `blast_nr()`:
- `blast_nt()`:
- `blast_est()`:
- `blast_pdb_aa()`:
- `blast_pdb_nt()`:
- `blast_swissprot()`:
- `blast_delta()`:
- `blast_refseq_rna()`:
- `blast_refseq_gene()`:
- `blast_refseq_protein()`:

### Analyze BLAST Report

- `filter_blast_`:

### Navigation functions
- `list_outformats()`: List available BLAST output formats

## Discussions and Bug Reports

I would be very happy to learn more about potential improvements of the concepts and functions provided in this package.

Furthermore, in case you find some bugs, need additional (more flexible) functionality of parts of this package, or want to contribute to this project please let me know:

https://github.com/HajkD/metablastr/issues

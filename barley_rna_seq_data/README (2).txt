RNA-seq Abundance Files

This directory contains RNA-seq gene expression abundance matrices used for downstream analysis of barley transcriptome datasets.

Files

The dataset is stored in four compressed files:

my_barley_input.2.part1.abundance.tsv.gz

my_barley_input.2.part2.abundance.tsv.gz

my_barley_input.2.part3.abundance.tsv.gz

my_barley_input.2.part4.abundance.tsv.gz

The full RNA-seq abundance matrix was split into four parts because of its large size.
Each file contains a subset of genes, but the same set of RNA-seq samples.

File format

Each file is a tab-separated table (.tsv) with the following structure:

Rows: barley gene identifiers (Hordeum vulgare)

Columns: RNA-seq samples

Values: gene expression abundance values derived from RNA-seq quantification

The files are gzip-compressed (.gz) to reduce storage size.


Reading the files

The files can be read directly in R without decompression:
abundance <- read.table("my_barley_input.2.part1.abundance.tsv.gz",
                        header = TRUE,
                        sep = "\t",
                        check.names = FALSE)


Reconstructing the full expression matrix

To obtain the complete abundance matrix, the four parts can be combined by concatenating them along the gene (row) dimension.


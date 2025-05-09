# Genotyping

## Description
<p id="Description">
  Performs statistical analysis on a database of patient SNPs (Single Nucleotide Polymorphism). This program compares between two groups (patient vs. control, or disease 1 vs. disease 2), performing Pearson's χ² test on a 3x2 or 2x2 contingency table of genotypes. In the case of 3x2 tables (when all three possible genotypes are present), it also calculates χ² and odds ratio for dominance (adding the heterozygote counts to either homozygote sequentially) and alleles (counting the number of alleles rather than genotypes).
</p>

## Dependencies
<p id="Dependencies">
  Language: Python 3<br>
  Modules: <a href=https://pypi.org/project/openpyxl/>openpyxl</a>, <a href=https://pypi.org/project/pandas/>pandas</a>, <a href=https://pypi.org/project/numpy/>numpy</a>, <a href=https://pypi.org/project/scipy/>scipy</a>, and <a href=https://pypi.org/project/statsmodels/>statsmodels</a> (logging, sys, and os as well, but those are part of the standard library).<br>
  File: datsets.exe installed in the same folder as the python file. Download from the NCBI <a href="https://www.ncbi.nlm.nih.gov/datasets/docs/v2/command-line-tools/download-and-install/">command-line tools page</a>. The one included here is Windows 64-bit, up-to-date as of 01/05/2025.
</p>

## Usage
<p id="Usage">
  This program takes a list of gene names (found in "./input", basically a newline-separated list of gene names) in <a href="https://software.broadinstitute.org/cancer/software/gsea/wiki/index.php/Data_formats#GRP:_Gene_set_file_format_.28.2A.grp.29">grp format</a> and an optional <a href="https://www.ncbi.nlm.nih.gov/datasets/docs/v2/api/api-keys/">NCBI API key</a> (also in "./input", which you can generate in your NCBI account settings), and returns a tab-separated list of gene summaries (written to "./output", in the format "Gene\tSummary\n").<br>
  WARNING: I've only tested this program in Windows, so the command line arguments might not work in other operating systems.
</p>

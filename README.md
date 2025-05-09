# Genotyping

## Description
<p id="Description">
  Performs statistical analysis on a database of patient SNPs (<a href="https://en.wikipedia.org/wiki/Single-nucleotide_polymorphism">Single Nucleotide Polymorphism</a>). This program compares between two groups (patient vs. control, or disease 1 vs. disease 2), performing Pearson's χ² test on a 3x2 or 2x2 contingency table of genotypes. In the case of 3x2 tables (when all three possible genotypes are present), it also calculates χ² and odds ratio for dominance (adding the heterozygote counts to either homozygote sequentially) and alleles (counting the number of alleles rather than genotypes).
</p>

## Dependencies
<p id="Dependencies">
  Language: Python 3<br>
  Modules: <a href=https://pypi.org/project/openpyxl/>openpyxl</a>, <a href=https://pypi.org/project/pandas/>pandas</a>, <a href=https://pypi.org/project/numpy/>numpy</a>, <a href=https://pypi.org/project/scipy/>scipy</a>, and <a href=https://pypi.org/project/statsmodels/>statsmodels</a> (logging, sys, and os as well, but those are part of the standard library).<br>
</p>

## Usage
<p id="Usage">
  This program reads a database of genotyping data (from the first sheet of an excel file found in "./input"). Each column of the database needs to be a different SNP, except for the last one which defines the groups. Each row will be a different patient. An example of a database in this format is seen in the following table:
   <table>
     <tr>
       <th><b>SNP 1</b></th>
       <th><b>SNP 2</b></th>
       <th><b>Group</b></th>
     </tr>
     <tr>
       <th>A/A</th>
       <th>G/G</th>
       <th>Condition 1</th>
     </tr>
     <tr>
       <th>A/C</th>
       <th>G/T</th>
       <th>Condition 1</th>
     </tr>
     <tr>
       <th>C/C</th>
       <th>T/T</th>
       <th>Condition 2</th>
     </tr>
   </tr></table>
  There should be, at most, three unique values for each SNP (i.e. all combinations of a single SNP) and two unique values for groups (i.e. two conditions to compare between). 
  This program takes a list of gene names (found in "./input", basically a newline-separated list of gene names) in <a href="https://software.broadinstitute.org/cancer/software/gsea/wiki/index.php/Data_formats#GRP:_Gene_set_file_format_.28.2A.grp.29">grp format</a> and an optional <a href="https://www.ncbi.nlm.nih.gov/datasets/docs/v2/api/api-keys/">NCBI API key</a> (also in "./input", which you can generate in your NCBI account settings), and returns a tab-separated list of gene summaries (written to "./output", in the format "Gene\tSummary\n").<br>
  WARNING: I've only tested this program in Windows, so the command line arguments might not work in other operating systems.
</p>

# First-step project script
The idea was to find if drug prescribed for given traits are associated with the trait.
For this, the goal was to find common genes between the DrugBank dataset (https://www.drugbank.ca/) and Mendelian randomization (MR) results and attribute a score for each drug.
MR results consist of associations between causal genes and a trait (with the p-value of the association)
The drugbank dataset consists of a list of drugs with their gene targets.
The scores for each drug were calculated as follows:

<a href="https://www.codecogs.com/eqnedit.php?latex=R={\frac{1}{t}}\times{\sum-log10(P)^T*Q}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?R={\frac{1}{t}}\times{\sum-log10(P)^T*Q}" title="R={\frac{1}{t}}\times{\sum-log10(P)^T*Q}" /></a>

Where: 

  -t is the number of genes for each drug (column sum) 
  
  -P is the matrix containing the p-values for each gene-trait association
  
  -Q is a matrix with 0 and 1 (0= the drug does not target the gene, 1= the drug targets the gene)

## DrugB.rmd

Script for parsing .xml DrugBank database file. Outputs a dataframe containing drug names,target genes,description...

## MR code.rmd

Script for building a dataframe from MR files. The script outputs a dataframe containing gene names, p-values, and traits.

## Script.html report:

The script consists of 4 main steps:
1) Filtering missing values from datasets
2) Calculating association scores for each drug
3) Visualizing data
4) Compare association scores between drugs targeting causal-genes (for the trait) and drugs that do not.

Each step of the script is annotated in this report. 
If you cannot preview it from github, use http://htmlpreview.github.io/ to do so.

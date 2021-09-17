[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5079556.svg)](https://doi.org/10.5281/zenodo.5079556)

# Peakdetection

**Peakdetection** will automatically detect peaks in a GWAS (BayesFactor or p-values) based on the quantiles of the profile.  

## Installation

peak.Rmd is ready to be used, and will automatically install the packages needed. 

## Usage

The user can modify parameters in the first chunk of peak.Rmd:
- output.path: path for the outputs.  
- gwas: input files containing the columns "Scaffold", "LG" (for linkage group; can be the chromosome ID), "ID" (ID of the SNPs), and results from GWAS. Each line is a SNP. 
- list.sign (optional): list of significant SNPs obtained with another software (as a check up). If not to be specified, leave it NULL. 
- vars: the number(s) of the column of in "gwas" containing the profile to be analysed. 
- slw.size: size of the sliding window. 
- smooth.intens: parameter of smoothing.
- type: type of the profiles (BF, Z-score, of p-value). 
- proba: quantile threshold for peak detection. 
- iter: number of iteration for defining whether a peak can be obtained randomly. 
- extens: output file extension.  

## Outputs

The outputs are being saved in the stat/ and plot/. The main output is stat/peak.\*.txt, containing the following column:
- Best: value of the peak.
- Pos: position of the peak (mode).
- Start: start position of the peak. 
- End: ending position of the peak. 
- Wide: wideness of the peak. 
- SNPs: the number of SNPs within the peak that is in the 95% most significant SNPs overall. 
- Genes: the number of genes across which the peak spans. 
- Sign: the number significant SNPs (from list.sign) contained in the peak. 

In the QQ plot, red circle indicates the expected median, and the red cross indicates the observed median. If both are in the same place, population structure has been correctly taken into account. The red line is with significant SNPs, and the dotted line without significant SNPs. 

## How to cite

Tiret M., Milesi P., 2021. Statistical peak detection for GWAS, DOI: 10.5281/zenodo.5079556.



[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
![R](https://img.shields.io/badge/R-%3E4.2-brightgreen)

# FragPipe-Analyst

A tool for analyzing quantitative proteomics datasets for [FragPipe](https://fragpipe.nesvilab.org/).


## Motivation

- Automate downstream statistical analysis of quantitative proteomics result generated by [FragPipe]((https://fragpipe.nesvilab.org/))

## Features

- Differential expression analysis
  - Result table and interactive volcano plot
- Heatmap for protein markers
- Protein intensity plots for a single or group of selected proteins
- Imputation
  - A number of missing value imputation options available including mean, knn, MLE etc.
- FDR correction
  -   Benjamin Hochberg (BH) method
  -   t-statistics correction: Implemented in
    [fdrtool](http://strimmerlab.org/software/fdrtool/)
- A variety of QC Plots
  1. PCA plot (Could move to QC section)
  2. Sample Correlation (pearson correlation)
  3. Sample Coefficient of variations (CVs)
  4. Number of proteins per sample
  5. Sample coverage (overlap of identified proteins across every sample)
  6. Missing value heatmap
  7. Imputation effect on sample distribution

- Report and multiple levels of exportable tables for further analysis
  - Table options
    - DE results
    - Unimputed data matrix: Original protein intensities before imputation
    - Imputed data matrix: Protein intensities after performing selected imputation method

## Installation

### Prerequisite
- R 4.2
- PDFlatex
  
### Multiple options
Once all the dependencies are installed, follow steps below to run the server locally.
You can build it natively:

``` sh
# Clone the repository
git clone https://github.com/MonashProteomics/FragPipe-Analys.git

# Move to the folder
cd FragPipe-Analyst

# Inside R console or R studio
> library("shiny")
> runApp()
```

Or run it through Docker:

``` sh
# Clone the repository
git clone https://github.com/MonashProteomics/FragPipe-Analys.git

# Move to the folder
cd FragPipe-Analyst

# Build FragPipe-Analyst (Any name after -t)
docker build -f Dockerfile -t FragPipe-Analyst .

# Run FragPipe-Analyst
docker run -p 3838:3838 FragPipe-Analyst
```

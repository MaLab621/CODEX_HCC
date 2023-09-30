# CODEX_HCC
This repo accompanies the following manuscript:  

Maestri E, Kedei N, Khatib S, Forgues M, Ylaya K, Hewitt S, Wang L, Chaisaingmongkol J, Ruchirawat M, Ma L, Wang XW. Spatial proximity of tumor-immune interactions predicts patient outcome in hepatocellular carcinoma. Hepatology (2023). DOI: [10.1097/HEP.0000000000000600](https://doi.org/10.1097/hep.0000000000000600)

## DATA
The raw CODEX data for two HCC cohorts (TIGER and LCI) are available here.

## TIGER (n=58)
```r
#read in the data
library(data.table)
setwd('your_path/CODEX_HCC')

#cell matrix 16 markers x 116912 cells
mat <- readRDS("./TIGER/TIGER_CODEX_HCC.mtx.RDS")

#cell metadata with cell_id & x,y coordinates
meta <- fread("./TIGER/TIGER_CODEX_HCC.cellmeta.csv.gz")

#markers in TIGER data:
markers <- c("CD31", "CD8", "CD45", "CD20", "E-cadherin", "beta-catenin", "CD4", "CD163", "HNFalpha",
               "CD68", "CD45RO", "CD11c", "CD45RA", "CD3E", "Ki67", "CD44")
```

## LCI (n=132)
```r
#cell matrix 16 markers x 402042 cells
mat <- readRDS("./LCI/LCI_CODEX_HCC.mtx.RDS")
 
#cell metadata cell_id & x,y coordinates
meta <- fread("./LCI/LCI_CODEX_HCC.cellmeta.csv.gz")

#Markers in LCI data:
markers <- c("CD31", "CD8", "CD45", "CD20", "E-cadherin", "beta-catenin", "CD4", "CD163", "HNFalpha",
              "CD68", "CD45RO", "CD11c", "CD45RA", "CD3E", "Ki67", "CD44")
```
Please note the CODEX staining for LCI was done in 2 batches: block1 and block3 (the "batch" label in the cell metadata).
For each batch, slightly different tuning parameters were used for each marker's threshold for positivity to adjust for background.
For block1, the channels CD31 and CD20 were 0 due to poor quality staining.

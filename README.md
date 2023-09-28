# CODEX_HCC
This repo accompanies the following manuscript:  

Maestri E, Kedei N, Khatib S, Forgues M, Ylaya K, Hewitt S, Wang L, Chaisaingmongkol J, Ruchirawat M, Ma L, Wang XW. Spatial proximity of tumor-immune interactions predicts patient outcome in hepatocellular carcinoma. Hepatology (2023). DOI: 10.1097/HEP.0000000000000600 

## DATA
The raw CODEX data for two HCC cohorts (TIGER and LCI) are available here.

## TIGER
```r
#read in the data
setwd('your_path/CODEX_HCC')
library(data.table)

#cell matrix 16 markers x 116912 cells
mat <- readRDS("./TIGER_CODEX_HCC.mtx.RDS")

#cell metadata with cell_id & x,y coordinates
meta <- fread("./TIGER_CODEX_HCC.cellmeta.csv")

#markers in TIGER data:
markers <- c("CD31", "CD8", "CD45", "CD20", "E-cadherin", "beta-catenin", "CD4", "CD163", "HNFalpha",
               "CD68", "CD45RO", "CD11c", "CD45RA", "CD3E", "Ki67", "CD44")
```

## LCI

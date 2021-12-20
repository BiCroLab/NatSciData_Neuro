# BLISS_NatSciData

Code Repository for the BLISS Nature Scientific Data analyses

## Getting Started

### Required software

In order to succesfully execute the code in this repository, the following tools are needed:

- [R](https://www.r-project.org/) >= 3.6.0
- R packages (available via [Bioconductor](https://bioconductor.org/)): 
  - AnnotationDbi
  - GenomicFeatures
  - rtracklayer
  - data.table
  - ggplot2
  - gridExtra
  - cowplot
  - scales
  - tximport
  - ChIPpeakAnno
  - ChIPseeker
  - org.Hs.eg.db
  - EnsDb.Hsapiens.v75
  - BSgenome.Hsapiens.UCSC.hg19
  - TxDb.Hsapiens.UCSC.hg19.knownGene
- Optional R packages (it would require you to change some parts of the code if not installed):
  - knitr
  - ggpubr
  - ggthemes
  - ggsci
  - viridis
  - RColorBrewer

### Required actions

Some of the files that are employed in the script were too large to be uploaded without compression.
As a result, they have to be decompressed before being read in R. You can do this by executing the following commands:

Move to the main folder
```
cd BLISS_NatSciData
```

Move the the RNA-seq folder and decompress salmon files
```
cd data/RNAseq
tar -zxvf salmon_quantification.tar.gz
```

Move the the Hi-C folder and decompress the pre-processed files
```
cd ../HiC
tar -zxvf eigenvector_data.tar.gz
tar -zxvf insulation_data.tar.gz
tar -zxvf loop_data.tar.gz
```

Finally, main script assumes that the suspension BLISS (sBLISS) BED files required are located in the `data/BLISS` folder. Moreover, you should either rename the BED files as shown below or change the corresponding names in the main script. The raw data can be downloaded from the European Nucleotide Archive (ENA) under the accession [PRJEB49370](https://www.ebi.ac.uk/ena/browser/view/PRJEB49370). For information on how pre-processing, alignment and deduplication, please refer to the [blissNP processing pipeline](https://github.com/BiCroLab/blissNP).  

```
NES (replicate 1) --> NES_sBLISS_rep1.bed
NES (replicate 2) --> NES_sBLISS_rep2.bed
NPC (replicate 1) --> NPC_sBLISS_rep1.bed
NPC (replicate 2) --> NPC_sBLISS_rep2.bed
NEU (replicate 1) --> NEU_sBLISS_rep1.bed
NEU (replicate 2) --> NEU_sBLISS_rep2.bed
```

Once the data has been downloaded, processed and placed in the correct folder, you can open R and proceed with the analysis.

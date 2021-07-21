# Hierarchical Consensus Partitioning with cola <img src="https://user-images.githubusercontent.com/449218/100007031-b39db400-2dcb-11eb-919a-1d5c2a9eec24.png" width=200 align="right" style="border:4px solid black;" />


## Features

1. It can detect subgroups which show major differences and also moderate differences.
2. It can detect subgroups with large sizes as well as with tiny sizes.
3. It generates detailed HTML reports for the complete analysis.

## Install

Hierarchical consensus partitioning is part of [the **cola** package](https://github.com/jokergoo/cola) (version >= 2.0.0). You can install it by:

```r
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install("cola")
```

The latest version can be installed directly from GitHub:

```r
library(devtools)
install_github("jokergoo/cola")
```

## Hierarchical Consensus Partitioning


<img src="https://user-images.githubusercontent.com/449218/126491482-31a9496f-cc4d-4c4f-80b7-7b752d8d8d06.png" width="400" />



### Usage

Three lines of code to perfrom hierarchical consensus partitioning analysis:

```r
mat = adjust_matrix(mat) # optional
rh = hierarchical_partition(mat, mc.cores = ...)
cola_report(rh, output_dir = ...)
```

### Plots

Following figure shows the hierarchy of the subgroups.

<img src="https://user-images.githubusercontent.com/449218/100014572-d7b2c280-2dd6-11eb-9265-a84d324122f2.png" width="300" />

Following figure shows the signature genes.

<img src="https://user-images.githubusercontent.com/449218/100014657-f913ae80-2dd6-11eb-9bf7-53f733e9f8f0.png" width="600" />

### Examples

|Dataset                   | Number of columns|Data type                   |HTML Report                                          |Data source                                                                        |
|:-------------------------|-----------------:|:---------------------------|:----------------------------------------------------|:----------------------------------------------------------------------------------|
|HSMM_single_cell          |               271|scRNASeq                    |https://cola-rh.github.io/HSMM_single_cell/          |https://bioconductor.org/packages/release/data/experiment/html/HSMMSingleCell.html |
|PBMC                      |              2638|scRNASeq                    |https://cola-rh.github.io/PBMC/                      |https://satijalab.org/seurat/articles/pbmc3k_tutorial.html                         |
|GSE90496                  |              2801|450K methylation array      |https://cola-rh.github.io/GSE90496/                  |https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE90496                        |
|Golub_leukemia            |                72|Microarray, gene expression |https://cola-rh.github.io/Golub_leukemia/            |https://bioconductor.org/packages/release/data/experiment/html/golubEsets.html     |
|Ritz_ALL                  |               128|Microarray, gene expression |https://cola-rh.github.io/Ritz_ALL/                  |https://bioconductor.org/packages/release/data/experiment/html/ALL.html            |
|TCGA_GBM_microarray       |               173|Microarray, gene expression |https://cola-rh.github.io/TCGA_GBM_microarray/       |https://gdc.cancer.gov/about-data/publications/gbm_exp                             |
|BaronPancreas_mouse       |              1886|scRNASeq                    |https://cola-rh.github.io/BaronPancreas_mouse/       |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|BuettnerESC               |               288|scRNASeq                    |https://cola-rh.github.io/BuettnerESC/               |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|DarmanisBrain             |               466|scRNASeq                    |https://cola-rh.github.io/DarmanisBrain/             |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|GrunHSC                   |              1915|scRNASeq                    |https://cola-rh.github.io/GrunHSC/                   |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|GrunPancreas              |              1728|scRNASeq                    |https://cola-rh.github.io/GrunPancreas/              |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|KolodziejczykESC          |               704|scRNASeq                    |https://cola-rh.github.io/KolodziejczykESC/          |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|LaMannoBrain_human_es     |              1715|scRNASeq                    |https://cola-rh.github.io/LaMannoBrain_human_es/     |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|LaMannoBrain_human_embryo |              1977|scRNASeq                    |https://cola-rh.github.io/LaMannoBrain_human_embryo/ |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|LaMannoBrain_human_ips    |               337|scRNASeq                    |https://cola-rh.github.io/LaMannoBrain_human_ips/    |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|LaMannoBrain_adult        |               243|scRNASeq                    |https://cola-rh.github.io/LaMannoBrain_adult/        |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|LaMannoBrain_mouse_embryo |              1907|scRNASeq                    |https://cola-rh.github.io/LaMannoBrain_mouse_embryo/ |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|LawlorPancreas            |               638|scRNASeq                    |https://cola-rh.github.io/LawlorPancreas/            |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|LengESC                   |               460|scRNASeq                    |https://cola-rh.github.io/LengESC/                   |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|ReprocessedTh2            |                96|scRNASeq                    |https://cola-rh.github.io/ReprocessedTh2/            |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|MessmerESC                |              1344|scRNASeq                    |https://cola-rh.github.io/MessmerESC/                |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|MuraroPancreas            |              3072|scRNASeq                    |https://cola-rh.github.io/MuraroPancreas/            |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|NestorowaHSC              |              1920|scRNASeq                    |https://cola-rh.github.io/NestorowaHSC/              |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|PollenGlia                |               367|scRNASeq                    |https://cola-rh.github.io/PollenGlia/                |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|RichardTCell              |               572|scRNASeq                    |https://cola-rh.github.io/RichardTCell/              |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|RomanovBrai               |              2881|scRNASeq                    |https://cola-rh.github.io/RomanovBrai/               |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|SegerstolpePancreas       |              3514|scRNASeq                    |https://cola-rh.github.io/SegerstolpePancreas/       |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|UsoskinBrain              |               864|scRNASeq                    |https://cola-rh.github.io/UsoskinBrain/              |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|TasicBrain                |              1809|scRNASeq                    |https://cola-rh.github.io/TasicBrain/                |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|ReprocessedAllen          |               379|scRNASeq                    |https://cola-rh.github.io/ReprocessedAllen/          |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|XinPancreas               |              1600|scRNASeq                    |https://cola-rh.github.io/XinPancreas/               |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|ZeiselBrain               |              3005|scRNASeq                    |https://cola-rh.github.io/ZeiselBrain/               |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|Fluidigm                  |                65|scRNASeq                    |https://cola-rh.github.io/Fluidigm/                  |https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html       |
|TCGA_ACC_methylation      |                80|450K methylation array      |https://cola-rh.github.io/TCGA_ACC_methylation/      |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_BLCA_methylation     |               434|450K methylation array      |https://cola-rh.github.io/TCGA_BLCA_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_BRCA_methylation     |               888|450K methylation array      |https://cola-rh.github.io/TCGA_BRCA_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_CESC_methylation     |               312|450K methylation array      |https://cola-rh.github.io/TCGA_CESC_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_COAD_methylation     |               337|450K methylation array      |https://cola-rh.github.io/TCGA_COAD_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_COADREAD_methylation |               443|450K methylation array      |https://cola-rh.github.io/TCGA_COADREAD_methylation/ |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_ESCA_methylation     |               202|450K methylation array      |https://cola-rh.github.io/TCGA_ESCA_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_GBM_methylation      |               155|450K methylation array      |https://cola-rh.github.io/TCGA_GBM_methylation/      |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_GBMLGG_methylation   |               685|450K methylation array      |https://cola-rh.github.io/TCGA_GBMLGG_methylation/   |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_HNSC_methylation     |               580|450K methylation array      |https://cola-rh.github.io/TCGA_HNSC_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_KICH_methylation     |                66|450K methylation array      |https://cola-rh.github.io/TCGA_KICH_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_KIRC_methylation     |               480|450K methylation array      |https://cola-rh.github.io/TCGA_KIRC_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_KIRP_methylation     |               321|450K methylation array      |https://cola-rh.github.io/TCGA_KIRP_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_LAML_methylation     |               194|450K methylation array      |https://cola-rh.github.io/TCGA_LAML_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_LGG_methylation      |               530|450K methylation array      |https://cola-rh.github.io/TCGA_LGG_methylation/      |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_LIHC_methylation     |               429|450K methylation array      |https://cola-rh.github.io/TCGA_LIHC_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_LUAD_methylation     |               492|450K methylation array      |https://cola-rh.github.io/TCGA_LUAD_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_LUNG_methylation     |               907|450K methylation array      |https://cola-rh.github.io/TCGA_LUNG_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_LUSC_methylation     |               415|450K methylation array      |https://cola-rh.github.io/TCGA_LUSC_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_MESO_methylation     |                87|450K methylation array      |https://cola-rh.github.io/TCGA_MESO_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_PAAD_methylation     |               195|450K methylation array      |https://cola-rh.github.io/TCGA_PAAD_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_PCPG_methylation     |               187|450K methylation array      |https://cola-rh.github.io/TCGA_PCPG_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_PRAD_methylation     |               549|450K methylation array      |https://cola-rh.github.io/TCGA_PRAD_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_READ_methylation     |               106|450K methylation array      |https://cola-rh.github.io/TCGA_READ_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_SARC_methylation     |               269|450K methylation array      |https://cola-rh.github.io/TCGA_SARC_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_SKCM_methylation     |               476|450K methylation array      |https://cola-rh.github.io/TCGA_SKCM_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_STAD_methylation     |               398|450K methylation array      |https://cola-rh.github.io/TCGA_STAD_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_TGCT_methylation     |               156|450K methylation array      |https://cola-rh.github.io/TCGA_TGCT_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_THCA_methylation     |               571|450K methylation array      |https://cola-rh.github.io/TCGA_THCA_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_THYM_methylation     |               126|450K methylation array      |https://cola-rh.github.io/TCGA_THYM_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_UCEC_methylation     |               478|450K methylation array      |https://cola-rh.github.io/TCGA_UCEC_methylation/     |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_UCS_methylation      |                57|450K methylation array      |https://cola-rh.github.io/TCGA_UCS_methylation/      |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443               |
|TCGA_UVM_methylation      |                80|450K methylation array      |https://cola-rh.github.io/TCGA_UVM_methylation/      |https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443

## License

MIT @ Zuguang Gu

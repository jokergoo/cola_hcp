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

|Dataset                                                                                                   | #Columns|Data type                   |HTML Report                                          |
|:---------------------------------------------------------------------------------------------------------|--------:|:---------------------------|:----------------------------------------------------|
|[HSMM_single_cell](https://bioconductor.org/packages/release/data/experiment/html/HSMMSingleCell.html)    |      271|scRNASeq                    |https://cola-rh.github.io/HSMM_single_cell/          |
|[PBMC](https://satijalab.org/seurat/articles/pbmc3k_tutorial.html)                                        |     2638|scRNASeq                    |https://cola-rh.github.io/PBMC/                      |
|[GSE90496](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE90496)                                   |     2801|450K methylation array      |https://cola-rh.github.io/GSE90496/                  |
|[Golub_leukemia](https://bioconductor.org/packages/release/data/experiment/html/golubEsets.html)          |       72|Microarray, gene expression |https://cola-rh.github.io/Golub_leukemia/            |
|[Ritz_ALL](https://bioconductor.org/packages/release/data/experiment/html/ALL.html)                       |      128|Microarray, gene expression |https://cola-rh.github.io/Ritz_ALL/                  |
|[TCGA_GBM_microarray](https://gdc.cancer.gov/about-data/publications/gbm_exp)                             |      173|Microarray, gene expression |https://cola-rh.github.io/TCGA_GBM_microarray/       |
|[BaronPancreas_mouse](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)       |     1886|scRNASeq                    |https://cola-rh.github.io/BaronPancreas_mouse/       |
|[BuettnerESC](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)               |      288|scRNASeq                    |https://cola-rh.github.io/BuettnerESC/               |
|[DarmanisBrain](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)             |      466|scRNASeq                    |https://cola-rh.github.io/DarmanisBrain/             |
|[GrunHSC](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)                   |     1915|scRNASeq                    |https://cola-rh.github.io/GrunHSC/                   |
|[GrunPancreas](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)              |     1728|scRNASeq                    |https://cola-rh.github.io/GrunPancreas/              |
|[KolodziejczykESC](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)          |      704|scRNASeq                    |https://cola-rh.github.io/KolodziejczykESC/          |
|[LaMannoBrain_human_es](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)     |     1715|scRNASeq                    |https://cola-rh.github.io/LaMannoBrain_human_es/     |
|[LaMannoBrain_human_embryo](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html) |     1977|scRNASeq                    |https://cola-rh.github.io/LaMannoBrain_human_embryo/ |
|[LaMannoBrain_human_ips](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)    |      337|scRNASeq                    |https://cola-rh.github.io/LaMannoBrain_human_ips/    |
|[LaMannoBrain_adult](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)        |      243|scRNASeq                    |https://cola-rh.github.io/LaMannoBrain_adult/        |
|[LaMannoBrain_mouse_embryo](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html) |     1907|scRNASeq                    |https://cola-rh.github.io/LaMannoBrain_mouse_embryo/ |
|[LawlorPancreas](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)            |      638|scRNASeq                    |https://cola-rh.github.io/LawlorPancreas/            |
|[LengESC](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)                   |      460|scRNASeq                    |https://cola-rh.github.io/LengESC/                   |
|[ReprocessedTh2](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)            |       96|scRNASeq                    |https://cola-rh.github.io/ReprocessedTh2/            |
|[MessmerESC](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)                |     1344|scRNASeq                    |https://cola-rh.github.io/MessmerESC/                |
|[MuraroPancreas](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)            |     3072|scRNASeq                    |https://cola-rh.github.io/MuraroPancreas/            |
|[NestorowaHSC](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)              |     1920|scRNASeq                    |https://cola-rh.github.io/NestorowaHSC/              |
|[PollenGlia](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)                |      367|scRNASeq                    |https://cola-rh.github.io/PollenGlia/                |
|[RichardTCell](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)              |      572|scRNASeq                    |https://cola-rh.github.io/RichardTCell/              |
|[RomanovBrai](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)               |     2881|scRNASeq                    |https://cola-rh.github.io/RomanovBrai/               |
|[SegerstolpePancreas](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)       |     3514|scRNASeq                    |https://cola-rh.github.io/SegerstolpePancreas/       |
|[TasicBrain](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)                |     1809|scRNASeq                    |https://cola-rh.github.io/TasicBrain/                |
|[ReprocessedAllen](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)          |      379|scRNASeq                    |https://cola-rh.github.io/ReprocessedAllen/          |
|[XinPancreas](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)               |     1600|scRNASeq                    |https://cola-rh.github.io/XinPancreas/               |
|[ZeiselBrain](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)               |     3005|scRNASeq                    |https://cola-rh.github.io/ZeiselBrain/               |
|[Fluidigm](https://bioconductor.org/packages/release/data/experiment/html/scRNAseq.html)                  |       65|scRNASeq                    |https://cola-rh.github.io/Fluidigm/                  |
|[TCGA_ACC_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)              |       80|450K methylation array      |https://cola-rh.github.io/TCGA_ACC_methylation/      |
|[TCGA_BLCA_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      434|450K methylation array      |https://cola-rh.github.io/TCGA_BLCA_methylation/     |
|[TCGA_BRCA_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      888|450K methylation array      |https://cola-rh.github.io/TCGA_BRCA_methylation/     |
|[TCGA_CESC_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      312|450K methylation array      |https://cola-rh.github.io/TCGA_CESC_methylation/     |
|[TCGA_COAD_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      337|450K methylation array      |https://cola-rh.github.io/TCGA_COAD_methylation/     |
|[TCGA_COADREAD_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)         |      443|450K methylation array      |https://cola-rh.github.io/TCGA_COADREAD_methylation/ |
|[TCGA_ESCA_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      202|450K methylation array      |https://cola-rh.github.io/TCGA_ESCA_methylation/     |
|[TCGA_GBM_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)              |      155|450K methylation array      |https://cola-rh.github.io/TCGA_GBM_methylation/      |
|[TCGA_GBMLGG_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)           |      685|450K methylation array      |https://cola-rh.github.io/TCGA_GBMLGG_methylation/   |
|[TCGA_HNSC_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      580|450K methylation array      |https://cola-rh.github.io/TCGA_HNSC_methylation/     |
|[TCGA_KICH_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |       66|450K methylation array      |https://cola-rh.github.io/TCGA_KICH_methylation/     |
|[TCGA_KIRC_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      480|450K methylation array      |https://cola-rh.github.io/TCGA_KIRC_methylation/     |
|[TCGA_KIRP_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      321|450K methylation array      |https://cola-rh.github.io/TCGA_KIRP_methylation/     |
|[TCGA_LAML_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      194|450K methylation array      |https://cola-rh.github.io/TCGA_LAML_methylation/     |
|[TCGA_LGG_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)              |      530|450K methylation array      |https://cola-rh.github.io/TCGA_LGG_methylation/      |
|[TCGA_LIHC_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      429|450K methylation array      |https://cola-rh.github.io/TCGA_LIHC_methylation/     |
|[TCGA_LUAD_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      492|450K methylation array      |https://cola-rh.github.io/TCGA_LUAD_methylation/     |
|[TCGA_LUNG_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      907|450K methylation array      |https://cola-rh.github.io/TCGA_LUNG_methylation/     |
|[TCGA_LUSC_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      415|450K methylation array      |https://cola-rh.github.io/TCGA_LUSC_methylation/     |
|[TCGA_MESO_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |       87|450K methylation array      |https://cola-rh.github.io/TCGA_MESO_methylation/     |
|[TCGA_PAAD_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      195|450K methylation array      |https://cola-rh.github.io/TCGA_PAAD_methylation/     |
|[TCGA_PCPG_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      187|450K methylation array      |https://cola-rh.github.io/TCGA_PCPG_methylation/     |
|[TCGA_PRAD_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      549|450K methylation array      |https://cola-rh.github.io/TCGA_PRAD_methylation/     |
|[TCGA_READ_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      106|450K methylation array      |https://cola-rh.github.io/TCGA_READ_methylation/     |
|[TCGA_SARC_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      269|450K methylation array      |https://cola-rh.github.io/TCGA_SARC_methylation/     |
|[TCGA_SKCM_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      476|450K methylation array      |https://cola-rh.github.io/TCGA_SKCM_methylation/     |
|[TCGA_STAD_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      398|450K methylation array      |https://cola-rh.github.io/TCGA_STAD_methylation/     |
|[TCGA_TGCT_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      156|450K methylation array      |https://cola-rh.github.io/TCGA_TGCT_methylation/     |
|[TCGA_THCA_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      571|450K methylation array      |https://cola-rh.github.io/TCGA_THCA_methylation/     |
|[TCGA_THYM_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      126|450K methylation array      |https://cola-rh.github.io/TCGA_THYM_methylation/     |
|[TCGA_UCEC_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)             |      478|450K methylation array      |https://cola-rh.github.io/TCGA_UCEC_methylation/     |
|[TCGA_UCS_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)              |       57|450K methylation array      |https://cola-rh.github.io/TCGA_UCS_methylation/      |
|[TCGA_UVM_methylation](https://xenabrowser.net/datapages/?hub=https://tcga.xenahubs.net:443)              |       80|450K methylation array      |https://cola-rh.github.io/TCGA_UVM_methylation/      |

## License

MIT @ Zuguang Gu

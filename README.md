# Hierarchical Consensus Partitioning with cola <img src="https://user-images.githubusercontent.com/449218/100007031-b39db400-2dcb-11eb-919a-1d5c2a9eec24.png" width=200 align="right" style="border:4px solid black;" />


## Features

1. It modularizes the consensus clustering processes that various methods can
   be easily integrated in different steps of the analysis.
2. It provides rich visualizations for intepreting the results.
3. It allows running multiple methods at the same time and provides
   functionalities to compare results in a straightforward way.
4. It provides a new method to extract features which are more efficient to
   separate subgroups.
5. It generates detailed HTML reports for the complete analysis.

## Install

Hierarchical consensus partitioning is part of [the **cola** package](https://github.com/jokergoo/cola). You can install it by:

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

<img width="700" src="https://user-images.githubusercontent.com/449218/100007575-90bfcf80-2dcc-11eb-8fd1-99d0011674b7.png" />

The steps are:

1. The input matrix _M_ is treated as the top node in the hierarchy, with a
   node label "0".
2. Apply multiple combinations of top-value methods and partitioning methods
   on the matrix with a small set of k (_e.g._, 2-4).
3. Select the consensus partitioning result (_i.e._ with a specific top-value
   method and a partitioning method) which shows the highest 1-PAC scores with
   its best k. This consensus partitioning is treated as the partitioning on
   the node.
4. If this partitioning is not stable (_e.g._, 1-PAC > 0.8), the hierarchical
   partitioning stops and the columns of the matrix are treated as a subgroup.
5. If the number of signatures or the fraction of signatures to the total
   number of rows in the matrix is too small, it means the partitioning does
   not show biological meaningful results and the hierarchical partitioning
   stops. The columns are treated as a subgroup.
6. If the partioning passes the filtering on step 4 and 5, the columns are
   split into two groups, where the one group with the label "1" from **cola**
   classification and the second group contains columns with other class
   labels, with the corresponding submatrices denoted as _M_<sub>1</sub> and
   _M_<sub>0</sub> respectively. In **cola**, the group with label "1" always
   has the minimal mean within-group distance. The two submatrices are treated
   as two children node of the current node and "1" or "0" is append to the
   node label as the labels for the two children nodes.
7. For each submatrix, if the number of columns is too small, the hierarchical
   partitioning stops and the columns are treated as a subgroup.
8. If the submatrix has enough columns, go to step 2 to perform consensus
   partioning recursively.

### Usage

Three lines of code to perfrom hierarchical consensus partitioning analysis:

```r
mat = adjust_matrix(mat) # optional
rh = hierarchical_partition(
    mat, 
    mc.cores = ...)
cola_report(rh, output_dir = ...)
```

### Plots

Following plots compare consensus heatmaps with k = 4 under all combinations of methods.

<img src="https://user-images.githubusercontent.com/449218/52631118-3a66f280-2ebe-11e9-8dea-0172d9beab91.png" />


## License

MIT @ Zuguang Gu

# FlowSOM-Rtsne example

This repository contains a worked example showing how to cluster and visualize a mass cytometry (CyTOF) data set, using [FlowSOM](http://bioconductor.org/packages/release/bioc/html/FlowSOM.html) for clustering and [Rtsne](https://github.com/jkrijthe/Rtsne) for visualization.


## FlowSOM

FlowSOM is an R/Bioconductor package for clustering flow cytometry and mass cytometry (CyTOF) data (see [paper](http://www.ncbi.nlm.nih.gov/pubmed/25573116) and [Bioconductor package](http://bioconductor.org/packages/release/bioc/html/FlowSOM.html)). The clustering algorithm is based on self-organizing maps and hierarchical consensus meta-clustering.

We previously showed that FlowSOM performs very well for clustering high-dimensional CyTOF data, and in particular has extremely fast runtimes (see [paper published in Cytometry Part A](http://onlinelibrary.wiley.com/doi/10.1002/cyto.a.23030/full) and [code repository on GitHub](https://github.com/lmweber/cytometry-clustering-comparison)).


## Rtsne and t-SNE

Rtsne is an R implementation of the popular t-SNE algorithm (see [t-SNE algorithm page](https://lvdmaaten.github.io/tsne/), [Rtsne development page](https://github.com/jkrijthe/Rtsne), and [Rtsne package on CRAN](https://cran.r-project.org/web/packages/Rtsne/index.html)).

The t-SNE algorithm projects high-dimensional data to 2 or 3 dimensions for visualization. This is conceptually similar to principal component analysis (PCA). However, the t-SNE algorithm is non-linear (while PCA is linear), making t-SNE much better suited for many types of biological data.

On a t-SNE plot of flow or mass cytometry data, points "near" to each other can be interpreted as belonging to the same or similar cell populations. However, the precise distances in the plot are not meaningful, so care should be taken not to over-interpret the plot. The algorithm also has a random start, so unless a random seed is used (as in this example), each run will look slightly different.


## Contents

The repository contains the following files.

- R code script: [FlowSOM_Rtsne_example.R](FlowSOM_Rtsne_example.R)
- data file: [data/Samusik_01_notransform.fcs](data/Samusik_01_notransform.fcs)
- output plot file: [plots/FlowSOM_Rtsne_plot.pdf](plots/FlowSOM_Rtsne_plot.pdf)
- output file of FlowSOM cluster labels: [results/cluster_labels_FlowSOM.txt](results/cluster_labels_FlowSOM.txt)




##I] Capturing gene expression in Platynereis dumerilii's brain
###  1/ Platynereis dumerilii, an ideal organism of brain development studies
####     i) General description
####     ii) Synchronous development of the larvae
####     iii) Spatial organization of complex biological tissues like the brain

###  2/ Gene expression in Platynereis' developing brain
####     i) Mechanisms of gene expression
####     ii) Brain development and cell differentiation

###  3/ Capturing gene expression in the laboratory
####     i) In-situ hybridization assays
####     ii) Building a referenced library of gene expression for Platynereis
         - Stereotypical development allows one gene to be considered as reference
####     iii) RNA sequencing


##II] From tissue to single cell transcriptomics, a paradigm shift
###  1/ Spatially referenced single cell-like in-situ hybridization data
####     i) Dividing images into "cells"
####     ii) A simple cell model, the "cube" data

###  2/ Singe cell RNA sequencing, building a map of the full transcriptome
####     i) Sequencing single cell RNA contents
####     ii) Mapping back gene expression to a spatial reference

###  3/ About the quantitative trait of single cell expression data
####     i) Light contamination in in-situ hybridization data
####     ii) Technical noise in single cell RNA-seq data

###  4/ Binarizing gene expression datasets
####     i) Binarizing for a limited number of genes
####     ii) Binarizing whole trnscriptomes
	 
##III] Clustering tissues from single cell expression data
###  1/ Elements of clustering for biological tissues
####     i) Why cluster?
####     ii) General considerations about clustering
        - No perfect method
        - directed vs undirected
        - choosing the number of cluster, a key issue

###  2/ Non spatial clustering methods
####     i) Hierarchical clustering 
####     ii) Independent mixture models

###  3/ Visualizing clustering results in 3D with bioWeb3D
####     i) Background
####     ii) Implementation
####     iii) Results and discussion

###  4/ Discussion 
####     i) Spatial clustering techniques (hierarchical, model based)
####     ii) Method chosen


##IV] Hidden Markov Random fields for biological data clustering
###  1/ Markov Random fields and Gibbs distribution
####     i) Neighborhood systems
####     ii) Defining a Markov field
####     iii) Single and multiple beta models in a biological context
####     iv) Considerations about the normalizing constant W(beta)

###  2/ Hidden Markov models
####     i) Conditional independence in the observed data
####     ii) Prior distribution on the conditional field
####     iii) Full likelihood of the model

###  3/ Parameter estimation using the EM principle
####     i) Model expectation decomposition
####     ii) Estimating Ry(theta | phi ^ L)
####     iii) Estimating Rz(beta | phi ^ L)
####     iv) Introducing the mean field principle

###  4/ Mean field EM algorithm
####     i) Mean field for estimating the tihms
####     ii) Mean field for estimating W(beta)

###  5/ Maximization

###  6/ Choosing K
####     i) BIC method
####     ii) BIC for highly symmetrical data


##V] Method validation and performance analysis on simulated data
###  1/ Simulating data with a spatial component 
####     i) Simulating non spatial gene expression data
####     ii) Introducing a known spatial context
     iii)Expected results

###  2/ Aligning clustering results 
####     i) Theoretical problem in comparing clustering results
#######     ii) Alignment via similarity/specificity matric

###  3/ Validation of parameters estimation and model choosing
####     i) Estimation of beta
####     ii) Estimation of theta
####     iii) Choosing K

###  4/ Method performance and initialization
####     i) Shortcomings of the EM principle
####     ii) Random initialization vs Hclust initialization

###  5/ Method performance compared to Hclust and independent mixture models
####     i) Results of comparison
####     ii) Discussion


##VI] Applying a MRF clustering method to single cell in-situ hybridization data in the brain of Platynereis dumerilii
###  1/ Downstream analysis opportunities offered by the model
####     i) Signification of Theta
####     ii) Cluster specific gene scoreing

###  3/ Choosing K on biological data
####     i) BIC results on biological data
####     ii) Discussion of choice of K(hat)

###  2/ Finding known biological structures to validate the method
####     i) Platynereis' eyes
####     ii) Mushroom bodies
####     iii) Apical organ
####     iiii) Motor regions

###  4/ Generating functional hypothesis about unknown biological tissues
####     i) Links between known regions
####     ii) Substructures in known tissues
####     iii) Novel tissues

###  5/ Discussion 
####     i) Validity hypothesis 
####     ii) Shortcomings of the method


##VII] Conclusion and future developments
###  1/ Conclusions
###  2/ Main challenges for the future
####     i) Applying the method for RNA-seq data
####     ii) Validity of the threshold 
####     iii) Applying the method 
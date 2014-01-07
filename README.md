##I] Capturing gene expression in Platynereis dumerilii's brain
####  1/ Platynereis dumerilii, an ideal organism of brain development studies
######     i) General description
    - Marine annelid
    - Place in evolution 
    - Link between fast evolving models (drosophila) and vertebrates
    - Phases of development : larvae and adult
    - Larvae and adult behavior

 
######     ii) Synchronous development of the larvae
    - Producing Platynereis in the lab
    - Stereotypical development of the lavae brain 
    - FIG 1 : two slices of the same region at 48hpf in 2 different individuals

####  2/ Gene expression in Platynereis' developing brain
######     i) Mechanisms of gene expression
    - Generalities about gene expression
    - Genes, transcription factors, all cells have the same genome expression differs

######     ii) Platynereis' brain development
    - General development pattern (symmetries, eyes, mushroom)
    - LOOK for a paper summing that up
    - State of the brain at 48hpf because we'll use it later

######     iii) Spatial organization of complex biological tissues like the brain
    - Some tissues will be spatially well defined others will be scattered
    - Example with the pancreas ?
    - Introducing the idea of the spacial coherency heterogeneity

####  3/ Capturing gene expression in the laboratory
######     i) In-situ hybridization assays
    - FIG 2 : In situ hybridization principles
    - Explanations about the technique 

######     ii) Building a referenced library of gene expression for Platynereis
         - Stereotypical development allows one gene to be considered as reference
    - Different individuals are "replicates"
    - Mapping to a scaffold created by the reference gene

######     iii) RNA sequencing
    - FIG 3 : about RNA sequencing for tissues
    - Explanations about the technique
    - Obtaining the full transcriptome at once
    - Necessity of having the genome to map to or a list of known genes (primR) 
    - Discuss the starting RNA quantity 
    - Discuss the fact that gene expression is averaged over the tissue losing spatial information.


##II] From tissue to single cell transcriptomics, a paradigm shift
####  1/ Spatially referenced single cell-like in-situ hybridization data
######     i) Dividing images into "cells"
    - Images with a good enough resolution can determine expression at the single cell level.
    - But every cell is different in terms of shape and size => need for a cell model
    - in-situ hybridization keeps the spatial information of every cell
    - Present possibilities for cell model with membrane markers etc... but to start with, a simple mode is possible => next paragraph

######     ii) A simple cell model, the "cube" data
    - FIG 4 : From images to luminiscence cube data
    - Present the cube cell model, and its assumptions
    - cells have roughly the same size 
    - cells are roughly cubical
    - Present the choice of size for the cubes (3um or 6 um)
    - This model introduces errors (cells divided or several cells in one cube, empty cubes between cells)
    - => When working on this data we will need methods that are able to smooth those mistakes over.

####  2/ Singe cell RNA sequencing, building a map of the full transcriptome
######     i) Sequencing single cell RNA contents
    - Same as tissue sequencing but with a lot less starting material
    - Present the main techniques used (see with Luis) : Microfluidics and others
    - We obtain the full transcriptome of every cell sequenced

######     ii) Mapping back gene expression to a spatial reference
    - Single cell RNA-seq at the moment does not allow to track cell localization
    - Need to map the transcriptome back to a spatial reference
    - Use in-situ hybridization results as reference


####  3/ About the quantitative trait of single cell expression data
######     i) Light contamination in in-situ hybridization data
    - FIG 5 : show light intensity across one slice
    - Explain problem of scale and light contamination

######     ii) Technical noise in single cell RNA-seq data
    - FIG 6 : show "typical" correlation plot from single cell RNA-seq with the noise increasing when reducing starting material
    - Both methods are currently unreliable quantitatively => need to binarize

####  4/ Binarizing gene expression datasets
######     i) Binarizing in-situ hybrdization datasets
    - With biological knowledge and a limited number of genes
    - Possibility to compare spatially the resulting binary expression patterns to microscope data and adjust for each gene the threshold manually
######     ii) Binarizing whole transcriptomes
    - Manual curation no longer possible
    - Thresholding ideally with density peaks
    - Problems that may occur and possible solutions (figure?)

####  5/ Preliminary results on mapping single cell RNA-seq data in from Platynereis' brain
######     i) Single cell RNA-seq in Platynereis' brain
    - Present the data (number of cell)
    - Present the method used (to dissolve the brain, to capture the cells, to sequence the cells
######     ii) Mapping back RNA-seq data back to PrimR in-situ hybridization assays
    - Select the overlapping genes
    - Present mapping method (Nuno's pipeline)
    - Present simple mapping technique and why it is not satisfactory
    - Present John's method  
    - FIG 6: find a nice way to show a few good examples of mapping
	 
##III] Clustering tissues from single cell expression data and visualizing them in a 3D space
####  1/ Elements of clustering for biological tissues
######     i) Why cluster?
    - Single cell data has a lot of potential but:
    - Big data general problem
    - need to be able to come back from the single cell level to the tissue for : a consistency check and improve the knowleddge at the tissue level from single cell level

######     ii) General considerations about clustering
    - No perfect method
    - directed vs undirected
    - choosing the number of cluster, a key issue

####  2/ Visualizing clustering results in 3D with bioWeb3D
######     i) Background
######     ii) Implementation
######     iii) Results and discussion
    - This section is the bioweb3D paper

####  3/ Non spatial clustering methods
######     i) Hierarchical clustering
    - General description of the method
    - Computing distance matrix on binary expression data
    - Hclust method to use (full or partial)
    - Discuss the choosing the K with hClust (dendrogram is not informative)
 
######     ii) Independent mixture models
    - General statistical framework
    - Present the model
    - Gene independence hypothesis (this will be discussed further in the next chapter)
    - Likelihood of the model
    - EM algorithm to maximize the parameters (theta)
    - Choosing K with the BIC

####  4/ Discussion 
######     i) Spatial clustering techniques (hierarchical, model based)
    - Limits of non spatial methods on noisy data (cite the "cell model of chapter 1" paragraph)
    - Not using the spatial data seems silly when we do have it (playing chess blind comparison ?)
    - Some clustering methods are able to take into account the spatial localization of the data points as well as the expression data
    - Quickly present spatial methods (spatial hclust), Mixture with a spatial component

######     ii) Method chosen
    - MRF because theta parameters are informative, easy to compute a likelihood and to choose K


##IV] Hidden Markov Random fields for biological data clustering
    - Extended methods part of the MRF paper
    
####  1/ Markov Random fields and Gibbs distribution
######     i) Neighborhood systems
######     ii) Defining a Markov field
######     iii) Single and multiple beta models in a biological context
######     iv) Considerations about the normalizing constant W(beta)

####  2/ Hidden Markov models
######     i) Conditional independence in the observed data
######     ii) Prior distribution on the conditional field
######     iii) Full likelihood of the model

####  3/ Parameter estimation using the EM principle
######     i) Model expectation decomposition
######     ii) Estimating Ry(theta | phi ^ L)
######     iii) Estimating Rz(beta | phi ^ L)
######     iv) Introducing the mean field principle

####  4/ Mean field EM algorithm
######     i) Mean field for estimating the tihms
######     ii) Mean field for estimating W(beta)

####  5/ Maximization

####  6/ Choosing K
######     i) BIC method
######     ii) BIC for highly symmetrical data


##V] Method validation and performance analysis on simulated data
    - Extended simulation part of the MRF paper

####  1/ Simulating data with a spatial component 
######     i) Simulating non spatial gene expression data
######     ii) Introducing a known spatial context
######     iii)Expected results

####  2/ Aligning clustering results 
######     i) Theoretical problem in comparing clustering results
##########     ii) Alignment via similarity/specificity matric

####  3/ Validation of parameters estimation and model choosing
######     i) Estimation of beta
######     ii) Estimation of theta
######     iii) Choosing K

####  4/ Method performance and initialization
######     i) Shortcomings of the EM principle
######     ii) Random initialization vs Hclust initialization

####  5/ Method performance compared to Hclust and independent mixture models
######     i) Results of comparison
######     ii) Discussion


##VI] Applying a MRF clustering method to single cell in-situ hybridization data in the brain of Platynereis dumerilii
####  1/ Downstream analysis opportunities offered by the model
######     i) Signification of Theta
######     ii) Cluster specific gene scoreing

####  3/ Choosing K on biological data
######     i) BIC results on biological data
######     ii) Discussion of choice of K(hat)

####  2/ Finding known biological structures to validate the method
######     i) Platynereis' eyes
######     ii) Mushroom bodies
######     iii) Apical organ
######     iiii) Motor regions

####  4/ Generating functional hypothesis about unknown biological tissues
######     i) Links between known regions
######     ii) Substructures in known tissues
######     iii) Novel tissues

####  5/ Discussion 
######     i) Validity hypothesis 
######     ii) Shortcomings of the method


##VII] Conclusion and future developments
####  1/ Conclusions
    - Method successfully adapted and modified from another field to what will be one of the main focus in science in the next decade
    - Application is not limited to functional organs but also to tumors 
    - Personalized medicine and tumor heterogeneity will be the next step in cancer treatment and this method may prove useful

####  2/ Main challenges for the future
######     i) Applying the method for RNA-seq data
######     ii) Validity of the threshold 
######     iii) Applying the method 
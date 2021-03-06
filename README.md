# CoCoCoNet User Manual (UNDER CONSTRUCTION)

CoCoCoNet is a simple to use webserver that allows the user to build, view and analyze co-expression networks without having to input experimental data. Because gene expression data is inherently noisy, meta-analysis provides a method to significantly improve the quality of data when assessed using the Guilt by Association (GBA) principle. This data is curated by aggregating the expression reads of many RNA-seq experiments obtained through the NCBI's SRA database [1] using guidelines outlined in [2]. 

To use CoCoCoNet, simply input a list of genes (or a single gene) as gene symbols and the corresponding species to be used in the construction of the network. Given these, you can select optional parameters, described below, generate the results and view the distribution of co-expression values as well as the network. CoCoCoNet also allows you to compare the network with another species using a 1 to 1 ortholog mapping [3] as well as perform a GBA analysis using EGAD [4].

CoCoCoNet is free to use and available at https://milton.cshl.edu/CoCoCoNet/

## The Parameters
![param](https://github.com/johnlee4/CoCoCoNet/blob/master/figures/main.png)

**Example Settings**
  
  Choose to use either: Top 236 co-expressed Yeast genes studied by Eisen et al [5] or the top 284 co-expressed genes associated with Autism Spectrum Disorder (ASD) from the SFARI Gene database [6].

**The Species**
  
  Select the species that your genes come from. 

**Select Input method:**
  
  Allows you to choose how to load in a gene list. Currently, you can select genes from a drop down list, paste a comma separated list, or upload a file with genes listed in new lines. 


**Priority vs Meta**
  
  Selecting Priority will only use a subset of the gene set filtered on expresionality across experiments.
  
  Meta on the otherhand will build the network using all available genes in the gene set.
  

**Using genes ...**
  
  "That I provide only" will construct the network using only selected genes.
  
  "That I provide plus __ more" will select the most closely related genes not in the provided set. Here we define the "relation" as having the largest weighted degree of edges connected to the provided genes.
  
  
## Generating the results

Once your genes have been properly loaded, the "Generate Results" and "Clear Results" options will appear. Selecting "Generate Results" will display the network, the distribution of Co-expression values, and a sliding threshold bar that allows the user to filter the network to include only connections greater than this threshold. The user also has the option to highlight genes along with their direct connections or highlight genes with specified enriched GO terms. Using the example setting of "Highly Co-expressed Yeast Genes" and selecting genes with GO term "translation initiation" gives the folowwing network.
![yeast](https://github.com/johnlee4/CoCoCoNet/blob/master/figures/yeast.png)


## Ortholog Mapped genes

The next section allows the user to input a second species to compare to the first. Doing so will select genes of the second species with a 1 to 1 ortholog of genes in the provided gene set. After selection, "Generate" and "Clear Section" buttons will appear where selecting "Generate" will again display the network, the co-expression value distribution, and a sliding threshold bar. Again the user has the option to highlight genes along with its nearest neighbors or highlight genes by GO term.  
![C_elegans](https://github.com/johnlee4/CoCoCoNet/blob/master/figures/roundworm.png)


## Extending Guilt by Association by Degree (EGAD)
The final section allows the user to perform Guilt by Association (GBA) analysis on the input genes and the corresponding 1 to 1 ortholog using EGAD [4]. EGAD analyzes enriched GO terms of each species using either neighbor voting or by node degree and reports the corresponding area under the receiver operating curve (AUROC) or the precision recall curve (AUPRC) across 3 cross validation folds. 

## Downloadables
![download](https://github.com/johnlee4/CoCoCoNet/blob/master/figures/download.png)

Data used to generate results can be downloaded at [ftp://milton.cshl.edu/data](ftp://milton.cshl.edu/data). User results can also be downloaded at every step by toggling the "Download" option.

## Browser Support

| OS | Version | Chrome | FireFox | Microsoft  Edge | Safari | 
| ----- | ----- | ----- | ----- | -----  | ----- | 
| Linux | Ubuntu | 79.0.3945 | 71.0 | N/A | N/A | 
| MacOS | Catalina | 79.0.3945 | 71.0 | N/A | 10.1.2 | 
| Windows | 10 | 79.0.3945 | 71.0 | 44.18362.449.0 | N/A | 


## References

[1] Leinonen, R., Sugawara, H., Shumway, M. on behalf of the International Nucleotide Sequence Database Collaboration (2011) The Sequence Read Archive, _Nucleic Acids Research_, __(39)__, suppl_1, D19–D21, https://doi.org/10.1093/nar/gkq1019

[2] Ballouz, S., Verleyen, W., Gillis, J. (2015) Guidance for RNA-seq co-expression network construction and analysis: safety in numbers, _Bioinformatics_, __(31)__, 13, 2123–2130, https://doi.org/10.1093/bioinformatics/btv118

[3] Kriventseva, E. V., Kuznetsov, D., Tegenfeldt, F., Manni, M., Dias, R., Simão, F. A., Zdobnov, E. M. (2019) OrthoDB v10: sampling the diversity of animal, plant, fungal, protist, bacterial and viral genomes for evolutionary and functional annotations of orthologs, _Nucleic Acids Research_, __(47)__, D1, D807–D811, https://doi.org/10.1093/nar/gky1053

[4] Ballouz, S., Weber, M., Pavlidis, P., Gillis, J. (2017) EGAD: ultra-fast functional analysis of gene networks, _Bioinformatics_, __(33)__, 4, 612–614, https://doi.org/10.1093/bioinformatics/btw695

[5] Eisen, M. B., Spellman, P. T., Brown, P. O., Botstein, D. (1998) Cluster analysis and display of genome-wide expression patterns, _Proceedings of the National Academy of Sciences_, __(95)__, 25, 14863-14868; https://www.pnas.org/content/95/25/14863

[6] Banerjee-Basu, S., Packer, A. (2010) SFARI Gene: an evolving database for the autism research community, _Disease Models & Mechanisms_, __3__: 133-135; https://dmm.biologists.org/content/3/3-4/133#ref-1

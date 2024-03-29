# A continually expanding collection of RNA-seq tools

These notes are not intended to be comprehensive. They include notes about methods, packages and tools I would like to explore. For a comprehensive overview of the subject, consider [other bioinformatics resources](https://github.com/mdozmorov/Bioinformatics_notes) and [collections of links to various resources](https://github.com/mdozmorov/MDmisc_notes). Issues with suggestions and pull requests are welcome!

# Table of content

* [Pipelines](#pipelines)
  * [Preprocessing](#preprocessing)
  * [Analysis](#analysis)
* [Quality control](#quality-control)
* [Clustering](#clustering)
* [Differential expression](#differential-expression)
* [Functional enrichment](#functional-enrichment)
* [Non-canonical RNAs](#non-canonical-rnas)
  * [Alternative splicing](#alternative-splicing)
  * [miRNAs](#mirnas)
  * [lncRNAs](#lncrnas)
  * [circRNAs](#circrnas)
  * [Gene fusion](#gene-fusion)
  * [Isoforms](isoforms)
* [Structural variations](#structural-variations)
* [Networks](#networks)
* [Motif enrichment](#motif-enrtichment)
* [Classification](#classification)
* [Visualization](#visualization)
* [Data](#data)
* [Misc](#misc)

## Pipelines

### Preprocessing

### Analysis

- `3D_RNA-seq` - R package and Shiny app, and Docker image, for differential expression, differential alternative splicing, and differential Transcript Usage. Two- and mutliple group analysis, time course. Input - Salmon/Kallisto transcript quantification files, or .csv. Diagnostic plots, PCA, batch removal using RUVseq, limma-voom for differential expression, iso-kTSP and TSIS for isoform switching between groups and in time course, respectively. Heatmaps, barplots, volcano plots, Venn diagrams. 3D stands for three days. Web: https://ics.hutton.ac.uk/3drnaseq/,  Manual: https://github.com/wyguo/ThreeDRNAseq/blob/master/vignettes/user_manuals/3D_RNA-seq_App_manual.md,  GitHub: https://github.com/wyguo/ThreeDRNAseq
    - Guo, Wenbin, Nikoleta Tzioutziou, Gordon Stephen, Iain Milne, Cristiane Calixto, Robbie Waugh, John WS Brown, and Runxuan Zhang. “3D RNA-Seq - a Powerful and Flexible Tool for Rapid and Accurate Differential Expression and Alternative Splicing Analysis of RNA-Seq Data for Biologists.” Preprint. Bioinformatics, May 31, 2019. https://doi.org/10.1101/656686.

- `DrEdGE` - Differential Expression Gene Explorer, Takes in a table of transcript abundance counts, experimental design, other input can be generated in R. Plot, table, heatmap visualization options. Web: http://dredge.bio.unc.edu/ , GitHub: https://github.com/ptgolden/dredge
    - Tintori, Sophia C, Patrick Golden, and Bob Goldstein. “Differential Expression Gene Explorer (DrEdGE): A Tool for Generating Interactive Online Data Visualizations for Exploration of Quantitative Transcript Abundance Datasets.” Preprint. Genomics, April 25, 2019. https://doi.org/10.1101/618439.

- `Phantasus` - interactive exploratory analyses of genomic data, from clustering, PCA, to enrichment, network, and pathway analyses. R package and Docker  (link: https://github.com/ctlab/phantasus) github.com/ctlab/phantasus. Works on user data, ARCHS4, TCGA (link: https://genome.ifmo.ru/phantasus/) genome.ifmo.ru/phantasus/

## Quality control

- `MultiQC` - Summarization and visualization QC results for multiple samples in one report. Recognizes multiple QC tools. http://multiqc.info/

- `ngsReports` - An R Package for managing FastQC reports and other NGS related log files. https://github.com/UofABioinformaticsHub/ngsReports, http://biorxiv.org/content/early/2018/05/02/313148.abstract

- `sickle` - A windowed adaptive trimming tool for FASTQ files using quality. Post-adapter trimming step. https://github.com/najoshi/sickle

- `fastqc` - an R package for quality control (QC) of short read fastq files, analog of the [original FASTQC](http://www.bioinformatics.babraham.ac.uk/projects/fastqc/), https://github.com/Malarkey73/fastqc

- `FastQt` - FastQC port to Qt5: A quality control tool for high throughput sequence data. https://github.com/labsquare/FastQt

- `fastqcheck` - Generate statistics on and validate fastq files. https://github.com/VertebrateResequencing/fastqcheck

## Clustering

- `clust` - Python package for identification of consistently coexpressed clusters of genes, within and across datasets. Consensus clustering principle. ~50% of genes do not cluster well and thus shouldn't be considered. Compared with seven tools (cross-clustering, k-means, SOMs, MCL, HC, Click, WGCNA) using seven different cluster validation metrics. Outperforms all, produces more focused and significant functional enrichment results. https://github.com/BaselAbujamous/clust
    - Abu-Jamous, Basel, and Steven Kelly. “Clust: Automatic Extraction of Optimal Co-Expressed Gene Clusters from Gene Expression Data.” Genome Biology 19, no. 1 (December 2018). https://doi.org/10.1186/s13059-018-1536-8.


## Differential expression

- `Degust` -  interactive RNA-seq analysis, RNA-seq exploration, analysis and visualisation. http://degust.erc.monash.edu/

- `ideal` - Interactive Differential Expression AnaLysis. http://bioconductor.org/packages/release/bioc/html/ideal.html

- Publication-ready volcano plots with enhanced colouring and labeling. https://github.com/kevinblighe/EnhancedVolcano

- `ALDEx` - differential abundance analysis of compositional data. ANOVA-like approach, partitioning within-condition to between-condition variation. Uses a Dirichlet-multinomial model to infer abundance from counts. Methods description for transforming proportional data into independent components.  https://bioconductor.org/packages/release/bioc/html/ALDEx2.html
    - Fernandes, Andrew D., Jean M. Macklaim, Thomas G. Linn, Gregor Reid, and Gregory B. Gloor. “ANOVA-like Differential Expression (ALDEx) Analysis for Mixed Population RNA-Seq.” PloS One 8, no. 7 (2013): e67019. https://doi.org/10.1371/journal.pone.0067019.


## Functional enrichment

- `CEMiTool` - gene co-expression analysis, reimplements WGCNA, includes selection of a soft-thresholding power using Cauchi distribution, gene enrichment analysis and, optionally, PPI network. Good overview of WGCNA algorithm. https://bioconductor.org/packages/release/bioc/html/CEMiTool.html
    - Russo, Pedro S. T., Gustavo R. Ferreira, Lucas E. Cardozo, Matheus C. Bürger, Raul Arias-Carrasco, Sandra R. Maruyama, Thiago D. C. Hirata, et al. “CEMiTool: A Bioconductor Package for Performing Comprehensive Modular Co-Expression Analyses.” BMC Bioinformatics 19, no. 1 (20 2018): 56. https://doi.org/10.1186/s12859-018-2053-1.

- `EnrichmentBrowser` - R package for microarray/RNA-seq normalization, ID mapping, differential analysis, functional enrichment (many methods) and network analyses and visualization. https://bioconductor.org/packages/release/bioc/html/EnrichmentBrowser.html
     - Geistlinger, Ludwig, Gergely Csaba, and Ralf Zimmer. “Bioconductor’s EnrichmentBrowser: Seamless Navigation through Combined Results of Set- & Network-Based Enrichment Analysis.” BMC Bioinformatics 17 (January 20, 2016): 45. https://doi.org/10.1186/s12859-016-0884-1.

- `data_analysis_portals.xlsx` - 25 data analysis portals, from the Metascape paper. [Source](https://static-content.springer.com/esm/art%3A10.1038%2Fs41467-019-09234-6/MediaObjects/41467_2019_9234_MOESM3_ESM.xlsx)

- `gProfileR` - enrichment of gene lists, from GO to KEGG and others, organism-specific, ortholog conversion

- `Metascape` - multi-gene lists functional analysis, auto gene ID recognition, >40 databases. http://metascape.org/gp/index.html#/main/step1
    - Zhou, Yingyao, Bin Zhou, Lars Pache, Max Chang, Alireza Hadj Khodabakhshi, Olga Tanaseichuk, Christopher Benner, and Sumit K. Chanda. “Metascape Provides a Biologist-Oriented Resource for the Analysis of Systems-Level Datasets.” Nature Communications 10, no. 1 (December 2019): 1523. https://doi.org/10.1038/s41467-019-09234-6.

- Positional Gene Enrichment analysis of gene sets for high resolution identification of overrepresented chromosomal regions.  http://silico.biotoul.fr/pge/
    - De Preter, K., Barriot, R., Speleman, F., Vandesompele, J., Moreau, Y., 2008, Nucleic Acids Res. https://academic.oup.com/nar/article/36/7/e43/2410597


## Non-canonical RNAs

### Alternative splicing

- `MAJIQ` - local splicing variation analysis. Detects canonical and alternative splicing events. Quantifies as Percent Selected In (PSI). Differential splicing as delta PSI. Visualization using VOILA package. Python 3. https://majiq.biociphers.org/
    - Vaquero-Garcia, Jorge, Alejandro Barrera, Matthew R. Gazzara, Juan González-Vallinas, Nicholas F. Lahens, John B. Hogenesch, Kristen W. Lynch, and Yoseph Barash. “A New View of Transcriptome Complexity and Regulation through the Lens of Local Splicing Variations.” ELife 5 (February 1, 2016): e11752. https://doi.org/10.7554/eLife.11752.

- `MISO` (Mixture-of-Isoforms) is a probabilistic framework that quantitates the expression level of alternatively spliced genes from RNA-Seq data, and identifies differentially regulated isoforms or exons across samples. - By modeling the generative process by which reads are produced from isoforms in RNA-Seq, the MISO model uses Bayesian inference to compute the probability that a read originated from a particular isoform.- MISO treats the expression level of a set of isoforms as a random variable and estimates a distribution over the values of this variable. - The estimation algorithm is based on sampling, and falls in the family of techniques known as Markov Chain Monte Carlo (“MCMC”). https://miso.readthedocs.io/en/fastmiso/
    - Katz, Yarden, Eric T. Wang, Edoardo M. Airoldi, and Christopher B. Burge. “Analysis and Design of RNA Sequencing Experiments for Identifying Isoform Regulation.” Nature Methods 7, no. 12 (December 2010): 1009–15. https://doi.org/10.1038/nmeth.1528.

- `RegTools` - integration of somatic variants from DNA-seq and splice junctions from RNA-seq data to identify variants causing aberrant splicing in cancer. https://regtools.readthedocs.io/en/latest/
    - Feng, Yang-Yang, Avinash Ramu, Kelsy C Cotto, Zachary L Skidmore, Jason Kunisaki, Donald F Conrad, Yiing Lin, et al. “RegTools: Integrated Analysis of Genomic and Transcriptomic Data for Discovery of Splicing Variants in Cancer,” November 25, 2018. https://doi.org/10.1101/436634.

- `rMATS` alternative splicing detection tool. Using paired samples.RNA-seq depth and alternative splicing power - 200M reads minimum. http://rnaseq-mats.sourceforge.net/
    - Shen, Shihao, Juw Won Park, Zhi-xiang Lu, Lan Lin, Michael D. Henry, Ying Nian Wu, Qing Zhou, and Yi Xing. “RMATS: Robust and Flexible Detection of Differential Alternative Splicing from Replicate RNA-Seq Data.” Proceedings of the National Academy of Sciences of the United States of America 111, no. 51 (December 23, 2014): E5593-5601. https://doi.org/10.1073/pnas.1419161111.

- `tappAS` - functional impact of alternative splicing. Input - transcript-level count matrix. http://tappas.org/

- `vast-tools` - A toolset for profiling alternative splicing events in RNA-Seq data. https://github.com/vastgroup/vast-tools
    - Irimia, Manuel, Robert J. Weatheritt, Jonathan D. Ellis, Neelroop N. Parikshak, Thomas Gonatopoulos-Pournatzis, Mariana Babor, Mathieu Quesnel-Vallières, et al. “A Highly Conserved Program of Neuronal Microexons Is Misregulated in Autistic Brains.” Cell 159, no. 7 (December 18, 2014): 1511–23. https://doi.org/10.1016/j.cell.2014.11.035.

### miRNAs

- `miRDB` - database for miRNA target prediction and functional annotations. The targets were predicted by MirTarget from RNA-seq and CLIP-seq data. Five species: human, mouse, rat, dog and chicken. Custom target prediction. Cell line-specific. Integrative analysis of target prediction and Gene Ontology data. http://mirdb.org
    - Chen, Yuhao, and Xiaowei Wang. “MiRDB: An Online Database for Prediction of Functional MicroRNA Targets.” Nucleic Acids Research, August 31, 2019, gkz757. https://doi.org/10.1093/nar/gkz757.

- `miRsponge` - identification and analysis of miRNA sponge interaction networks and modules. Seven methods for miRNA sponge interaction detection (miRHomology, pc, sppc, hermes, ppc, muTaME, and cernia), and integrative method, description of each method. Four module detection methods (FN, MCL, LINKCOMM, MCODE), description of each. Enrichment analyses - disease (DO, DisGeNet, Network of Cancer Genes), functions (GO, KEGG, REACTOME). Survival analysis.
    - Zhang, Junpeng, Lin Liu, Taosheng Xu, Yong Xie, Chunwen Zhao, Jiuyong Li, and Thuc Duy Le. “MiRsponge: An R/Bioconductor Package for the Identification and Analysis of MiRNA Sponge Interaction Networks and Modules.” BioRxiv, January 1, 2018, 507749. https://doi.org/10.1101/507749.

- `MirGeneDB` - standardized microRNA database, 1288 microRNA families across 45 species. Downloadable, FASTA, GFF, BED files. Nomenclature refs 19, 20. http://mirgenedb.org/
    - Fromm, Bastian, Diana Domanska, Eirik Hoye, Vladimir Ovchinnikov, Wenjing Kang, Ernesto Aparicio-Puerta, Morten Johansen, et al. “MirGeneDB 2.0: The Metazoan MicroRNA Complement.” BioRxiv, August 13, 2019. https://doi.org/10.1101/258749.


### lncRNAs

- `lncRNAKB` - database of long noncoding RNAs. lncRNAs are typically less conserved, expressed low on average and highly tissue-specific. Combines six resources (CHESS, LNCipedia, NONCODE, FANTOM, MiTranscriptome, BIGTranscriptome). Information about tissue-specific expression, eQTL, WGCNA co-expression to predict functions in a tissue-specific manner, random forest prediction of protein-coding score. Data: GTF gene annotation, tissue-specific expression (TPM, counts, eQTL). http://psychiatry.som.jhmi.edu/lncrnakb/, https://www.rna-seqblog.com/lncrnakb-a-comprehensive-knowledgebase-of-long-non-coding-rnas/
    - Seifuddin, Fayaz, Komudi Singh, Abhilash Suresh, Yun-Ching Chen, Vijender Chaitankar, Ilker Tunc, Xiangbo Ruan, et al. “LncRNAKB: A Comprehensive Knowledgebase of Long Non-Coding RNAs.” Preprint. Bioinformatics, June 13, 2019. https://doi.org/10.1101/669994.


### circRNAs

- `CIRCpedia` database of cornRNAs from human, mouse, and some model organisms. Ribo-, poly(A)-, RNAse R methods for enriching for circRNAs. http://www.picb.ac.cn/rnomics/circpedia/. `CIRCexplorer2` for the analysis of such experiments, https://circexplorer2.readthedocs.io/en/latest/
    - Zhang et al., “Diverse Alternative Back-Splicing and Alternative Splicing Landscape of Circular RNAs.”

### Gene fusion

- `FusionScan` – prediction of fusion genes from RNA-Seq data. [RNA-seq blog post](https://www.rna-seqblog.com/fusionscan-prediction-of-fusion-genes-from-rna-seq-data/), http://fusionscan.ewha.ac.kr/, https://github.com/iamlife/FusionScan

- `Arriba` - Fast and accurate gene fusion detection from RNA-Seq data. https://github.com/suhrig/arriba

- `FuSeq` - fast fusion detection. Compared with FusionMap, TRUP, TopHat-Fusion, JAFFA, SOAPfuse.  https://github.com/nghiavtr/FuSeq
    - Vu, Trung Nghia, Wenjiang Deng, Quang Thinh Trac, Stefano Calza, Woochang Hwang, and Yudi Pawitan. “A Fast Detection of Fusion Genes from Paired-End RNA-Seq Data.” BMC Genomics 19, no. 1 (December 2018). https://doi.org/10.1186/s12864-018-5156-1.

- `GeneFuse` - Gene fusion detection and visualization. https://github.com/OpenGene/GeneFuse

- `EricScript` is a computational framework for the discovery of gene fusions in paired end RNA-seq data, https://sites.google.com/site/bioericscript/

### Isoforms

- `IsoformSwitchAnalyzeR` - An R package to Identify, Annotate and Visualize Alternative Splicing and Isoform Switches with Functional Consequences (from RNA-seq data). https://bioconductor.org/packages/release/bioc/html/IsoformSwitchAnalyzeR.html
    - Vitting-Seerup, Kristoffer, and Albin Sandelin. “IsoformSwitchAnalyzeR: Analysis of Changes in Genome-Wide Patterns of Alternative Splicing and Its Functional Consequences.” Edited by Bonnie Berger. Bioinformatics, April 15, 2019. https://doi.org/10.1093/bioinformatics/btz247.
    - Vitting-Seerup, Kristoffer, and Albin Sandelin. “The Landscape of Isoform Switches in Human Cancers.” Molecular Cancer Research 15, no. 9 (September 2017): 1206–20. https://doi.org/10.1158/1541-7786.MCR-16-0459. - Isoform switching analysis of TCGA data, tumor vs. normal. Consequences, survival prediction. Supplementary data has isoform switching analysis results for all TCGA cancers, https://mcr.aacrjournals.org/content/15/9/1206.figures-only

## Structural variations

- `SQUID` - transcriptomic structural variation caller. Genome segment graph, then rearrange segments so that as many read alignments as possible are concordant with the rearranged sequence. Compared with MUMmer3, DELLY2, LUMPY in simulated settings, and with SOAPfuse, deFuse, FusionCatcher, JAFFA, INTEGRATE tools using real data. https://github.com/Kingsford-Group/squid
    - Ma, Cong, Mingfu Shao, and Carl Kingsford. “SQUID: Transcriptomic Structural Variation Detection from RNA-Seq.” Genome Biology 19, no. 1 (12 2018): 52. https://doi.org/10.1186/s13059-018-1421-5.

- `transindel` - Indel caller for DNA-seq or RNA-seq, https://github.com/cauyrd/transIndel


## Networks

- `GENIE3` - random forest regression detection of gene modules. Input - expression matrix, output - gene x gene square co-regulation matrix. https://github.com/aertslab/GENIE3


## Motif enrichment

- `RcisTarget` - finding enriched motifs in cis-regulatory regions in a gene list. https://github.com/aertslab/RcisTarget


## Classification

- `MLSeq` - Machine learning interface for RNA-Seq data. https://www.bioconductor.org/packages/release/bioc/html/MLSeq.html, Zararsız, Gökmen, Dincer Goksuluk, Selcuk Korkmaz, Vahap Eldem, Gozde Erturk Zararsiz, Izzet Parug Duru, and Ahmet Ozturk. “A Comprehensive Simulation Study on Classification of RNA-Seq Data.” Edited by Christian Schönbach. PLOS ONE 12, no. 8 (August 23, 2017): e0182507. https://doi.org/10.1371/journal.pone.0182507.


## Visualization

- `chromoMap` - Interactive Visualization and Mapping of Human Chromosomes, https://cran.r-project.org/web/packages/chromoMap/index.html

- genomation: a toolkit for annotation and visualization of genomic data. https://bioconductor.org/packages/devel/bioc/vignettes/genomation/inst/doc/GenomationManual.html

- `karyoploteR` - An R/Bioconductor package to plot arbitrary data along the genome. https://github.com/bernatgel/karyoploteR

- `pcaExplorer` - Interactive Visualization of RNA-seq Data Using a Principal Components Approach. https://bioconductor.org/packages/release/bioc/html/pcaExplorer.html

- `WIlsON` - Web-based Interactive Omics VisualizatioN, accepts, text files, SummarizedExperiment datasets. 


## Data

- `cBioPortalData` - cBioPortal data as MultiAssayExperiment objects. https://github.com/waldronlab/cBioPortalData

- `curatedTCGAData` - Curated Data From The Cancer Genome Atlas (TCGA) as MultiAssayExperiment objects. https://github.com/waldronlab/curatedTCGAData

- `ARCHS4` - Massive Mining of Publicly Available RNA-seq Data from Human and Mouse. http://amp.pharm.mssm.edu/archs4/download.html

- `PINS` - A novel method for data integration and disease subtyping. http://www.cs.wayne.edu/tinnguyen/PINS/PINS.html

- `recount2` - https://bioconductor.org/help/workflows/recountWorkflow/

- `GREIN` - re-analysis of RNA-seq datasets from GEO. Download processed data, visualization, power analysis, differential expression, functional enrichment analysis, connectivity analysis with LINCS L1000 data. Web-app, http://www.ilincs.org/apps/grein/, source code, https://github.com/uc-bd2k/grein, Docker image, https://hub.docker.com/r/ucbd2k/grein/
    - Al Mahi, Naim, Mehdi Fazel Najafabadi, Marcin Pilarczyk, Michal Kouril, and Mario Medvedovic. “GREIN: An Interactive Web Platform for Re-Analyzing GEO RNA-Seq Data,” October 27, 2018. https://doi.org/10.1101/326223.

- `DEE2` - Digital Expression Explorer - gene- and transcript-level processed data from multiple organisms, amenable for downstream analysis in R etc. `getDEE2` R package to get the data, https://github.com/markziemann/dee2/blob/master/AccessDEEfromR.md. Web interface: http://dee2.io
    - Ziemann, Mark, Antony Kaspi, and Assam El-Osta. “Digital Expression Explorer 2: A Repository of Uniformly Processed RNA Sequencing Data.” GigaScience 8, no. 4 (April 1, 2019). https://doi.org/10.1093/gigascience/giz022.


## Misc

- `BioJupies` - analysis of GEO/GTEx data or your own gene expression table/FASTQ in autogenerated Jupyter notebook. Rich set of tools for EDA (PCA, Clustergrammer, Library size analysis), Differential expression analysis (Volcano, MA plots), Enrichment analysis (Enrichr, GO, Pathway, TF, Kinase, miRNA enrichments), L1000 signatures. Best suited for two-group analysis. Includes Methods for the selected tools. https://amp.pharm.mssm.edu/biojupies/

- `HGNChelper` - Handy Functions for Working with HGNC Gene Symbols and Affymetrix Probeset Identifiers. https://cran.r-project.org/web/packages/HGNChelper/index.html

- `tximport` - importing transcript abundance datasets from Salmon, Sailfish, kallisto, RSEM, and differential analysis

- `rpkmforgenes` - a Python script for calculating gene expression for RNA-Seq data. http://sandberg.cmb.ki.se/media/data/rnaseq/instructions-rpkmforgenes.html

- Python interface to access reference genome features (such as genes, transcripts, and exons) from Ensembl, https://github.com/openvax/pyensembl

- `TPMcalculator` - converts gene counts to TPM using transcript information from a GTF file. TPM vs. FPKM correlation for validation. C/C++ command line tool, Docker image, CWL workflow. https://github.com/ncbi/TPMCalculator
    - Vera Alvarez, Roberto, Lorinc Sandor Pongor, Leonardo Mariño-Ramírez, and David Landsman. “TPMCalculator: One-Step Software to Quantify MRNA Abundance of Genomic Features.” Edited by Bonnie Berger. Bioinformatics 35, no. 11 (June 1, 2019): 1960–62. https://doi.org/10.1093/bioinformatics/bty896.


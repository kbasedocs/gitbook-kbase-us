---
description: Some of the tools in KBase available for expression analysis
---

# Expression and Transcriptomics

KBase offers a powerful suite of [expression analysis Apps](https://kbase.us/applist/#Expression). Starting with short reads, you can use the tool suite to analyze transcriptomic data in a . You can also compare the expression data with the flux when studying metabolic models in KBase and identify pathways where expression and flux agree or conflict.

KBase offers a powerful suite of [expression analysis tools](https://kbase.us/applist/#Expression). Starting with short reads, you can use the tool suite to assemble, quantify long transcripts, and identify differentially expressed genes. You can also compare the expression data with the flux when studying metabolic models in KBase and identify pathways where expression and flux agree or conflict

### **Reads Management**

* [Assess Read Quality with FastQC](https://kbase.us/applist/apps/kb\_fastqc/runFastQC/release) – Read quality analysis
* [Cutadapt](https://kbase.us/applist/apps/kb\_cutadapt/remove\_adapters/release) – Remove adapter sequences from reads
* [Trim Reads with Trimmomatic](https://kbase.us/applist/apps/kb\_trimmomatic/run\_trimmomatic/release) – Read trimming and removing Illumina adapters

### **Alignment**

* [Align Reads using Bowtie2](https://kbase.us/applist/apps/kb\_Bowtie2/align\_reads\_using\_bowtie2/release) – aligns the sequencing reads for a set of two or more samples to long reference sequences of a prokaryotic genome using Bowtie2 and outputs a set of alignments for the given sample set in BAM format.
* [Align Reads using TopHat2](https://kbase.us/applist/apps/kb\_tophat2/align\_reads\_using\_tophat2/release) – aligns the sequencing reads for a set of two or more samples to an eukaryotic genome using TopHat2 in order to identify splice junctions between exons with the help of Bowtie2 mapping program.
* [Align Reads using HISAT2](https://kbase.us/applist/apps/kb\_hisat2/align\_reads\_using\_hisat2/release) – aligns the sequencing reads for a set of two or more samples to long reference sequences of a genome using HISAT2 and outputs a set of alignments for the given sample set or reads set in BAM format.
* [Align Reads using STAR](https://narrative.kbase.us/#catalog/apps/STAR/align\_reads\_using\_STAR/beta) – aligns the sequencing reads of a single or a set of two (paired end) reads to long reference sequences of a prokaryotic genome using the STAR alignment program.

### **Assembly**

* [Assemble Transcripts using Cufflinks](https://kbase.us/applist/apps/kb\_cufflinks/assemble\_transcripts\_using\_cufflinks/release) – assembles transcripts for a given sample or a sample set using Cufflinks so that you can view the relative abundances of the assembled transcripts in a histogram, obtained as output from Cufflinks.
* [Assemble Transcripts using StringTie](https://kbase.us/applist/apps/kb\_stringtie/run\_stringtie/release) – assembles transcripts for a given sample or a sample set using StringTie so that you can view the relative abundances of the assembled transcripts in a histogram.

### **Differential Expression**&#x20;

* [Identify Differential Expression using Cuffdiff](https://kbase.us/applist/apps/kb\_cufflinks/run\_Cuffdiff/release) – uses the Cufflinks transcripts for two or more samples to calculate gene and transcript levels in more than one condition and finds significant changes in the expression levels.
* [Create Differential Expression Matrix using Ballgown](https://kbase.us/applist/apps/kb\_ballgown/run\_ballgown\_app/release) – uses the transcripts for two or more samples obtained from either Cufflinks or StringTie to calculate gene and transcript levels in more than one condition and finds significant changes in the expression levels.
* [Create Differential Expression Matrix using DESeq2](https://kbase.us/applist/apps/kb\_deseq/run\_DESeq2/release) – uses the transcripts for two or more samples obtained from either Cufflinks or StringTie to calculate gene and transcript levels in more than one condition and finds significant changes in the expression levels.

### Downstream Analyses

* [Filter Expression Matrix](https://kbase.us/applist/apps/CoExpression/expression\_toolkit\_filter\_expression/release) – Filter an expression matrix using either Log Odds Ratio (LOR) or ANalysis of VAriance (ANOVA) algorithms.
* [Cluster Expression Data – Hierarchical ](https://kbase.us/applist/apps/KBaseFeatureValues/expression\_toolkit\_cluster\_hierarchical/release)– Perform hierarchical clustering to group gene expression data into a dendrogram.
* [Estimate K for K-means Clustering](https://kbase.us/applist/apps/KBaseFeatureValues/expression\_toolkit\_estimate\_k/release) – Generate reasonable numbers of clusters (K) for use in the [Cluster Expression Data - K-Means](https://kbase.us/applist/apps/KBaseFeatureValues/expression\_toolkit\_cluster\_k\_means/release) App.
* [Cluster Expression Data – K-means](https://kbase.us/applist/apps/KBaseFeatureValues/expression\_toolkit\_cluster\_k\_means/release) – Perform K-means clustering to group expression data for observing and analyzing patterns of gene expression.
* [Cluster Expression Data – WGCNA](https://kbase.us/applist/apps/CoExpression/expression\_toolkit\_cluster\_WGCNA/release) – Perform weighted gene co-expression network analysis (WGCNA) to detect gene clusters and expression patterns.
* [View Interactive Heatmap](https://kbase.us/applist/apps/NarrativeViewers/view\_expression\_interactive\_heatmap/release) – display heatmap of expressed genes.&#x20;
* [View Multi-cluster Heatmap](https://kbase.us/applist/apps/CoExpression/expression\_toolkit\_view\_heatmap/release) – display multi-cluster heatmap of expressed genes.

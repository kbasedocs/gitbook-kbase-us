---
description: Some of the tools available for expression analysis
---

# Transcriptomics and Expression

![](../../.gitbook/assets/expression-1.jpg) KBase offers a powerful suite of expression analysis Apps. Starting with short reads, you can use the tool suite to assemble and quantify long transcripts, identify differentially expressed genes, cluster them and analyze them as functionally enriched modules. You can also compare the expression data with the flux when studying metabolic models in KBase and identify pathways where expression and flux agree or conflict.

### **Reads Management**

* [Assess Read Quality with FastQC](https://narrative.kbase.us/#appcatalog/app/kb_fastqc/runFastQC/release) – Read quality analysis
* [CutAdapt](https://narrative.kbase.us/#appcatalog/app/kb_cutadapt/remove_adapters/release) – Remove adapter sequences from reads
* [Trim Reads with Trimmomatic](https://narrative.kbase.us/#appcatalog/app/kb_trimmomatic/run_trimmomatic/release) – Read trimming and removing Illumina adapters

### **Reads Alignment**

* [Align Reads using Bowtie2](https://narrative.kbase.us/#appcatalog/app/KBaseRNASeq/align_reads_using_bowtie2/release) — aligns the sequencing reads for a set of two or more samples to long reference sequences of a prokaryotic genome using Bowtie2 and outputs a set of alignments for the given sample set in BAM format.
* [Align Reads using Tophat2](https://narrative.kbase.us/#appcatalog/app/KBaseRNASeq/align_reads_using_tophat/release) — aligns the sequencing reads for a set of two or more samples to an eukaryotic genome using TopHat2 in order to identify splice junctions between exons with the help of Bowtie2 mapping program.
* [Align Reads using HISAT2](https://narrative.kbase.us/#appcatalog/app/KBaseRNASeq/align_reads_using_hisat2/release) — aligns the sequencing reads for a set of two or more samples to long reference sequences of a genome using HISAT2 and outputs a set of alignments for the given sample set or reads set in BAM format.

### **Reads Assembly**

* [Assemble Transcripts using Cufflinks](https://narrative.kbase.us/#appcatalog/app/KBaseRNASeq/assemble_transcripts_with_cufflinks/release) — assembles transcripts for a given sample or a sample set using Cufflinks so that you can view the relative abundances of the assembled transcripts in a histogram, obtained as output from Cufflinks.
* [Assemble Transcripts using StringTie](https://narrative.kbase.us/#catalog/apps/KBaseRNASeq/assemble_transcripts_with_stringtie/release) — assembles transcripts for a given sample or a sample set using StringTie so that you can view the relative abundances of the assembled transcripts in a histogram.

### **Differential Expression**

* [Identify Differential Expression using Cuffdiff](https://narrative.kbase.us/#catalog/apps/KBaseRNASeq/identify_differential_expression_using_cuffdiff/release) [— ](https://narrative.kbase.us/#catalog/apps/KBaseRNASeq/identify_differential_expression_using_cuffdiff/release)uses the Cufflinks transcripts for two or more samples to calculate gene and transcript levels in more than one condition and finds significant changes in the expression levels.
* [Create Differential Expression Matrix using Ballgown](https://narrative.kbase.us/#catalog/apps/KBaseRNASeq/identify_differential_expression_using_ballgown/release) [— ](https://narrative.kbase.us/#catalog/apps/KBaseRNASeq/identify_differential_expression_using_ballgown/release)uses the transcripts for two or more samples obtained from either Cufflinks or StringTie to calculate gene and transcript levels in more than one condition and finds significant changes in the expression levels.
* [Create Differential Expression Matrix using DESeq2](https://narrative.kbase.us/#catalog/apps/kb_deseq/run_DESeq2/release) [— ](https://narrative.kbase.us/#catalog/apps/kb_deseq/run_DESeq2/release)uses the transcripts for two or more samples obtained from either Cufflinks or StringTie to calculate gene and transcript levels in more than one condition and finds significant changes in the expression levels.
* [Filter Expression Matrix](https://narrative.kbase.us/#catalog/apps/CoExpression/expression_toolkit_filter_expression/release) [— ](https://narrative.kbase.us/#catalog/apps/CoExpression/expression_toolkit_filter_expression/release)Filter an expression matrix using either Log Odds Ratio \(LOR\) or ANalysis of VAriance \(ANOVA\) algorithms.
* [Cluster Expression Data – Hierarchical ](https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_cluster_hierarchical/release)[— ](https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_cluster_hierarchical/release)Perform hierarchical clustering to group gene expression data into a dendrogram.
* [Estimate K for K-means Clustering](https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_estimate_k/release) [— ](https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_estimate_k/release)Generate reasonable numbers of clusters \(K\) for use in the [Cluster Expression Data - K-Means](https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_cluster_k_means/release) App.
* [Cluster Expression Data – K-means](https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_cluster_k_means/release) [— ](https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_cluster_k_means/release)Perform K-means clustering to group expression data for observing and analyzing patterns of gene expression.
* [Cluster Expression Data – WGCNA](https://narrative.kbase.us/#catalog/apps/CoExpression/expression_toolkit_cluster_WGCNA/release) [— ](https://narrative.kbase.us/#catalog/apps/CoExpression/expression_toolkit_cluster_WGCNA/release)Perform weighted gene co-expression network analysis \(WGCNA\) to detect gene clusters and expression patterns.
* [View Interactive Heatmap](https://narrative.kbase.us/#catalog/apps/kb_cummerbund/view_expression_interactive_heatmap/release) [— ](https://narrative.kbase.us/#catalog/apps/kb_cummerbund/view_expression_interactive_heatmap/release)display heatmap of expressed genes. 
* [View Multi-cluster Heatmap](https://narrative.kbase.us/#catalog/apps/CoExpression/expression_toolkit_view_heatmap/release) [—](https://narrative.kbase.us/#catalog/apps/CoExpression/expression_toolkit_view_heatmap/release) display multi-cluster heatmap of expressed genes.

### \*\*\*\*


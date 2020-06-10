# Transcriptomics and Expression Analysis in KBase

![](../../.gitbook/assets/expression-1.jpg) KBase offers a powerful suite of expression analysis tools. Starting with short reads, you can use the tool suite to assemble and quantify long transcripts, identify differentially expressed genes, cluster them and analyze them as functionally enriched modules. You can also compare the expression data with the flux when studying metabolic models in KBase and identify pathways where expression and flux agree or conflict.

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

### **RNA-Seq Analysis Tutorials**

* [RNA-seq Analysis using New Tuxedo Suite \(Arabidopsis\)](https://narrative.kbase.us/narrative/ws.19391.obj.1): 
* [RNA-seq Analysis \(E. coli\)](https://narrative.kbase.us/narrative/ws.50093.obj.1)

#### Prerequisites for RNA-seq Analysis

We support the popular Tuxedo suite of tools \(original and new\) for RNA-seq analysis. As a result, KBase requires reference genome to guide the analysis of short reads. 

1. **Import Genome:** Use the [_Public_ tab in **Data Panel**](../../getting-started/narrative-user-guide/add-data-to-your-narrative.md) ****to choose the reference genome from KBase’s public data. If it’s not available, you can use the __[_Import_ tab in **Data Panel**](../../getting-started/narrative-user-guide/add-data-to-your-narrative.md) ****to import the genome of interest to your Narrative.
2. **Import Short Reads:** Use the Import tab or any of the reads uploader apps from the ****[**Apps Panel**](../../getting-started/narrative-user-guide/browse-kbase-analysis-tools.md) to import the short reads from your experiment into your Narrative. Example reads are also available from the __[_Public_ tab](../../getting-started/narrative-user-guide/add-data-to-your-narrative.md). The reads must be a set of single-end, paired-end, or interleaved paired-end reads in FASTA, FASTQ, or SRA format.
3. **Create Sample Set:** Run the [Create RNA-seq Sample Set](https://narrative.kbase.us/#catalog/apps/KBaseRNASeq/describe_rnaseq_experiment/release) App to group together your reads into an RNA-seq sample set with associated experimental metadata so that you can easily and efficiently run the RNA-seq Apps in batch mode wherever appropriate.
4. **QC Sample Set:** Run [FASTQC](https://narrative.kbase.us/#appcatalog/app/kb_fastqc/runFastQC/release) to assess the read quality of the reads set from the previous step and if needed, run [Trimmomatic](https://narrative.kbase.us/#appcatalog/app/kb_trimmomatic/run_trimmomatic/release), [Cutadapt](https://narrative.kbase.us/#appcatalog/app/kb_cutadapt/remove_adapters/release), or [PRINSEQ](https://narrative.kbase.us/#appcatalog/app/kb_PRINSEQ/execReadLibraryPRINSEQ/release) to pre-process or filter the reads before starting RNA-seq analysis.

#### RNA-seq Analysis

The RNA-seq pipeline in KBase is modular and consists of three steps. You can pick any of the multiple Apps available for a given step depending on your preference or individual characteristics of the App.

1. **Read Alignment:** Run the [BowTie2](https://narrative.kbase.us/#appcatalog/app/kb_Bowtie2/align_reads_using_bowtie2/release) app or the splice-aware [TopHat2](https://narrative.kbase.us/#catalog/apps/kb_tophat2/align_reads_using_tophat2/release), [HISAT2](https://narrative.kbase.us/#catalog/apps/kb_hisat2/align_reads_using_hisat2/release), or [STAR](https://narrative.kbase.us/#catalog/apps/STAR/align_reads_using_STAR/beta) apps to map short reads to the reference genome. The output is a set of BAM alignments and Qualimap report. You can download the alignment output object generated by aligner Apps for further analysis.
2. **Transcriptome Assembly and Quantification:** Run the [Cufflinks](https://narrative.kbase.us/#catalog/apps/kb_cufflinks/assemble_transcripts_using_cufflinks/release) or [StringTie](https://narrative.kbase.us/#catalog/apps/kb_stringtie/run_stringtie/release) App on the read alignments from the previous step to generate and assemble full-length transcripts and quantify transcripts and genes as appropriate. You can view downloadable normalized full expression matrices in FPKM \(fragments per kilobase of exon model per million mapped reads\) and TPM \(transcripts per million\).
3. **Differential Gene Expression:** Run the [Cuffdiff](https://narrative.kbase.us/#catalog/apps/kb_cufflinks/run_Cuffdiff/release) or [Ballgown](https://narrative.kbase.us/#catalog/apps/kb_ballgown/run_ballgown_app/release) or [DESeq2](https://narrative.kbase.us/#catalog/apps/kb_deseq/run_DESeq2/release) App to generate gene or transcript level differential expression based on the quantification from the previous step. Run [Create Feature Set/Filtered Expression Matrix From Differential Expression](https://narrative.kbase.us/#appcatalog/app/FeatureSetUtils/upload_featureset_from_diff_expr/release) after selecting appropriate q-value and fold change cutoffs as input parameters for the filtering of the differential gene expression.

#### Downstream Expression Analysis

KBase offers a number of Apps to filter, cluster, visualize, and functionally enrich the feature sets based on differential expression derived from RNA-seq analysis. Also, the expression data from RNA-seq can be assimilated into metabolic models to identify pathways where expression and flux agree or conflict.

1. **Filtering:** You can [create a filtered expression matrix and associated feature set](https://narrative.kbase.us/#catalog/apps/FeatureSetUtils/upload_featureset_from_diff_expr/release) based on fold-change or adjusted p-value. You can also [filter an expression matrix](https://narrative.kbase.us/#catalog/apps/CoExpression/expression_toolkit_filter_expression/release) based on LOR or ANOVA.
2. **Clustering:** Depending on your preference, run the [Hierarchical](https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_cluster_hierarchical/release), [K-Means](https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_cluster_k_means/release) or [WGCNA](https://narrative.kbase.us/#catalog/apps/CoExpression/expression_toolkit_cluster_WGCNA/release) clustering App to group features into clusters based on gene expression. You can also visualize the clusters as an interactive heatmap.
3. **Functional Enrichment:** [Assess the functional enrichment](https://narrative.kbase.us/#appcatalog/app/kb_functional_enrichment_1/functional_enrichment_go_term/release) for a set of features using associated GO terms.
4. **Integration into Metabolic Models:** Assimilate the expression data from RNA-seq into the metabolic models to [compare reaction fluxes with gene expression](https://narrative.kbase.us/#appcatalog/app/fba_tools/compare_flux_with_expression) and thus identify pathways where expression and flux agree or conflict.

[![](../../.gitbook/assets/transcriptomics1.png)](https://kbase.us/wp-content/uploads/2019/02/transcriptomics1.png)

_Figure 1: The original and new Tuxedo RNA-seq analysis suites in KBase have modular Apps for building flexible analysis workflows._

[![](../../.gitbook/assets/transcriptomics2.png)](https://kbase.us/wp-content/uploads/2019/02/transcriptomics2.png)

_Figure 2: The complete differential RNA-seq workflow in KBase_


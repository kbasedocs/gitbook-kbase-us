---
description: >-
  Some of the tools in KBase available for analyzing microbial communities and
  metagenomics
---

# Metagenomics & Community Exploration

KBase has a multitude of [Apps designed to analyze microbial communities and metagenomic reads data](https://kbase.us/applist/#Microbial%20Communities). They provide a way to understand the functional interactions between species in microbial communities. Annotated genomes extracted from metagenomic sequence libraries can be used for metabolic modeling, comparative phylogenomics, functional profiling, and more.

### **Metagenomic Read Analysis & Assembly**

* [FastQC](https://kbase.us/applist/apps/kb\_fastqc/runFastQC/release)  – Raw read quality control and analysis&#x20;
* [Trim Reads with Trimmomatic](https://kbase.us/applist/apps/kb\_trimmomatic/run\_trimmomatic/release) – Read trimming and adaptor removal
* [Kaiju](https://kbase.us/applist/apps/kb\_kaiju/run\_kaiju/release) – Taxonomy assignment of raw metagenomic reads
* [MEGAHIT](https://kbase.us/applist/apps/MEGAHIT/run\_megahit/release) – Assemble large and complex metagenomic reads
* [MetaSPAdes](https://kbase.us/applist/apps/kb\_SPAdes/run\_metaSPAdes/release) – Assemble shotgun metagenomic reads
* [IDBA-UD](https://kbase.us/applist/apps/kb\_IDBA/run\_idba\_ud/release) – Assemble short metagenomic reads

### Contig Binning, Optimization, and Quality Analysis&#x20;

* [MaxBin2](https://kbase.us/applist/apps/kb\_maxbin/run\_maxbin2/release) – Group metagenomic contigs using depth-of-coverage, nucleotide composition, and marker genes
* [MetaBAT2](https://kbase.us/applist/apps/metabat/run\_metabat/release) – Group metagenomic contigs using strain abundance and nucleotide composition
* [CONCOCT](https://kbase.us/applist/apps/kb\_concoct/run\_kb\_concoct/release) – Group metagenomic contigs using depth-of-coverage and nucleotide composition
* [DAS-Tool](https://kbase.us/applist/apps/kb\_das\_tool/run\_kb\_das\_tool/release) – Optimizes bacterial or archaeal genome bins using a de-replication, aggregation and scoring strategy
* [CheckM ](https://kbase.us/applist/apps/kb\_Msuite/run\_checkM\_lineage\_wf/release)– Assess genome and MAG quality
* [Jorg](https://kbase.us/applist/apps/kb\_jorg/run\_kb\_jorg/beta) ([in beta](../beta.md))– Improve and circularize single-genome assemblies and MAGs
* [Circos](https://kbase.us/applist/apps/kb\_circos/run\_kb\_circos/beta) ([in beta](../beta.md)) – Visualize assembly coverage&#x20;

### **Community Exploration**

* RAST for [Multiple Microbial Genomes](https://kbase.us/applist/apps/RAST\_SDK/reannotate\_microbial\_genomes/release) and [Multiple Microbial Assemblies](https://kbase.us/applist/apps/RAST\_SDK/annotate\_contigsets/release) – Annotate multiple bacterial or archaeal genomes and assemblies or sets using RASTtk
* [Annotate and Distill Genomes with DRAM](https://kbase.us/applist/apps/kb\_DRAM/run\_kb\_dram\_annotate/release) – Annotates Metagenome Assembled Genomes (MAGs) and provides an interactive functional summary per genome
* [dRep](https://kbase.us/applist/apps/kb\_dRep/run\_dereplicate/beta) ([in beta](../beta.md)) – Dereplicate binned contigs, assemblies, and genomes using nucleotide similarity&#x20;
* [VirSorter](https://kbase.us/applist/apps/VirSorter/run\_VirSorter/release) – Identify viral sequences from viral and microbial metagenomes
* [Classify Microbes with GTDB-Tk](https://kbase.us/applist/apps/kb\_gtdbtk/run\_kb\_gtdbtk\_classify\_wf/release)  – Assign taxonomy to isolate and classify Metagenome Assembled Genomes (MAGs) using Genome Taxonomy Database (GTDB) genome taxonomy
* [ModelSEED](https://kbase.us/applist/apps/fba\_tools/build\_multiple\_metabolic\_models/release) – Generate and merge metabolic models from annotated genomes
* [Phylogenetic Pangenome Accumulation](https://kbase.us/applist/apps/kb\_phylogenomics/view\_pan\_phylo/release) – Produce phylogenetic trees from annotated genomes
* [Metabolic modeling tools for microbial communities](metabolic-modeling.md#microbial-communities) – analyze community metabolism

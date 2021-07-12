---
description: >-
  Some of the tools available for analyzing microbial communities and
  metagenomics
---

# Metagenomics & Community Exploration

KBase has a multitude of [Apps](https://kbase.us/applist/#Microbial%20Communities) designed to analyze microbial communities and metagenomic reads data. They provide a way to understand the functional interactions between species in microbial communities. Annotated genomes extracted from metagenomic samples can be used for metabolic modeling, comparative phylogenomics, functional profiling, and more.

**Metagenomic Sequence Analysis & Assembly**

* [FastQC](https://kbase.us/applist/apps/kb_fastqc/runFastQC/release) and [CheckM](https://kbase.us/applist/apps/kb_Msuite/run_checkM_lineage_wf/release) –Quality control and analysis 
* [Trim Reads with Trimmomatic](https://kbase.us/applist/apps/kb_trimmomatic/run_trimmomatic/release) – Read trimming and adaptor removal
* [MEGAHIT](https://kbase.us/applist/apps/MEGAHIT/run_megahit/release) – Assemble large and complex metagenomic reads
* [MetaSPAdes](https://kbase.us/applist/apps/kb_SPAdes/run_metaSPAdes/release) – Assemble shotgun metagenomic reads
* [IDBA-UD](https://kbase.us/applist/apps/kb_IDBA/run_idba_ud/release) – Assemble short metagenomic reads
* [MaxBin2](https://kbase.us/applist/apps/kb_maxbin/run_maxbin2/release) – Bin metagenomic contigs into corresponding putative populations
* [MetaBAT2](https://kbase.us/applist/apps/metabat/run_metabat/release) – Bin metagenomic contigs into corresponding putative genomes

**Community Exploration**

* RAST for [Multiple Microbial Genomes](https://kbase.us/applist/apps/RAST_SDK/reannotate_microbial_genomes/release) and [Multiple Microbial Assemblies](https://kbase.us/applist/apps/RAST_SDK/annotate_contigsets/release) – Annotate multiple bacterial or archaeal genomes and assemblies or sets using RASTtk 
* [Kaiju](https://kbase.us/applist/apps/kb_kaiju/run_kaiju/release) – Classify taxonomy of metagenomic reads
* [ModelSEED](https://kbase.us/applist/apps/fba_tools/build_multiple_metabolic_models/release) – Generate and merge metabolic models
* [Produce phylogenetic trees](https://kbase.us/applist/apps/kb_phylogenomics/view_pan_phylo/release) from annotated genomes
* Use [metabolic modeling tools](metabolic-modeling.md) to analyze community metabolism


---
description: >-
  Some of the tools in KBase available for comparative genomics and
  phylogenetics
---

# Comparative Genomics

KBase provides multiple [comparative genomics and phylogenetic analysis Apps](https://kbase.us/applist/#Comparative%20Genomics) to enable researchers to understand evolutionary relationships between organisms and explore structural and functional variance across genomes.

### **Phylogenetic and Taxonomic Analysis**

* [Insert Genome Into Species Tree](https://kbase.us/applist/apps/SpeciesTreeBuilder/insert\_set\_of\_genomes\_into\_species\_tree/release) – Build a phylogenetic tree with your genomes and RefSeq microbial genomes based on conserved orthologous groups
* [Build Microbial Species Tree](https://narrative.kbase.us/#catalog/apps/kb\_phylogenomics/build\_microbial\_speciestree/beta) ([in beta](../beta.md)) – Build a phylogenetic tree with your genome and phylum exemplars from RefSeq
* [Build Gene Tree](https://narrative.kbase.us/#catalog/apps/kb\_phylogenomics/build\_gene\_tree/beta) ([in beta](../beta.md)) – Build an evolutionary reconstruction tree for a collection of sequence homology related genes
* [Build Phylogenetic Tree with FastTree2](https://kbase.us/applist/apps/kb\_fasttree/run\_FastTree/release)  – Build a tree with FastTree2 directly on a user-created Multiple Sequence Alignment (MSA)

### Sequence Homology and Functional Analysis

* [BLASTx](https://kbase.us/applist/apps/kb\_blast/BLASTx\_Search/release), [tBLASTn](https://kbase.us/applist/apps/kb\_blast/tBLASTn\_Search/release), and [tBLASTx](https://kbase.us/applist/apps/kb\_blast/tBLASTx\_Search/release) – Search genes in genomes and Annotated Metagenome Assemblies (AMAs) and compare translated protein sequences
* [BLASTn](https://kbase.us/applist/apps/kb\_blast/BLASTn\_Search/release) – Search genes and AMAs and compare nucleotide sequences
* [BLASTp](https://kbase.us/applist/apps/kb\_blast/BLASTp\_Search/release) and [psiBLAST](https://kbase.us/applist/apps/kb\_blast/psiBLAST\_msa\_start\_Search/release) – Search genes and AMAs and compare protein sequences
* MUSCLE for [nucleotide](https://kbase.us/applist/apps/kb\_muscle/MUSCLE\_nuc/release) or [protein](https://kbase.us/applist/apps/kb\_muscle/MUSCLE\_prot/release) sequences – Build and analyze multiple sequence alignments (MSA)
* [HMMER MSA Collection](https://narrative.kbase.us/#catalog/modules/kb\_hmmer) – Search and profile genes in genomes and Annotated Metagenome Assemblies (AMAs) with a collection of user-defined MSAs
  * [HMMER Search from MSA](https://kbase.us/applist/apps/kb\_hmmer/HMMER\_MSA\_Search/release) – Search genes in genomes and AMAs with a single user-defined MSA &#x20;
  * [HMMER Search with dbCAN2 of CAZy families](https://kbase.us/applist/apps/kb\_hmmer/HMMER\_dbCAN\_Search/release) – Search and profile genes in genomes and AMAs with the suite of CAZy dbCAN2 hidden markov models (HMMs)
  * [HMMER Search for Phylo Markers](https://kbase.us/applist/apps/kb\_hmmer/HMMER\_PhyloMarkers\_Search/release) – Search and profile genes in genomes and AMAs with the suite of GTDB protein phylogenetic marker HMMs
  * [HMMER Search for Env BioElement families](https://kbase.us/applist/apps/kb\_hmmer/HMMER\_env-bioelement-hmm\_Search/release) – Search and profile genes in genomes and AMAs with the suite of Environmental BioElement metabolic families
* [Annotate Domains in a GenomeSet](https://kbase.us/applist/apps/kb\_phylogenomics/run\_DomainAnnotation\_Sets/release) – Compute canonical gene family membership using COG, Pfam, and TIGRFAMs&#x20;
* [View Function Profile for Genomes](https://kbase.us/applist/apps/kb\_phylogenomics/view\_fxn\_profile/release) and [View Function Profile for a Phylogenetic Tree](https://kbase.us/applist/apps/kb\_phylogenomics/view\_fxn\_profile\_phylo/release) – Examine functional content from canonical domain family annotation

### **Pangenome Exploration**&#x20;

* [Compare Two Proteomes](https://kbase.us/applist/apps/GenomeProteomeComparison/compare\_two\_proteomes/release) – Compare proteomes and produce a synteny map dot plot matrix and table of gene differences
* [Build Pangenome with OrthoMCL](https://kbase.us/applist/apps/PangenomeOrthomcl/build\_pangenome\_with\_orthomcl/release) – Group orthologous protein sequences and identify core and non-core genes across multiple species
* [Compute Pangenome](https://kbase.us/applist/apps/GenomeComparisonSDK/build\_pangenome/release) – Build a pangenome and evaluate protein family conservation&#x20;
* [Pangenome Circle Plot ](https://kbase.us/applist/apps/kb\_phylogenomics/view\_pan\_circle\_plot/release)– View a microbial pangenome as a circle plot using &#x20;
* [Compare Genomes from Pangenome](https://kbase.us/applist/apps/GenomeComparisonSDK/compare\_genomes/release) – Compare isofunctional and homologous gene families within a pangenome
* [Phylogenetic Pangenome Accumulation](https://kbase.us/applist/apps/kb\_phylogenomics/view\_pan\_phylo/release) – View the pangenome in a phylogenetic context&#x20;


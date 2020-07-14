# Community & Metagenomic Analysis

![Community &amp; Metagenomics](https://kbase.us/wp-content/uploads/2018/08/metagenome.png)KBase has a multitude of tools designed to analyze microbial communities and metagenomic reads data. They provide a way to understand the functional interactions between species in microbial communities. Annotated genomes extracted from metagenomic samples can be used for metabolic modeling, comparative phylogenomics, functional profiling, and more.

## KBase Community and Metagenomic Capabilities

**Metagenomic Sequence Analysis & Assembly**

* Perform quality control and analysis with _FastQC_ and _CheckM_
* Trim reads to remove adaptors with _Trimmomatic_
* Assemble binned contigs using _MEGAHIT_, _metaSPAdes_, and _IDBA-UD_
* Bin contigs using _MaxBin2_ or _metaBAT2_
* Import, extract, and edit bins with various apps

**Community Exploration**

* Annotate binned contigs with the RAST pipeline
* Explore taxonomic abundance with _Kaiju_
* Generate and merge metabolic models with _ModelSEED_ 
* Produce phylogenetic trees from annotated genomes
* Use [metabolic modeling](https://kbase.us/metabolic-modeling-in-kbase/) tools to analyze community metabolism

## Narrative Tutorials

The interactive [Genome Extraction from Shotgun Metagenome Sequence Data](https://narrative.kbase.us/narrative/33233) tutorial is a good way to understand an important metagenomic pipeline. The workflow is described in the image below.

![Genome Extraction from Shotgun Metagenome Sequence Data](https://kbase.us/wp-content/uploads/2018/07/Fixed-Nar-Graphic.png)

The [Using Metagenomes to Discover Novel Microbial Linages in KBase](https://narrative.kbase.us/narrative/64677) tutorial is another helpful tool that demonstrates the application of bioinformatic tools for metagenome assembly and genome binning. This Narrative highlights the effective use of employing multiple genome binners and a bin optimization approach.

Use __[The PlantSEED Resource in KBase](https://narrative.kbase.us/narrative/15250) tutorial to see the streamlined process of annotating plant genome sequences, automatically constructing metabolic models based on genome annotations, and using models to test annotations.


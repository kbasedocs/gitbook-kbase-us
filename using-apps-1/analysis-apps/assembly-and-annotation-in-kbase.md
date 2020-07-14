---
description: List of tools for Assembly and Annotation
---

# Assembly and Annotation

![Assemble &amp; Annotate](https://kbase.us/wp-content/uploads/2016/09/genome.jpg)KBase provides multiple Apps for _de novo_ assembly of prokaryotic Next-Generation Sequencing \(NGS\) reads from various sequencing platforms. These assemblies can then be annotated with RAST or Prokka, enabling you to explore structural and functional features of a Genome or use it in other analyses. The interactive [Assembly & Annotation Narrative tutorial](https://narrative.kbase.us/narrative/ws.18188.obj.6) is a good way to learn about this powerful functionality.

### **Reads Quality Control and Assessment**

* [Trim Reads with Trimmomatic](https://narrative.kbase.us/#catalog/apps/kb_trimmomatic/run_trimmomatic/release) – Read trimming and adaptor removal
* [Filter Out Low-Complexity Reads with PRINSEQ](https://narrative.kbase.us/#catalog/apps/kb_PRINSEQ/execReadLibraryPRINSEQ/release) – Filter low complexity reads
* [Assess Read Quality with FastQC](https://narrative.kbase.us/#catalog/apps/kb_fastqc/runFastQC/release) – Quality assessment and reporting
* [Cutadapt](https://narrative.kbase.us/#catalog/apps/kb_cutadapt/remove_adapters/release) – Custom adapter removal

### Assembly

_De novo_ assembly of Illumina and Ion Torrent next-generation sequencing reads. Support for single-end and paired-end read libraries

* [Assemble with HipMer](https://narrative.kbase.us/#catalog/apps/hipmer/run_hipmer_hpc/release) – [HipMer](https://sourceforge.net/p/hipmer/wiki/Home/) is a highly-parallelized port of JGI’s Meraculous fassembler. Meraculous is a de Bruijn graph-based which increases speed by not performing error correction. Instead, it bases contigs on already high-quality scores and fills the gaps based on localized assemblies from the reads. HipMer greatly enhances the speed of Meraculous.
* [Assemble with IDBA-UD](https://narrative.kbase.us/#catalog/apps/AssemblyRAST/run_idba/release) – [IDBA-UD](http://i.cs.hku.hk/~alse/hkubrg/projects/idba_ud/) is an iterative graph-based assembler for single-cell and standard short read data and is good for data of highly uneven sequencing depth. This assembler uses an iterative approach for selecting k-mer size that compensates for the information loss associated with single k-mer based de Bruijn graphs, making IDBA-UD one of the more accurate microbial assemblers.
* [Assemble with MaSuRCA](https://narrative.kbase.us/#catalog/apps/AssemblyRAST/run_masurca/release) – [MaSuRCA](https://academic.oup.com/bioinformatics/article/29/21/2669/195975/The-MaSuRCA-genome-assembler) is a short read assembler that combines the benefits of de Bruijn graph and overlap layout consensus assembly approaches. The main concept is the creation of super-reads that contain sequence information present in the original reads, which super-reads are then extended in both directions using an efficient k-mer lookup table. MaSuRCA is one of a smaller set of assemblers biologists use for eukaryotic assembly.
* [Assemble with MEGAHIT](https://narrative.kbase.us/#catalog/apps/AssemblyRAST/run_megahit/release) – [MEGAHIT](https://academic.oup.com/bioinformatics/article-lookup/doi/10.1093/bioinformatics/btv033) is a single node assembler for large and complex metagenomics NGS reads. It makes use of succinct de Bruijn graph \(SdBG\) to achieve low memory assembly, making it fast and especially suitable for assembly of small metagenomes, metatranscriptomes or low-coverage data in general.
* [Assemble with SPAdes](https://narrative.kbase.us/#catalog/apps/AssemblyRAST/run_spades/release) – [SPAdes](http://online.liebertpub.com/doi/full/10.1089/cmb.2012.0021) is a single-cell and standard assembler based on paired de Bruijn graphs, considered to be one of the most accurate microbial assemblers. SPAdes employs a multisized de Bruijn graph which detects and removes bubble and chimeric reads, estimates insert distance from paired kmers, and computes contigs based on paired assembly graph.
* [Assemble with Velvet](https://narrative.kbase.us/#catalog/apps/AssemblyRAST/run_velvet/release) – [Velvet](http://onlinelibrary.wiley.com/doi/10.1002/0471250953.bi1105s31/full) is a classic de Bruijn graph based assembler that works by efficiently manipulating de Bruijn graphs through simplification and compression. It eliminates errors and resolves repeats by first using an error correction algorithm that merges sequences together. Repeats are then removed from the sequence via the repeat solver that separates paths which share local overlaps.
* [Compare assemblies with QUAST](https://narrative.kbase.us/#catalog/apps/kb_quast/run_QUAST_app/release) – Assess the output assemblies from different configurations of the same assembler, or compare assemblies from multiple assemblers to determine which one is optimal for downstream analysis.

### Annotation

* [Annotate Domains in a Genome](https://narrative.kbase.us/#appcatalog/app/DomainAnnotation/annotate_domains_in_a_genome/release) –  identifies protein domains from widely used domain libraries \(COGs, TIGRfams, Pfam\).
* [Annotate Assembly with Prokka](https://narrative.kbase.us/#appcatalog/app/ProkkaAnnotation/annotate_contigs/release) – combines multiple open-source annotation tools in a quick and thorough annotation pipeline for prokaryotic sequences for genomes, plasmids, and metagenomes.
* [Annotate Microbial Assembly](https://narrative.kbase.us/#appcatalog/app/RAST_SDK/annotate_contigset/release) – uses components from the RAST \([Rapid Annotations using Subsystems Technology](http://rast.nmpdr.org/)\) toolkit to annotate an assembled bacterial or archaeal genome.
* [Annotate Microbial Genome](https://narrative.kbase.us/#appcatalog/app/RAST_SDK/reannotate_microbial_genome/release) – uses RAST to annotate a prokaryotic genome, to update the annotations of a genome, or to perform computations on a set of genomes so that they are consistent.
* [Annotate Plant Coding Sequences with Metabolic Functions](https://narrative.kbase.us/#appcatalog/app/RAST_SDK/annotate_plant_transcripts/release) – performs functional annotation of plant cDNA or protein sequences.

_The output of the annotation apps is a Genome, which is displayed in a tabular genome viewer \(see below\) that shows information about the Genome as well as a list of contigs and the genes that were called on each contig._

![ViewContig](../../.gitbook/assets/viewcontig.png)

### [Assembly and Annotation Narrative Tutorial](https://narrative.kbase.us/narrative/notebooks/ws.18188.obj.6)


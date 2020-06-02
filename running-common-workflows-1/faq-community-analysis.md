# FAQ: Community Analysis

## I am very new to shotgun metagenomics based assembly and annotations, and there are many apps are listed in KBase. Does KBase have a pre-developed workflow for shotgun metagenomics, starting from assembly, annotations and metabolic pathways mining?

KBase tries to be as flexible as possible, so there are many options. One App that you could consider is the JGI Metagenome Assembly App. It is a beta app with a complete workflow, optimized by the JGI, that goes from raw reads to an assembly using BFC, BBTools for read QC and metaSPAdes. The assembled sequence can be binned using the available binning tools. And the individual bins annotated using the standard prokaryotic annotation apps \(Prokka, RAST\). 

For annotating the complete metagenome assembly, the Prokka App is being updated to allow this, but it is still in beta. For metabolic modeling of an entire community, there is currently one app, Build Community Metabolic Model that requires a set of genomes or bins as input. It doesn't take the entire metagenome annotation as input since it attempts to model the individual members and the transfer between them. It is possible to make a mixed bag model using the entire metagenome annotation, that can be useful to see entire pathways are present in the metagenome.

## Why extract genome sequences from metagenomes rather than working with unassembled genome sequences?

When you have a contiguous fragment of a genome, then you get 1\) full-length genes and their protein products, 2\) genomic context of the genes, so have a better chance of understanding of which genes are being used as part of the same system/pathway, especially if they are polycistronic \(operons\), 3\) more accurate phylogenetic placement with consensus placement from multiple genes, and possibly even a clade-specific phylogenetic marker.

## What is the best way to assemble 100-150bp sequencing data in order to recover MAGs?

Effective MAG recovery is highly dependent on your sample. If there is a lot of diversity in the sample and/or low read coverage, MAGs are more challenging to recover, regardless of the tools used. This is partly why we recommend evaluating your data prior to assembly, so you can get some idea of what your data look like.

## What causes the contamination in the bins? And what is considered a high quality bin for filtering them out?

Contamination in the bins can occur for a variety of reasons, including but not limited to contig misassembly, limited diversity in kmer space, horizontal gene transfer. In general, a genome that is 90% complete and &lt;5% contaminated is high-quality. A rough guide to the quality of MAGs and SAGs can be found here: [https://www.nature.com/articles/nbt.3893](https://www.nature.com/articles/nbt.3893)

## How would I exclude eukaryotes and viruses from a marine metagenome?

Note that this is hard to do, not just in KBase, but in general. If I were to attempt this, I would 1\) annotate my entire metagenome assembly, 2\) identify contigs that fall into the different categories of interest \(bacteria/archaea/viruses/eukaryotes\), 3\) filter out contigs belonging to eukaryotes/viruses, 4\) summarize remaining results. A major challenge here will be the unambiguous identification of the different domains of life, which is sometimes tricky \(e.g. prophages\). Another note: file manipulation outside of KBase would be required to perform this task - we currently do not have KBase apps to complete this task.


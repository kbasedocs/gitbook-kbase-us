---
description: >-
  This is a list of error messages found within the Job Log for Functional
  Genomics App Jobs, what they mean and how to go about fixing them or if a job
  ticket needs to be submitted.
---

# Functional Genomics App Errors

## **Types of Errors**

* **UE**=Probably user error or user fixable
* **KE**=KBase error
* **UK**=Unknown or multiple possibles causes
* **TE**=Temporary system problem

{% hint style="info" %}
Use your Browser's search tool to paste in your error message to locate your error message, information about the error and next steps. 
{% endhint %}

You can always submit a ticket for help, questions, or follow-up to the [KBase Help Board](https://kbase-jira.atlassian.net/jira/your-work). 

## Cluster Expression Data: [Hierarchical](https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_cluster_hierarchical/), [Estimate K](https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_estimate_k/), [K-Means](https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_cluster_k_means/)

#### `Error running service CLI for method 'ClusterServiceR.cluster_hierarchical' with exit code 1 …...`

KE: The app is failing and needs maintenance. 

_Nothing can be done at this time. KBase is working on a solution to this problem._ 

## [BLASTp prot-prot Search](https://narrative.kbase.us/#catalog/apps/kb_blast/BLASTp_Search/)

#### `cannot have both input_one_sequence and input_one_ref parameter` 

UE: The app requires either a single Query Sequence or a Query Object with single sequence. 

_Change the inputs and try resubmitting the job._

#### `output_one_name parameter required if input_one_sequence parameter is provided` 

UE: If a Query Sequence is used as input, an Output Query Sequence must be named. 

_Add an output name or change the input. Then try resubmitting the job._

## [**Build a Feature Set**](https://narrative.kbase.us/#catalog/apps/FeatureSetUtils/build_feature_set/)

#### `Feature ID AT2G30640 does not exist in the supplied genome`  

UE The selected feature does not exist in the genome. 

_Recheck the selection and try resubmitting the job._

## **Insert** [**Genome**](https://narrative.kbase.us/#catalog/apps/SpeciesTreeBuilder/insert_set_of_genomes_into_species_tree/) **or** [**Set of Genomes**](https://narrative.kbase.us/#catalog/apps/SpeciesTreeBuilder/insert_genomeset_into_species_tree) **into SpeciesTree**

#### `Error processing genome [xxx/xxx/x] (Not one protein family member found)`  

UE: The species tree is built using the predicted proteins in the genomes. 

_Run an app that does gene calling/genome annotation on the listed genome\(s\). Either RAST or Prokka annotation will work._ 

## [**Phylogenetic Pangenome Accumulation**](https://narrative.kbase.us/#catalog/apps/kb_phylogenomics/view_pan_phylo/)

#### `float division by zero` 

The app will fail with this message if there are only 2 genomes in the pangenome. 

_Try running the app with 3 or more genomes._ 

## **View Function Profile for** [**FeatureSet**](https://narrative.kbase.us/#catalog/apps/kb_phylogenomics/view_fxn_profile_featureSet/)**,** [**Genomes**](https://narrative.kbase.us/#catalog/apps/kb_phylogenomics/view_fxn_profile/)**, or** [**a Phylogenetic Tree**](https://narrative.kbase.us/#catalog/apps/kb_phylogenomics/view_fxn_profile_phylo/)

#### `ABORT: You must run the RAST SEED Annotation App or use SKIP option….` 

UE: The app is expecting RAST annotation for the input genome\(s\). 

_The easiest option is to check the 'Skip missing genomes' box in the advanced parameters. For more complete output 1\) rune Annotate Microbial Genome\(s\) with RAST on the listed genomes and 2\) use the genome\(s\) newly created by RAST as the input to the View Function Profile. Because the names are different, the app does not know how to find the newer version of the genome._

#### `ABORT: You must run the 'Domain Annotation' App or use SKIP option ….` 

UE: The app is expecting Domain annotation for the input genome\(s\).

_Either run the Domain Annotation on the listed genome\(s\) or check the ‘Skip missing genomes’ box in the advanced parameters._ 

## [Classify Taxonomy of Metagenomic Reads with Kaiju](https://narrative.kbase.us/#catalog/apps/kb_kaiju/run_kaiju)

#### `missing or empty krona input file`  

UE: The filters were too restrictive and no output was generated. 

_Change the input parameters and try resubmitting the job._

## [**GTDB-Tk classify**](https://narrative.kbase.us/#catalog/apps/kb_gtdbtk/run_kb_gtdbtk/release)

#### `(1, '/bin/bash -c "source activate py2 && GTDBTK_DATA_PATH`  

KE: Unknown error. 

_Nothing can be done at this time. KBase is working on a solution to this problem._

#### `(2, '/bin/bash -c "source activate py2 && GTDBTK_DATA_PATH` 

UE: The ‘Minimum Alignment Percent’ was left blank 

_Assign a minimum percent in the advanced parameters and try resubmitting the job._

## [**Create Differential Expression Matrix using DeSEQ2**](https://narrative.kbase.us/#catalog/apps/kb_deseq/run_DESeq2/release) 

#### `Invalid input:nselect Run All Paired Condition Combinations or provide partial condition pairs. Dont do both`  

UE: The user failed to select ALL vs Partial conditions. It cannot be blank and you cannot select both. 

_Do **one** of the following:_

1. _Check the box next to 'Run All Paired Condition Combinations.'_
2. _Add a 'Run Partial Condition Combinations.'_

## [Classify Taxonomy of Metagenomic Reads with GOTTCHA2](https://narrative.kbase.us/#catalog/apps/gottcha2/run_gottcha2/)

#### `(2, No such file or directory)` 

1. UE: The wrong reference database was used. 

   _Change the reference database and try resubmitting the job._

2. KE: More than two reads libraries were included in the input. 

   _The developers have a task to fix this. The workaround is to only submit a maximum of two libraries at a time. Merging reads libraries can help with this process._ 

## \*\*\*\*[**Kraken**2 Taxonomic Sequence Classifier](https://narrative.kbase.us/#catalog/apps/kraken2/run_kraken2/beta)

#### `You must enter either an input genome or input reads` 

UE: There are two input options and one of them must be selected. 

_Add an input and try resubmitting the job._

## [**VirSorter**](https://narrative.kbase.us/#catalog/apps/VirSorter/run_VirSorter/release)

#### `Cannot write data to fasta` 

KE: The user interface allows users to enter a genome as input but the app will reject it. The error has been reported. 

_Change to an input that is not a genome and try resubmitting the job._


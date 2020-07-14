---
description: >-
  This is a list of error messages found within the Job Log for Assembly App
  Jobs, what they mean and how to go about fixing them or if a job ticket needs
  to be submitted.
---

# Assembly App Errors

## **Types of Errors**

* **UE**=User fixable or possible user error
* **KE**=KBase error
* **UK**=Unknown or multiple possibles causes
* **TE**=Temporary system problem

{% hint style="info" %}
Use your Browser's search tool to paste in your error message to locate your error message, information about the error and next steps. 
{% endhint %}

You can always submit a ticket for help, questions, or follow-up to the [KBase Help Board](https://kbase-jira.atlassian.net/jira/your-work). 

## Common errors across SPAdes Assembly Apps

### [Assemble Reads with SPAdes](https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_SPAdes); [Assemble Reads with HybridSPAdes](https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_hybridSPAdes/release); [Assemble Reads with metaSPAdes](https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_metaSPAdes/release); [Filter Assembled Contigs by Length](https://narrative.kbase.us/#catalog/apps/kb_assembly_compare/run_filter_contigs_by_length)

#### `There are no contigs to save, thus there is no valid assembly.`  

UE: There are no contigs that passed the minimum contig size. 

_Adjust the minimum contig size or other optional parameters. Then try resubmitting the job._ 

#### `Error running SPAdes, return code: 1` 

UE: Potential explanations 

* The coverage of your input is so uneven that everything is disconnected. 
* The reads contain too many k-mers to fit into available memory. 
* Incomplete write! Reason: No space left on device. 
* Coverage not uniform hybridSPAdes ended abnormally 
* Failed to align paired reads left paired reads is not equal to right paired reads cannot specify any data types except a single paired-end library \(optionally accompanied by a single library of TSLR-contigs, or PacBio reads, or Nanopore reads\) in metaSPAdes mode 
* The program was terminated by segmentation fault 
* Too many erroneous kmers, the estimates might be unreliable

_Look for an explanation from SPAdes in the log. If possible, correct the error and try resubmitting the job._ 

#### `Deinterleave failed - line count is not divisible by 8` 

UE: The interleaved file does not appear to be the correct format. 

_Recheck that the files are labeled properly and try resubmitting the job._ 

#### `Reads object XXX is marked as containing metagenomic data but the assembly method was not specified as metagenomic` 

UE: The input object and the selected parameters disagree 

_Change the data input or the app parameters and try resubmitting the job._ 

#### `Plasmid assembly requires that one and only one library as input.` 

UE: There is more than one input library. 

_Change the input to be just one library, change the library source, or merge the libraries and try resubmitting the job._ 

#### `Invalid type for object 27459/32/1…..` 

UE: The user is allowed to enter an Assembly for the long reads \(like in the MaSuRCA app\) but this results in an error. 

_Ensure objects correspond with the object types listed and try resubmitting the job._ 

#### `QUAST reported an error, return code was 4` 

UE: None of the assembly files contains correct contigs \(none greater than the minimum contig filter\). 

_Provide different files or decrease --min-contig threshold. Then try resubmitting the job._ 

## [Velvet Assembler](https://narrative.kbase.us/#catalog/apps/Velvet/run_velvet)

#### `Error on Object #1: Illegal character in object name`

UE: Velvet did not assemble any contigs longer than the minimum length. 

_Change the configuration and try resubmitting the job._ 

## \_\_[Assemble with HipMer](https://narrative.kbase.us/#catalog/apps/hipmer/run_hipmer_hpc)

#### `'list index out of range'` 

UE: There is no input data 

_Add_ [_data_](../../getting-started/narrative/add-data.md) _to the app and try resubmitting the job._ 

#### `Error in HipMER execution` 

UE: Possible causes - 

* The data was a metagenome, but the metagenome flag was not enabled 
* The  metagenome flag was enabled but the data was not a metagenome 
* Exceeded time limit at NERSC
* Other data/parameter combinations that result in no returned assembly

_Change the configuration and try resubmitting the job._ 

#### `Using input parameters, you have filtered all contigs from the HipMer assembly. Decrease the minimum contig size and try again`

UE: The minimum contig length is too large. 

_Lower the minimum contig length in the parameters and try resubmitting the job._ 

#### `(2, No such file or directory)` 

TE: Hipmer was in the queue too long and did not run. 

_Try resubmitting the job_. 

## [MaSuRCA Assembler](https://narrative.kbase.us/#catalog/apps/kb_MaSuRCA/run_masurca_assembler)

#### `Error running command: XXX/config.txt Exit Code: 1` 

UE: invalid file for PACBIO invalid file for NANOPORE.

_Recheck the file and try resubmitting the job._ 

## [Assemble Transcripts using StringTie](https://narrative.kbase.us/#catalog/apps/kb_stringtie/run_stringtie/)

#### `Genome at 48203/40/2 does not have reference to the assembly object` 

UE: A previous step \(e.g., HISAT\) used an assembly instead of a genome as input. 

_Go back to the previous step and use a genome as input._ 

#### `coercing to unicode: need string or buffer` 

KE: genome related issue with some of the NCBI RefSeq genomes. 

_Workaround: import the GFF-format genome with correct feature annotations and try resubmitting the job. See_ [_https://kbase-jira.atlassian.net/browse/PUBLIC-969_](https://kbase-jira.atlassian.net/browse/PUBLIC-969)\_\_

## [**Merge Reads Libraries**](https://narrative.kbase.us/#catalog/apps/kb_ReadsUtilities/KButil_Merge_MultipleReadsLibs_to_OneLibrary/)

#### `incompatible read library types in ReadsSet` 

UE_:_ Every library in the input to merge must be of the same type, either all Paired-End or Single-End. 

_Change the inputs and try resubmitting the job._

#### **`[Errno 28] No space left on device`**

UE/KE: Most likely case: The combined size of the libraries exceeds the current KBase hardware. Efforts are being made to increase capacity and to provide a cleaner more informative message. Workarounds should be considered.

_The  workarounds include:_  

1. _Reduce the number of libraries in the merge_
2. _Run Kaiju to determine which samples have similar profiles. Then try the co-assemblies pairwise using two-at-a-time based on which profiles are most similar._ 

  __


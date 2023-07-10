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
Use your Browser's search tool to paste in your error message to locate your error message, information about the error and next steps.&#x20;
{% endhint %}

You can always submit a ticket for help, questions, or follow-up to the [KBase Help Board](https://kbase-jira.atlassian.net/jira/your-work).&#x20;

## Common errors across SPAdes Assembly Apps

### [Assemble Reads with SPAdes](https://narrative.kbase.us/#catalog/apps/kb\_SPAdes/run\_SPAdes); [Assemble Reads with HybridSPAdes](https://narrative.kbase.us/#catalog/apps/kb\_SPAdes/run\_hybridSPAdes/release); [Assemble Reads with metaSPAdes](https://narrative.kbase.us/#catalog/apps/kb\_SPAdes/run\_metaSPAdes/release); [Filter Assembled Contigs by Length](https://narrative.kbase.us/#catalog/apps/kb\_assembly\_compare/run\_filter\_contigs\_by\_length)

#### `There are no contigs to save, thus there is no valid assembly.`&#x20;

UE: There are no contigs that passed the minimum contig size.&#x20;

_Adjust the minimum contig size or other optional parameters. Then try resubmitting the job._&#x20;

#### `Error running SPAdes, return code: 1`&#x20;

UE: Potential explanations&#x20;

* The coverage of your input is so uneven that everything is disconnected.&#x20;
* The reads contain too many k-mers to fit into available memory.&#x20;
* Incomplete write! Reason: No space left on device.&#x20;
* Coverage not uniform hybridSPAdes ended abnormally&#x20;
* Failed to align paired reads left paired reads is not equal to right paired reads cannot specify any data types except a single paired-end library (optionally accompanied by a single library of TSLR-contigs, or PacBio reads, or Nanopore reads) in metaSPAdes mode&#x20;
* The program was terminated by segmentation fault&#x20;
* Too many erroneous kmers, the estimates might be unreliable

_Look for an explanation from SPAdes in the log. If possible, correct the error and try resubmitting the job._&#x20;

#### `Deinterleave failed - line count is not divisible by 8`&#x20;

UE: The interleaved file does not appear to be the correct format.&#x20;

_Recheck that the files are labeled properly and try resubmitting the job._&#x20;

#### `Reads object XXX is marked as containing metagenomic data but the assembly method was not specified as metagenomic`&#x20;

UE: The input object and the selected parameters disagree&#x20;

_Change the data input or the app parameters and try resubmitting the job._&#x20;

#### `Plasmid assembly requires that one and only one library as input.`&#x20;

UE: There is more than one input library.&#x20;

_Change the input to be just one library, change the library source, or merge the libraries and try resubmitting the job._&#x20;

#### `Invalid type for object 27459/32/1…..`&#x20;

UE: The user is allowed to enter an Assembly for the long reads (like in the MaSuRCA app) but this results in an error.&#x20;

_Ensure objects correspond with the object types listed and try resubmitting the job._&#x20;

#### `QUAST reported an error, return code was 4`&#x20;

UE: None of the assembly files contains correct contigs (none greater than the minimum contig filter).&#x20;

_Provide different files or decrease --min-contig threshold. Then try resubmitting the job._&#x20;

## [Velvet Assembler](https://narrative.kbase.us/#catalog/apps/Velvet/run\_velvet)

#### `Error on Object #1: Illegal character in object name`

UE: Velvet did not assemble any contigs longer than the minimum length.&#x20;

_Change the configuration and try resubmitting the job._&#x20;

## [Assemble with HipMer](https://narrative.kbase.us/#catalog/apps/hipmer/run\_hipmer\_hpc)

#### `'list index out of range'`&#x20;

UE: There is no input data&#x20;

_Add_ [_data_](../../getting-started/narrative/add-data.md) _to the app and try resubmitting the job._&#x20;

#### `Error in HipMER execution`&#x20;

UE: Possible causes -&#x20;

* The data was a metagenome, but the metagenome flag was not enabled&#x20;
* The  metagenome flag was enabled but the data was not a metagenome&#x20;
* Exceeded time limit at NERSC
* Other data/parameter combinations that result in no returned assembly

_Change the configuration and try resubmitting the job._&#x20;

#### `Using input parameters, you have filtered all contigs from the HipMer assembly. Decrease the minimum contig size and try again`

UE: The minimum contig length is too large.&#x20;

_Lower the minimum contig length in the parameters and try resubmitting the job._&#x20;

#### `(2, No such file or directory)`&#x20;

TE: Hipmer was in the queue too long and did not run.&#x20;

_Try resubmitting the job_.&#x20;

## [MaSuRCA Assembler](https://narrative.kbase.us/#catalog/apps/kb\_MaSuRCA/run\_masurca\_assembler)

#### `Error running command: XXX/config.txt Exit Code: 1`&#x20;

UE: invalid file for PACBIO invalid file for NANOPORE.

_Recheck the file and try resubmitting the job._&#x20;

## [Assemble Transcripts using StringTie](https://narrative.kbase.us/#catalog/apps/kb\_stringtie/run\_stringtie/)

#### `Genome at 48203/40/2 does not have reference to the assembly object`&#x20;

UE: A previous step (e.g., HISAT) used an assembly instead of a genome as input.&#x20;

_Go back to the previous step and use a genome as input._&#x20;

#### `coercing to unicode: need string or buffer`&#x20;

KE: genome related issue with some of the NCBI RefSeq genomes.&#x20;

_Workaround: import the GFF-format genome with correct feature annotations and try resubmitting the job. See_ [_https://kbase-jira.atlassian.net/browse/PUBLIC-969_](https://kbase-jira.atlassian.net/browse/PUBLIC-969)

## [**Merge Reads Libraries**](https://narrative.kbase.us/#catalog/apps/kb\_ReadsUtilities/KButil\_Merge\_MultipleReadsLibs\_to\_OneLibrary/)

#### `incompatible read library types in ReadsSet`&#x20;

UE_:_ Every library in the input to merge must be of the same type, either all Paired-End or Single-End.&#x20;

_Change the inputs and try resubmitting the job._

#### **`[Errno 28] No space left on device`**

UE/KE: Most likely case: The combined size of the libraries exceeds the current KBase hardware. Efforts are being made to increase capacity and to provide a cleaner more informative message. Workarounds should be considered.

_The  workarounds include:_ &#x20;

1. _Reduce the number of libraries in the merge_
2. _Run Kaiju to determine which samples have similar profiles. Then try the co-assemblies pairwise using two-at-a-time based on which profiles are most similar._&#x20;

&#x20;&#x20;

---
description: >-
  This is a list of error messages found within the Job Log for Annotation App
  Jobs, what they mean and how to go about fixing them or if a job ticket needs
  to be submitted.
---

# Annotation App Errors

## **Types of Errors**

* **UE**=Probably user error or user fixable
* **KE**=KBase error
* **UK**=Unknown or multiple possibles causes
* **TE**=Temporary system problem

{% hint style="info" %}
Use your Browser's search tool to paste in your error message to locate your error message, information about the error and next steps. 
{% endhint %}

You can always submit a ticket for help, questions, or follow-up to the [KBase Help Board](https://kbase-jira.atlassian.net/jira/your-work). 

## **Common Errors across Annotation Apps**

#### RAST: [Annotate Microbial Genome](https://narrative.kbase.us/#catalog/apps/RAST_SDK/reannotate_microbial_genome/) / [Annotate Multiple Microbial Genomes](https://narrative.kbase.us/#catalog/apps/RAST_SDK/reannotate_microbial_genomes/) / [Annotate Microbial Assembly](https://narrative.kbase.us/#catalog/apps/RAST_SDK/annotate_contigset/) **/** [Annotate Multiple Microbial Assemblies](https://narrative.kbase.us/#catalog/apps/RAST_SDK/annotate_contigsets/) 

#### Prokka:  [Annotate Assembly and Re-annotate Genomes with Prokka](https://narrative.kbase.us/#catalog/apps/ProkkaAnnotation/annotate_contigs/)

#### `(2, No such file or directory)` 

UE: One or more contigs had header lines longer than 37 characters. 

_Edit the fasta file, upload again, and try resubmitting the job._

#### `Error invoking method call_features_rRNA_SEED`  

UE: One or more of the FASTA header lines are extremely long. 

_Shorten them, re-upload, and try resubmitting the job._ _._ 

#### `Object #1, 0ae7adb1-6351-4d26-a526-cc09c15e46ee.report has invalid reference: ….`

UE: There are no input datasets listed. 

_Supply the dataset\(s\) and try resubmitting the job._

####  `too many contigs` 

UE: RAST has a limit of 10,000 contigs. Prokka has a limit of 30,000 contigs.

_Divide the file or bin the contigs before running RAST again by resubmitting the job._

#### `Error on ObjectSpecification #1: Unable to parse version portion of object reference nnnn/2/1, nnnn to an integer` 

UE: The wrong delimiter was used in the free text of the Assembly list or Genome list. 

_Change the delimiter to a semicolon \(;\) and try resubmitting the job._

#### `Error on ObjectSpecification #1: Illegal number of separators /`

UE: The wrong delimiter was used in the free text of the Assembly list or Genome list.

_Change the delimiter to a semicolon \(;\) and try resubmitting the job._ 

#### `name assembly_info is not defined` 

UE: You are running the beta version of the app. 

_Change to the released version._

## [Annotate Plant Transcripts with Metabolic Functions](https://narrative.kbase.us/#catalog/apps/kb_plant_rast/annotate_plant_transcripts/dbac462bc80e4d9db11efe0ff6e82c8fb28a3034)

#### `The genome does not contain any CDSs or features!` 

UE: The input genome does not have the needed features. 

_Double check the file and try resubmitting the job._

## [**Assess Genome Quality with CheckM**](https://narrative.kbase.us/#catalog/apps/kb_Msuite/run_checkM_lineage_wf/release)

#### `Object NNN cannot be accessed: User user_name may not read workspace XXXXX`  

UE: The app requires data which is owned by another user and you do not have access. In another scenario, either you or the user have deleted the original assembly. 

_Ask the user for access to the needed file._


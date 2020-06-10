---
description: >-
  This is a list of error messages found within the Job Log for Import Jobs,
  what they mean and how to go about fixing them or if a job ticket needs to be
  submitted.
---

# Import Job Errors

## **Types of Import Job Errors**

* **UE**=Probably user error or user fixable
* **KE**=KBase error

{% hint style="info" %}
Use your Browser's search tool to paste in the error to locate possible fixes or next steps. 
{% endhint %}

You can always submit a ticket for help, questions, or follow-up to the [KBase Help Board](https://kbase-jira.atlassian.net/jira/your-work). 

## Common Import Job Error Messages

#### `Cannot connect to URL: ftp://ftp.imicrobe.us. ...` 

UE: The provided URL cannot be accessed from within KBase. 

_Recheck the URL and permissions. Then try resubmitting the job._ 

#### `Invalid FTP Link: ...` 

UE: The provided URL cannot be accessed from within KBase. Perhaps the option for ‘Direct’ download should be specified instead of ‘FTP’ \(e.g., when downloading from the SRA\) 

_Recheck the URL and permissions. Then try resubmitting the job._ 

#### `Invalid Google Drive Link ...` 

UE: The provided URL cannot be accessed from within KBase. 

_Recheck the URL and its permission. Then try resubmitting the job._ 

## **Bulk or Batch Imports**

#### `(2, No such file or directory)` 

UE: The file is not in the Staging Area.

_Verify that the name is correct and upload is complete. Then try resubmitting the job._ 

## [**Import FASTQ/SRA File as Reads from Staging Area**](https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fastq_sra_as_reads_from_staging)

#### `(2, No such file or directory)` 

KE: The fastqdump ran but the file names are not the expected names. 

_Use the long workaround_ [_here_](https://kbase-jira.atlassian.net/browse/PUBLIC-946)_._

#### `SRA input file type selected. But missing SRA file` 

UE**:** The format of the file is not recognized. 

_Recheck the file and try resubmitting the job._ 

#### `Invalid FASTQ file ...` 

KE/UE: Sometimes the user has specified the file name wrong. It can also happen because the importer has problems with file names that end in ".1" 

_Use the long workaround_ [_here_](https://kbase-jira.atlassian.net/browse/PUBLIC-946)_._

#### `Error running command: /kb/deployment/bin/fastq-dump ...` 

UE: The file does not appear to be in the expected SRA format. 

_Recheck the file and try resubmitting the job._ 

#### `Error running command:pigz ...` 

UE: The file could not be unzipped by KBase and most likely couldn’t be unzipped by the user either. 

_Verify the file is can be unzipped locally._ 

#### `Both SRA and FASTQ/FASTA file given.` 

UE: The inputs should be either all fast or all SRA. 

_Modify the inputs, then try resubmitting the job._ 

#### `Same file [XXX.XXXX.gz] is used for forward and reverse. Please select different files and try again.` 

UE: There are names for both a forward and reverse strand and they are identical. 

_A Single-end read library only needs one name. A Paired-end read library needs two files with different names._ 

#### `File /kb/XXX.fasta is not a FASTQ file` 

UE: Either the file is not in fastq format or the file extension is not recognized.

_Recheck that the file is in the right format. Change the extension to .fastq if needed, then try resubmitting the job._ 

#### `Invalid FASTQ file` 

UE: Possible issues

* The fastq file includes one or more sequences that are less than 10 bases. Short reads are a problem for some tools.
* The fastq file doesn't have the right number of lines. For example, the lines in a single-end file needs to be a multiple of four and interleaved paired-end library should be a multiple of eight.
* The options haven't been selected correctly. For example, using an interleaved fastq file but failing to check the Interleaved box. _The page_ [_http://kbase.us/data-upload-download-guide/short-reads/_](http://kbase.us/data-upload-download-guide/short-reads/) _might be helpful here._ 
* The file might not have the right filename to be recognized.
  * The file is an SRA file and not fastq. 
* DOS-style carriage-return line files along with new-lines. Our fasta validation doesn't handle this properly. _To remove the carriage return characters use can this unix command_

  _`tr -d '\015' < 1.fastq >cleaned_1.fastq`_

  \_\_[_https://support.nesi.org.nz/hc/en-gb/articles/218032857-Converting-from-Windows-style-to-UNIX-style-line-endings_](https://support.nesi.org.nz/hc/en-gb/articles/218032857-Converting-from-Windows-style-to-UNIX-style-line-endings)\_\_

  \_\_[_https://kb.iu.edu/d/acux_](https://kb.iu.edu/d/acux)\_\_

#### `Reading FASTQ record failed - non-blank lines are not a multiple of four.`

UE: The number of lines in the FASTQ file are not a multiple of four.

_Recheck the file and try resubmitting the job._ 

#### `Interleave failed - reads files do not have an equal number of records….`

UE: Something went wrong trying to interleave the Paired-end files.

_Recheck the line count of the files. Hidden carriage returns or linefeeds in the file could contribute to the problem._

#### `Deinterleave failed - line count is not divisible by 8`

UE: The interleaved file does not appear to be the correct format.

_Recheck the file and try resubmitting the job._ 

#### `Object 1: Illegal character in object name` 

UE: The name of the output reads object can’t have spaces or special characters.

_Rename the output file and then try resubmitting the job._ 

## [Import FASTA File as Assembly from Staging Area](https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fasta_as_assembly_from_staging)

#### `There are no contigs to save, thus there is no valid assembly.`

UE_:_ There are no contigs that passed the minimum contig size.

_Adjust the minimum contig size or other optional parameters. Then try resubmitting the job._ 

#### `The FASTA header key XXX appears more than once in the file`

UE: The FASTA header lines may not be unique.

_Recheck the format of the header lines and_ _try resubmitting the job._ 

`This FASTA file has non nucleic acid characters`

UE: The file appears to be proteins or special characters instead of DNA.

_Recheck the file contents, and then_ _try resubmitting the job._ 

`This FASTA file may have amino acids in it instead of the required nucleotides.`

UE: The file appears to be proteins instead of DNA.

_Recheck the file contents, and then_ _try resubmitting the job._ 

`FASTQ/FASTA input file type selected. But missing FASTQ/FASTA file`

UE: Selected file does not match the import selected.

_Select a valid combination and try resubmitting the job._ 

`(\utf-8\, b\PK\x03\x04\x14\x00\x08…….`

UE: Attempt to import a zip file with multiple files as a single data object.

_Run the App '_ [_Unpack a Compressed File in Staging Area_](https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/unpack_staging_file)_' on the file and retry resubmitting the job._ 

## [Import GenBank File as Genome from Staging Area](https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_genbank_as_genome_from_staging)

#### **`Duplicate gene ID: XXXX_xxxx`**

UE: Gene IDs within the input file are not unique.

_Edit gene IDs and try resubmitting the job._ 

#### **`The input directory does not have any files with one of the following extensions .gbff,.gbk,.gb,.genbank,.dat,.gbf`**

UE: The app only recognizes the listed file extensions as valid GenBank files.

_Change the file extension and try resubmitting the job._ 

#### **`XXX is not a valid KBase taxon ID`**

UE: The Taxonomy ID in the advanced parameters is optional and needs to be an integer when specified. The user provided the text string ‘XXX’.

_Use an integer taxon ID or leave it blank. The information will be picked up from the GenBank file or from the scientific name._

## [Import GFF3/FASTA file as Genome from Staging Area](https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_gff_fasta_as_genome_from_staging)

#### **`Every feature sequence id must match a fasta sequence id`**

UE: The IDs in the ‘sequence source’ lines must match the header lines in the FASTA file in the GFF format. 

_Correct the GFF format and try resubmitting the job._  

#### **`unable to parse >.....`**

UE: The file may not be in GFF format. 

_Recheck the file format and try resubmitting the job._ 

#### `Features must be completely contained within the Contig in the Fasta file.`

UE: The coordinates for the feature are outside the bounds of the contig.

 _Recheck the file where indicated and try resubmitting the job._ 

## [Import Media file \(TSV/Excel\) from Staging Area](https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_tsv_excel_as_media_from_staging)

#### **`Starch.csv" is not a valid EXCEL nor TSV file`**

UE: File format is not recognized. 

_Recheck the file format and try resubmitting the job._  

## [Import TSV/XLS/SBML File as an FBAModel from Staging Area](https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_file_as_fba_model_from_staging)

#### **`data file 4.xml either does not use commas or tabs as a separator`**

UE: File format is not recognized. 

_Recheck the file format and try resubmitting the job._  

#### **`No object with name _Nostoc_azollae__0708`**

UE: The genome does not exist in the narrative 

_Fix the genome name and try resubmitting the job._ 

## [**Unpack a Compressed File in Staging Area**](https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/unpack_staging_file) ****

#### `Error running command:pigz ...` 

UE: The file could not be unzipped by KBase and most likely couldn’t be unzipped by the user either. 

_Verify the file can be unzipped locally._ 


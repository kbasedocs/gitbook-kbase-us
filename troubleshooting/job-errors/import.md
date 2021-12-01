---
description: >-
  This is a list of error messages found within the Job Log for Import Jobs,
  what they mean and how to go about fixing them or if a job ticket needs to be
  submitted.
---

# Import Job Errors

## **Types of Import Job Errors**

* **UE**=User fixable or possible user error
* **KE**=KBase error

{% hint style="info" %}
Use your Browser's search tool to paste in the error to locate possible fixes or next steps.&#x20;
{% endhint %}

You can always submit a ticket for help, questions, or follow-up to the [KBase Help Board](https://kbase-jira.atlassian.net/jira/your-work).&#x20;

## Common Import Job Error Messages

#### `Cannot connect to URL: ftp://ftp.imicrobe.us. ...`&#x20;

UE: The provided URL cannot be accessed from within KBase.&#x20;

_Recheck the URL and permissions. Then try resubmitting the job._&#x20;

#### `Invalid FTP Link: ...`&#x20;

UE: The provided URL cannot be accessed from within KBase. Perhaps the option for ‘Direct’ download should be specified instead of ‘FTP’ (e.g., when downloading from the SRA)&#x20;

_Recheck the URL and permissions. Then try resubmitting the job._&#x20;

#### `Invalid Google Drive Link ...`&#x20;

UE: The provided URL cannot be accessed from within KBase.&#x20;

_Recheck the URL and its permission. Then try resubmitting the job._&#x20;

## **Bulk or Batch Imports**

#### `(2, No such file or directory)`&#x20;

UE: The file is not in the Staging Area.

_Verify that the name is correct and upload is complete. Then try resubmitting the job._&#x20;

## [**Import FASTQ/SRA File as Reads from Staging Area**](https://narrative.kbase.us/#catalog/apps/kb\_uploadmethods/import\_fastq\_sra\_as\_reads\_from\_staging)

#### `(2, No such file or directory)`&#x20;

KE: The fastqdump ran but the file names are not the expected names.&#x20;

_Use the long workaround_ [_here_](https://kbase-jira.atlassian.net/browse/PUBLIC-946)_._

#### `SRA input file type selected. But missing SRA file`&#x20;

UE**:** The format of the file is not recognized.&#x20;

_Recheck the file and try resubmitting the job._&#x20;

#### `Invalid FASTQ file ...`&#x20;

KE/UE: Sometimes the user has specified the file name wrong. It can also happen because the importer has problems with file names that end in ".1"&#x20;

_Use the long workaround_ [_here_](https://kbase-jira.atlassian.net/browse/PUBLIC-946)_._

#### `Error running command: /kb/deployment/bin/fastq-dump ...`&#x20;

UE: The file does not appear to be in the expected SRA format.&#x20;

_Recheck the file and try resubmitting the job._&#x20;

#### `Error running command:pigz ...`&#x20;

UE: The file could not be unzipped by KBase and most likely couldn’t be unzipped by the user either.&#x20;

_Verify the file is can be unzipped locally._&#x20;

#### `Both SRA and FASTQ/FASTA file given.`&#x20;

UE: The inputs should be either all fastq/a or all SRA.&#x20;

_Modify the inputs, then try resubmitting the job._&#x20;

#### `Same file [XXX.XXXX.gz] is used for forward and reverse. Please select different files and try again.`&#x20;

UE: There are names for both a forward and reverse strand and they are identical.&#x20;

_A Single-end read library only needs one name. A Paired-end read library needs two files with different names._&#x20;

#### `File /kb/XXX.fasta is not a FASTQ file`&#x20;

UE: Either the file is not in fastq format or the file extension is not recognized.

_Recheck that the file is in the right format. Change the extension to .fastq if needed, then try resubmitting the job._&#x20;

#### `Invalid FASTQ file`&#x20;

UE: Possible issues

* The fastq file includes one or more sequences that are less than 10 bases. Short reads are a problem for some tools.
* The fastq file doesn't have the right number of lines. For example, the lines in a single-end file needs to be a multiple of four and interleaved paired-end library should be a multiple of eight.
* The options haven't been selected correctly. For example, using an interleaved fastq file but failing to check the Interleaved box. _The documentation on_ [_FASTQ/SRA Reads_](../../data/upload-download-guide/reads.md) _may be helpful._
* The file might not have the right filename to be recognized.
  * The file is an SRA file and not FASTQ.&#x20;
* DOS-style carriage-return line files along with new-lines. Our fasta validation doesn't handle this properly. _To remove the carriage return characters use this_ [_unix command:_](https://support.nesi.org.nz/hc/en-gb/articles/218032857-Converting-from-Windows-style-to-UNIX-style-line-endings) _ **`tr -d '\015' < 1.fastq >cleaned_1.fastq`**_

#### `Reading FASTQ record failed - non-blank lines are not a multiple of four.`

UE: The number of lines in the FASTQ file are not a multiple of four.

_Recheck the file and try resubmitting the job._&#x20;

#### `Interleave failed - reads files do not have an equal number of records….`

UE: Something went wrong trying to interleave the Paired-end files.

_Recheck the line count of the files. Hidden carriage returns or linefeeds in the file could contribute to the problem._

#### `Deinterleave failed - line count is not divisible by 8`

UE: The interleaved file does not appear to be the correct format.

_Recheck the file and try resubmitting the job._&#x20;

#### `Object 1: Illegal character in object name`&#x20;

UE: The name of the output reads object can’t have spaces or special characters.

_Rename the output file and then try resubmitting the job._&#x20;

## [Import FASTA File as Assembly from Staging Area](https://narrative.kbase.us/#catalog/apps/kb\_uploadmethods/import\_fasta\_as\_assembly\_from\_staging)

#### `There are no contigs to save, thus there is no valid assembly.`

UE_:_ There are no contigs that passed the minimum contig size.

_Adjust the minimum contig size or other optional parameters. Then try resubmitting the job._&#x20;

#### `The FASTA header key XXX appears more than once in the file`

UE: The FASTA header lines may not be unique.

_Recheck the format of the header lines and_ _try resubmitting the job._&#x20;

#### `This FASTA file has non nucleic acid characters`

UE: The file appears to be proteins or special characters instead of DNA.

_Recheck the file contents, and then_ _try resubmitting the job._&#x20;

#### `This FASTA file may have amino acids in it instead of the required nucleotides.`

UE: The file appears to be proteins instead of DNA.

_Recheck the file contents, and then_ _try resubmitting the job._&#x20;

#### `FASTQ/FASTA input file type selected. But missing FASTQ/FASTA file`

UE: Selected file does not match the import selected.

_Select a valid combination and try resubmitting the job._&#x20;

#### `(\utf-8\, b\PK\x03\x04\x14\x00\x08…….`

UE: Attempt to import a zip file with multiple files as a single data object.

_Run the App '_ [_Unpack a Compressed File in Staging Area_](https://narrative.kbase.us/#catalog/apps/kb\_uploadmethods/unpack\_staging\_file)_' on the file and retry resubmitting the job._&#x20;

## [Import GenBank File as Genome from Staging Area](https://narrative.kbase.us/#catalog/apps/kb\_uploadmethods/import\_genbank\_as\_genome\_from\_staging)

#### **`Duplicate gene ID: XXXX_xxxx`**

UE: Gene IDs within the input file are not unique.

_Edit gene IDs and try resubmitting the job._&#x20;

#### **`The input directory does not have any files with one of the following extensions .gbff,.gbk,.gb,.genbank,.dat,.gbf`**

UE: The app only recognizes the listed file extensions as valid GenBank files.

_Change the file extension and try resubmitting the job._&#x20;

#### **`XXX is not a valid KBase taxon ID`**

UE: The Taxonomy ID in the advanced parameters is optional and needs to be an integer when specified. The user provided the text string ‘XXX’.

_Use an integer taxon ID or leave it blank. The information will be picked up from the GenBank file or from the scientific name._

## [Import GFF3/FASTA file as Genome from Staging Area](https://narrative.kbase.us/#catalog/apps/kb\_uploadmethods/import\_gff\_fasta\_as\_genome\_from\_staging)

#### **`Every feature sequence id must match a fasta sequence id`**

UE: The IDs in the ‘sequence source’ lines must match the header lines in the FASTA file in the GFF format.&#x20;

_Correct the GFF format and try resubmitting the job._ &#x20;

#### **`unable to parse >.....`**

UE: The file may not be in GFF format.&#x20;

_Recheck the file format and try resubmitting the job._&#x20;

#### `Features must be completely contained within the Contig in the Fasta file.`

UE: The coordinates for the feature are outside the bounds of the contig.

&#x20;_Recheck the file where indicated and try resubmitting the job. In rare instances, the GFF file contains a feature that wraps around the 0 position and the coordinates look like the feature goes off the end of the sequence. The options are to 1) remove the feature from the GFF file, 2) edit the feature so that it is in two parts, or 3) find a GenBank formatted version of the file and resubmit._&#x20;

## [Import Media file (TSV/Excel) from Staging Area](https://narrative.kbase.us/#catalog/apps/kb\_uploadmethods/import\_tsv\_excel\_as\_media\_from\_staging)

#### **`Starch.csv" is not a valid EXCEL nor TSV file`**

UE: File format is not recognized.&#x20;

_Recheck the file format and try resubmitting the job._&#x20;

## [Import TSV/XLS/SBML File as an FBAModel from Staging Area](https://narrative.kbase.us/#catalog/apps/kb\_uploadmethods/import\_file\_as\_fba\_model\_from\_staging)

#### **`data file 4.xml either does not use commas or tabs as a separator`**

UE: File format is not recognized.&#x20;

_Recheck the file format and try resubmitting the job._&#x20;

#### **`No object with name _Nostoc_azollae__0708`**

UE: The genome does not exist in the narrative&#x20;

_Fix the genome name and try resubmitting the job._&#x20;

## [**Unpack a Compressed File in Staging Area**](https://narrative.kbase.us/#catalog/apps/kb\_uploadmethods/unpack\_staging\_file) ****&#x20;

#### `Error running command:pigz ...`&#x20;

UE: The file could not be unzipped by KBase and most likely couldn’t be unzipped by the user either.&#x20;

_Verify the file can be unzipped locally._&#x20;

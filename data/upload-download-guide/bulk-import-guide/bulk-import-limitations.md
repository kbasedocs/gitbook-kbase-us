---
description: >-
  This page contains a list of the most commonly observed bugs and known
  limitations to the bulk import process.
---

# Bulk Import Limitations

## Known Issues and Limitations

* Issue: Only a single set of parameters can be used for a given type in a given bulk import. 
  * Workaround: Subset your imports and run an app cell for each subset with a single set of parameters. Note that this only applies to different parameters within an import type. If you have a set of Illumina reads, PacBio reads, and assemblies, you can import one of the sets of reads and the assemblies in one import, and the other type of reads in a separate import.
* Issue: Staging Area allows uploading incomplete files, leading to data corruption.
  * Workaround: This is an existing issue in the staging area that exists for single-file imports as well. Ensure that your files have fully uploaded and the file size in the staging area matches the size of the file from your machine. You can use MD5 checksums to verify the file uploaded correctly. You can view the MD5 inside the staging area by viewing the info for the file, as shown in the screenshot below. Then, verify that the MD5 in the staging area matches the MD5 on your local machine using the following command depending on your operating system \(replacing "assembly\_1.fasta" with your file name\):
    * MacOS: `md5 assembly_1.fasta`  
    * Windows: `certutil -hashfile assembly_1.fasta md5`
    * Linux: `md5sum assembly_1.fasta` 

![](../../../.gitbook/assets/md5.png)

* Issue: Locating the job status for each import within the Bulk Import cell. 
  * Workaround: Some users have found it not immediately apparent how to view the job status. The status can be viewed within the Job Status tab of the App cell by clicking anywhere on the line for a child job to expand that job.
* Issue: Autofill for certain data types does not work. 
  * Workaround: Currently our implementation does not read files in a way to recognize pairs of files that go together, such as pairs of non-interleaved FASTQ files. During import these will need to be manually assigned to a forward or reverse read. 
* Issue: Logs/reports/status do not appear. 
  * Workaround: There have been infrequent bugs found in which logs failed to appear, jobs reported as successful but no report could be generated, and similar issues. Reloading the page has been found to fix all these issues so far.
* Issue: Bulk jobs allow overwriting existing objects. 
  * Workaround: The jobs should be reviewed prior to starting to ensure there are no duplicate names or no names that would overwrite existing objects. If it is discovered that an object has been incorrectly overwritten, the object can be reverted to the previous version.


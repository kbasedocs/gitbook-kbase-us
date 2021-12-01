# Bulk Import Guide

{% hint style="danger" %}
Bulk Import is undergoing user testing and not yet released.&#x20;
{% endhint %}

## How it works

The Staging Area has new features for importing data. The import type selection dropdown can detect the data type of the file based on its extension _where possible_. Some types will not automatically select, such as .fasta or .fastq. In these cases more than one importer can use the FASTA file extension. However, suggested importers will be listed at the top of the drop down under “Suggested Types.”&#x20;

For example, files with the extension FASTQ can import as a single interleaved file, as a pair of forward and reverse non-interleaved files to create a PairedEndLibrary, or as a single non-interleaved file to create a SingleEndLibrary.&#x20;

![Suggested Types for Importing Data into the Narrative](../../../.gitbook/assets/BulkImport\_SuggestedTypes.png)

To run bulk import, ensure all the files you want to import have an import type selected and the check box is active, then click "Import Selected."&#x20;

{% hint style="info" %}
Bulk import currently only supports _one parameter set per data type_. If you need to upload files of a given data type with different parameters, perform a separate set of bulk imports for each parameter set.
{% endhint %}

![](../../../.gitbook/assets/screen-shot-2021-08-04-at-11.37.27-am.png)

You’ll see a new import cell created for bulk imports. This cell contains a tab for each of the data types you selected from the Staging Area, which you can view by clicking on the available types within the Data type column on the left. This cell is a bulk wrapper for existing import apps, so you can fill out the parameters the same as you would for a single import.&#x20;

![Bulk Import App in the Narrative](<../../../.gitbook/assets/BulkImport\_missinginputs (1).png>)

Once you have filled out all file paths and parameters, you can then run the import. While the import is running you will still be able to see all the logs and status details in the Job Status tab, but arranged for the bulk import. You can expand each of the child jobs by clicking on the corresponding line to view details, then expand further to see the logs. When the bulk import cell is set to run, each child job for the individual data object will have a status, including Actions to cancel or retry individual jobs.

![Running Bulk Import App](../../../.gitbook/assets/BulkImport\_JobStatus.png)

Alternatively, queued and running jobs can be cancelled using the bulk action dropdown. Or the retry action can be used for multiple import jobs within the bulk import cell. &#x20;

![Bulk Action Dropdown](<../../../.gitbook/assets/BulkImport\_CancelRetryAll (1).png>)

When the jobs are completed successfully, you’ll be able to see all the information on the data object, repackaged for viewability in bulk. The first new feature is a table of all successful jobs. Clicking on object names adds a viewer widget to the Narrative. All the reports are available under the "Reports" tree. The full list is collapsed by default to conserve memory. The list can be expanded to show each report, and each report can be viewed in a separate window.&#x20;

![Result tab of the Bulk Import Cell](../../../.gitbook/assets/BulkImport\_ResultObject.png)

## What data types does this apply to?

While this will be applicable to all data types and file extensions in the future, bulk import currently supports the following:

* Assembly - FASTA
* SRA Reads&#x20;
* FASTQ Reads Interleaved - FASTQ Interleaved reads
* FASTQ Reads Noninterleaved - FASTQ paired-end reads or FASTQ single-end reads library
* GenBank Genome - GenBank
* GFF Metagenome - FASTA and GFF3

{% hint style="warning" %}
When selected files are not supported data types for Bulk Import within the Staging Area, separate, single import app cells will open in the Narrative for each type and file.
{% endhint %}

## What are the limitations?

This is a new feature in KBase, and the current release should be considered a beta version with future development still to come. Some of the most notable limitations are listed here. This is not a comprehensive list but does contain the known bugs, issues, and limitations that are the highest priority for future releases.&#x20;

View [common bugs and limitations](bulk-import-limitations.md).&#x20;


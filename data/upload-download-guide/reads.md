---
description: Formatting and uploading FASTQ and SRA reads files.
---

# FASTQ/SRA Reads

In KBase, reads from FASTQ and SRA files can be imported to create reads library data objects. The objects will either be a SingleEndLibrary or a PairedEndLibrary. The tools in KBase can then be used to assemble reads into an “Assembly” data object or to align reads to an “Assembly." After uploading and importing reads data, you may want to refer to the documentation about [Assembly and Annotation](../../apps/analysis/assembly-and-annotation.md). Reads can also be used in [RNA-seq and expression analysis](../../apps/analysis/expression.md).

{% hint style="info" %}
Single-end and paired-end reads can be uploaded in FASTQ or SRA format. For FASTQ files, please ensure that your filename ends with the .fastq, .fnq, or .fq file extension. SRA files should have the .sra file extension. The uploader also accepts compressed files in .zip, .gz, .bz2, .tar.gz, .tar.bz2 formats.
{% endhint %}

Files can be uploaded into your KBase Staging Area from your local computer or directly from a publicly accessible FTP or HTTP URL.

## Importing reads from your computer

### Single-end library in FASTQ or SRA format

Using a file on your computer, open the [_Import_ tab within the **Data Browser**](../../getting-started/narrative/add-data.md)**.** Then drag & drop the single-end library into your Staging Area. Open the pulldown menu to the right of the filename in the Staging Area and select “FASTQ Reads" or "SRA Reads."

![](../../.gitbook/assets/FASTQreads\_staging\_import.png)

Now click the import icon (up arrow) to the right of data type selection. The slide-out Data Browser will close and an app called “Import FASTQ/SRA File as Reads from Staging Area” will be added to your Narrative.

Notice that the name of the Reads Library file is already filled in, as is a suggested Reads Object Name that will be created by the import (you can change that if you like). Adjust the Sequencing Technology and any of the advanced options if needed. Note that this was a metagenomic sample, we would _uncheck_ the box next to Single Genome. When ready, click the green "Run" button to start the import. When the import is finished, your Data Panel will update to show the new SingleEndLibrary object, and a report will appear in the import app cell.

### Paired-end library in FASTQ format

There are two ways that KBase and [GenBank SRA](https://www.ncbi.nlm.nih.gov/sra/docs/submitformats/) recognize a paired-end library. A paired-end library can be either two files which typically have the same name and are designated as forward and reverse or is interleaved. Interleaved files use an 8-line format where forward and reverse reads alternate.

Open the __ [_Import_ tab in the **Data Browser**](../../getting-started/narrative/add-data.md#uploading-data-from-external-sources) and drag either one interleaved file or two paired files into the Staging Area.

Open the pulldown menu to the right of the filename under the _Import As..._ column in your Staging Area and select “FASTQ Reads” for the first file in the pair. Then click the import icon (up arrow) to the right of “FASTQ Reads”. The Data Browser slide-out will close and the “Import FASTQ/SRA File as Reads from Staging Area” App will open.

Notice that the name of the FASTA/FASTQ file is filled in. A suggested Reads Object Name is also created by the import and can be changed.

If the files are two paired file, you will need to select a file for “Reverse/Right FASTA/FASTQ File Path” from the dropdown.

![Paired-end or non-interleaved FASTQ Import](../../.gitbook/assets/paired\_end\_import.png)

As with the single-end library example, you can make adjustments to the available parameters. Adjust the Sequencing Technology and any of the advanced options if needed. If the file is an interleaved paired-end library, check the box to the right of Interleaved.

![Interleaved FASTQ Import](../../.gitbook/assets/FastQ\_interleaved.png)

When ready, click the green "Run" button to start the import. When the import is finished, your Data Panel will update to show the new PairedEndLibrary object, and a report will appear in the Import App.

## Importing a reads library from other sources

In the Staging Area, beneath the box for Drag and Drop, there are other options for adding data to your staging area. You can import reads into KBase using [Globus Online](../globus.md), or by supplying a URL for a publicly accessible FTP location, Google Drive, Dropbox, or a direct HTTP link.

![](<../../.gitbook/assets/Staging\_Upload options.png>)

If your reads are in a publicly accessible URL, you can bypass the Staging Area and directly import reads into your Narrative using one of these three apps (which you can find in the Apps panel or the [App Catalog](https://kbase.us/applist/)):

* [Import SRA File as Reads From Web](https://narrative.kbase.us/#catalog/apps/kb\_uploadmethods/import\_sra\_as\_reads\_from\_web/release)
* [Import Single-End Reads From Web](https://narrative.kbase.us/#catalog/apps/kb\_uploadmethods/load\_single\_end\_reads\_from\_URL/release)
* [Import Paired-End Reads From Web](https://narrative.kbase.us/#catalog/apps/kb\_uploadmethods/load\_paired\_end\_reads\_from\_URL/release)

### **Drag & Drop Limitations**

The drag & drop from your local computer works for many files, but there is a size limit that depends on your computer and browser. Some users have reported problems around 20GB. For larger files, use [Globus Online transfer](../globus.md).

### Bulk Import

FASTQ and SRA reads can be imported as one of the supported bulk import types. You can select multiple assemblies simultaneously from the staging area to import them at once. See the bulk import section of [the guide to importing data into the Narrative.](https://docs.kbase.us/getting-started/narrative/add-data)

## **Transfer reads from JGI**

If you are a JGI user, you can transfer public genome reads and assemblies (as well as your private data and annotated genomes) from JGI to your KBase account—see [this page](../jgi-transfer.md) for instructions.

## ****

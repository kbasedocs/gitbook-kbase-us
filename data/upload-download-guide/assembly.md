---
description: How to upload FASTA files into KBase.
---

# Assembly

{% hint style="info" %}
An assembly file is a single file containing one or more contiguous DNA sequences in FASTA format. It can be uploaded to KBase from your local computer (with file extension .fasta, .fna, .fa, or .fas) or directly from a publicly accessible FTP or HTTP URL.&#x20;
{% endhint %}

“Assembly” is the KBase data type for assembled, unannotated DNA sequence contigs. If you want to upload annotated sequences in GenBank or GFF format, please see the [Genome](genome.md) page.

![](../../.gitbook/assets/Assembly\_Import.gif)

## Importing an Assembly from your computer

Using a file on your computer, open the [_Import_ tab within the **Data Browser**](../../getting-started/narrative/add-data.md)**.** Then drag & drop the assembly file into the Staging Area box or select from your computer files.

Open the _Import As_ pulldown menu to the right of the filename in your Staging Area and select “Assembly.”

![Import Fasta Assembly File](../../.gitbook/assets/Import\_fasta\_assembly.png)

Make sure the correct file type is selected and the checkbox is active, then click the “Import Selected” button. The data slide-out will close and an app called “Import FASTA File as Assembly from Staging Area” will be added to your Narrative.

![Import Assembly / FASTA file Import App Cell](../../.gitbook/assets/Assembly\_AppCell\_import.png)

The name of the Assembly file is filled in, as is a suggested name for the Assembly data object that will be created by the import (you can change the Assembly object name). Adjust the minimum contig length if needed and then click the green "Run" button to start the import. When the import is finished, your Data Panel will update to show the new Assembly object, and a report will appear in the Import App.

## Upload an Assembly from other sources

You can upload data into your KBase Staging Area using [Globus](../globus.md), or by supplying a URL for a publicly accessible FTP location, Google Drive, Dropbox, or a direct HTTP link to import into the Narrative. Options for adding data to your Staging Area are described [here](../../getting-started/narrative/add-data.md).

![Drag and Drop, Upload with Globus, Upload with URL options to upload and import data into KBase](<../../.gitbook/assets/Staging\_Upload options.png>)

### **Drag & Drop Limitations**

The drag & drop option from your local computer works for many files, but there is a size limit that depends on your computer and browser. For larger files (around 20GB), use [Globus Online transfer](../globus.md).&#x20;

### Bulk Import

Assemblies can be imported as one of the supported bulk import types. You can select multiple assemblies simultaneously from the staging area to import them at once. See the bulk import section of [the guide to importing data into the Narrative.](https://docs.kbase.us/getting-started/narrative/add-data)

## Transfer assemblies from JGI

If you are a JGI user, you can transfer public genome reads and assemblies (as well as your private data and annotated genomes) from JGI to your KBase account—see [this page](../jgi-transfer.md) for instructions.

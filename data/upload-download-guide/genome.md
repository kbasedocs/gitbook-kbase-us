---
description: >-
  Formatting and uploading annotated assemblies and GenBank or GFF and FASTA
  files.
---

# Genome

In KBase, a **Genome object is the annotated version of an Assembly** and can encompass several types of feature calls. If you want to upload solely the DNA sequence from a FASTA file (without annotations), go to the [Assembly](assembly.md) page.

{% hint style="info" %}
The Genome importer supports only GenBank and GFF formatted files.&#x20;

A GenBank-formatted input file should include sequence contig(s), feature calls (annotations), and taxonomy information for the organism. KBase parses the input file into two data objects: an assembly object with the sequence and a genome object containing the original feature calls and annotations.

GenBank-formatted files with no features can be uploaded as Genomes.

A _GenBank-formatted_ file can be uploaded into the Staging Area from your local computer (files with.gb, .gbff, or .gbk extensions) or directly from an FTP or HTTP URL.
{% endhint %}

{% hint style="warning" %}
A _GFF-formatted_ file must be paired with a **corresponding FASTA file** of the DNA sequence. These  will be parsed into two data objects: an assembly object with the sequence and a genome object containing the original feature calls and annotations.
{% endhint %}

Further instructions for adding data to your Staging Area can be found [here](../../getting-started/narrative/add-data.md#uploading-data-from-external-sources).

## Importing a GenBank-formatted genome

Using a file on your computer, open the [_Import_ tab within the **Data Browser**](../../getting-started/narrative/add-data.md)**.** Then drag & drop the genome file into your Staging Area.&#x20;

Open the _Import As..._ pulldown menu to the right of the filename in your Staging Area and select “GenBank Genome.”

Click the import icon (up arrow) to the right of “GenBank Genome.”&#x20;

![](../../.gitbook/assets/GenBank\_Staging\_import.png)

The Data Browser will close and the “Import GenBank File as Genome from Staging Area” App will be added to your Narrative.

Notice that the name of the Genome file is filled in, as is a suggested name for the Genome and Assembly data objects that will be created by the import, which _can_ be changed. Adjust the Genome Type and source of the GenBank file or any advanced parameters if needed.&#x20;

![Import GenBank Genome App](<../../.gitbook/assets/GenBank\_Import (1).gif>)

Click the green "Run" button to start the import. When the import is finished, your **Data Panel** will update to show the new Genome and Assembly objects, and a report will appear in the Import App.

## Importing a GFF-formatted Genome

Open the __ [_Import_ tab in the **Data Browser**](../../getting-started/narrative/add-data.md) and drag and drop _both_ the genome _and_ corresponding FASTA file into your Staging Area. In your Staging Area, open the _Import As..._ pulldown menu to the right of the GFF filename and select “GFF Genome."

![Importing a GFF and FASTA Genome from the Staging Area](../../.gitbook/assets/GFF\_staging\_import.png)

Note the name of the corresponding FASTA file.

Now click the import button (up arrow) to the right of “GFF Genome”. The data slide-out will close and the “Import GFF/FASTA File as Genome from Staging Area” App will be added to your Narrative. The GFF File Path name will be filled in.

You will need to fill in the name of the FASTA file. Using the dropdown for the “FASTA File Path”, select the FASTA file in the Staging Area. Ensure the file type is a FASTA file type.&#x20;

![GFF/FASTA Genome Import](../../.gitbook/assets/GFF\_FASTA\_Genome\_import.png)

The name of the Scientific Name may be filled in, as is a suggested name for the Genome data object that will be created by the import. You can edit the name of the output Genome Object Name, Scientific Name, and any advanced options as needed. Click the green "Run" button. When the import is finished, your Data Panel will update to show the new Genome object, and a report will appear in the Import App.

## Uploading a Genome from other sources

You can upload data into your KBase Staging Area using [Globus](../globus.md), or by supplying a URL for a publicly accessible FTP location, Google Drive, Dropbox, or a direct HTTP link to import into the Narrative. Options for adding data to your Staging Area are described [here](../../getting-started/narrative/add-data.md).

![Drag and Drop, Upload with Globus, Upload with URL options to upload and import data into KBase](<../../.gitbook/assets/Staging\_Upload options.png>)

### **Drag & Drop Limitations**

The drag & drop option from your local computer works for many files, but there is a size limit that depends on your computer and browser. For larger files (around 20 gigabases), use the [Globus Online transfer](../globus.md).&#x20;

### Bulk Import

Both GenBank and GFF genomes can be imported as one of the supported bulk import types. You can select multiple assemblies simultaneously from the staging area to import them at once. See the bulk import section of [the guide to importing data into the Narrative.](https://docs.kbase.us/getting-started/narrative/add-data)&#x20;

## Uploading a Genome using a URL&#x20;

Open the __ [_Import_ tab in the **Data Browser**](../../getting-started/narrative/add-data.md) and click on the _Upload with URL_ button (below the drag & drop area) to open an Upload App Cell.

The Data Browser will close and the “Upload a File to Staging from Web” App will appear in your Narrative. Alternatively, you can open the app directly from the **Apps Panel**. From the app, click on the dropdown for the URL Type and select the URL type.

![Upload File to Staging from Web App](../../.gitbook/assets/UploadwithURL\_app.png)

{% hint style="info" %}
When uploading a GenBank Genome, you will only need to use one link. When uploading a GFF Genome, you will need to use two links for the GFF file and the FASTA file.&#x20;
{% endhint %}

In the App, click the "+" button for the URLs and paste in the name of the Genome file (GenBank or GFF). Hit the "+" button again and paste in the name of the FASTA file.

Then click the green "Run" button to start the upload. After the App completes the files will appear in your Staging Area, which you can access via the _Import_ tab in the **Data Browser**.

The genome file(s) are now in your Staging Area. Now you need to import them to your Narrative to use them in analyses.

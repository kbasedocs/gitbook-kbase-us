---
description: Generating and handling Amplicon Matrices to link to Samples
---

# Amplicon Matrix

## Formatting Amplicon Matrix files

Any approach to creating an amplicon matrix should be usable in KBase, but may require additional curation. Amplicon matrices or taxonomic abundance matrices include OTU (operational taxonomic units) and ASV (amplicon sequence variants).&#x20;

We recommend to upload raw counts as analysis ([rarefaction, standardization, and normalization](../../apps/analysis/amplicon-data-matrices.md)) will be tracked and provenance maintained on system. There are a number of [tools in KBase to analyze Amplicon Matrices and metadata](../../apps/analysis/amplicon-data-matrices.md).&#x20;

{% hint style="info" %}
Amplicon matrices can be uploaded from a TSV (tab-separated values) file with a .tsv file extension.

When uploading, ensure that **rows are taxa** and **columns are samples**. A _column for taxonomy is optional_.

Consensus sequences must also be included as a FASTA file with extension .fa, .fasta. Sequence names **must match **_**exactly**_** ** with the taxa names in the amplicon matrix.&#x20;
{% endhint %}

Two files are _needed_ for uploading amplicon data:

* _FASTA file_ with consensus sequences
* _Taxonomic abundance matrix_ (OTU or ASV)&#x20;
  * row = taxon
  * column = sample
  * optional column = taxonomy

Additional information to have on hand for parameters include:

* _Sample processing metadata_ (SampleSet), i.e. sequencing technology or platform, target gene or region
* _Bioinformatic processing metadata,_ i.e. clustering method, quality filtering steps

## Uploading and Importing

Amplicon Matrices can be uploaded into KBase without linking metadata. For full functionality of analysis tools using metadata, first [upload and import the SampleSet](sampleset.md).&#x20;

Using a file on your computer, open the [_Import_ tab within the **Data Browser**](../../getting-started/narrative/add-data.md)**.** Then drag & drop the amplicon matrix file **and** the FASTA file with consensus sequences into the Staging Area.

Once the files are in your Staging Area, you can import the data into your Narrative.

Go to the APPS panel and open the Upload category to locate the "Import Amplicon Matrix from TSV/FASTA File in Staging Area" App. Click on the Import Amplicon App to add it to your Narrative.&#x20;

![Import Amplicon Matrix from TSV/FASTA File in Staging Area. Double click to view. ](../../.gitbook/assets/AmpliconMatrix\_import.png)

In the first section for Input Objects, select the previously imported SamplesSet file from the dropdown menu for linking metadata.&#x20;

Under Parameters, select the Amplicon Matrix or Taxonomic Abundance TSV file using the dropdown and then the corresponding sequences FASTA file.&#x20;

Parameters that _require_ _inputs_ are the target gene, target subfragment, taxon calling method, i.e. denoising or clustering, and sequence error cutoff.&#x20;

Additional processing metadata, i.e. primer sequences, library kit, sequencing center, the denoise or clustering methods can be input by clicking "show advanced" parameters. While these parameters are not required, they are recommended to enhance workflow documentation and reproducibility.&#x20;

Fill in the Amplicon Matrix Object Name and click the "Run" button.&#x20;

Once your amplicon matrix is imported into the Narrative, you can use the "View Matrix as Table" App to view your new AmpliconMatrix object. &#x20;

{% file src="../../.gitbook/assets/amplicon_example.zip" %}
Example of test amplicon matrix with consensus FASTA
{% endfile %}

The amplicon matrix may be applied to an existing [SampleSet](sampleset.md) and [Attribute Mapping](https://narrative.kbase.us/#catalog/apps/kb\_uploadmethods/import\_attribute\_mapping\_from\_staging/beta) on-system to facilitate the interoperability of objects in KBase.&#x20;

## Tutorial Webinar

{% embed url="https://youtu.be/w7y23FC5JUc?t=573" %}
Importing Samples and Amplicon
{% endembed %}

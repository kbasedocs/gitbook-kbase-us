---
description: >-
  Metabolomics, exometabolite, and chemical abundance data can be integrated
  with metabolic modeling and flux balance analysis tools in KBase.
---

# Chemical Abundance Matrix

Once chemical abundance data matrices are [uploaded](chemical-abundance-matrix.md#uploading-and-importing), they can be analyzed using [KBase Apps for metabolomics](../../apps/analysis/metabolic-modeling.md#metabolomics), such as Escher mapping. Additional statistical analysis of the chemical abundance attribute maps, such as PCA and clustering, can also be performed.

{% hint style="info" %}
A Chemical Abundance Matrix can be uploaded from a TSV (tab-separated values) file with a .tsv or .tab file extension, or from Excel spreadsheet with a .xls extension.

Each Chemical Type can be either a specific compound, aggregate (totals), exometabolites (measurements of compounds that are consumed or excreted into the medium).&#x20;
{% endhint %}

## Formatting chemical abundance matrices

The [Create Chemical Abundance Matrix Template App](https://kbase.us/applist/apps/GenericsAPI/build\_chemical\_abundance\_template/release) creates an Excel spreadsheet for direct download that can be populated with chemical abundance data. Chemical abundance data works best with an [existing SampleSet](sampleset.md).&#x20;

If a SampleSet exists, it can be applied to the chemical abundance data. Chemical abundance data needs to be formatted to ensure Samples are correctly linked.

![Create Chemical Abundance Matrix Template](../../.gitbook/assets/ChemicalAbundanceMatrix\_create.png)

This App generates a spreadsheet onto which you can copy your data to ensure it links to the SampleSet when uploaded.&#x20;

Select chemical data to include, such as aggregate M/Z, compound name, predicted formula, and more, depending on what data you have for upload. Also select which chemical IDs to include in the template from [KEGG](https://www.genome.jp/kegg/compound/), [ChEBI](https://www.ebi.ac.uk/chebi/), and [ModelSEED](https://modelseed.org/biochem/compounds) databases.&#x20;

## Uploading and Importing

&#x20;For full functionality of analysis tools using metadata, first [upload and import the SampleSet](sampleset.md).&#x20;

Once you have added and [formatted](../samples/ontology.md) your data to the Chemical Abundance Matrix template, you can upload it using the [Import Chemical Abundance Matrix from CSV/Excel/TSV File in Staging Area App](https://narrative.kbase.us/#catalog/apps/GenericsAPI/import\_chemical\_abundance/release).&#x20;

Using a file on your computer, open the [_Import_ tab within the **Data Browser**](../../getting-started/narrative/add-data.md)**.** Then drag & drop the chemical abundance matrix file into the Staging Area.

Once the matrix is in your Staging Area, you can import the data into your Narrative.

![Import Chemical Abundance Matrix](../../.gitbook/assets/ChemicalAbundanceMatrix\_import.png)

In the first section for Input Objects, select the previously imported SamplesSet file from the dropdown menu for linking metadata.&#x20;

Under Parameters, select the Chemical Abundance Matrix using the FilePath dropdown.&#x20;

Fill in the Matrix Object Name and click the "Run" button to add the metabolomics data to the Narrative.

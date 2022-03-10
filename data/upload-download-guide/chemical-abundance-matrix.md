---
description: >-
  Metabolomics, exometabolite, and chemical abundance data can be integrated
  with metabolic modeling and flux balance analysis tools in KBase.
---

# Chemical Abundance Matrix

## What is "chemical abundance" in KBase?

We use the term "chemical abundance" as a name for our data type in KBase, but it encompasses a wide array matrices. In short, any spreadsheet containing a element, compound, exometabolite abundance per sample can be uploaded as a chemical abundance matrix. This can include data from multiple types of MS instrument as well as data collected on the concentration or amount of compounds or elements. These data could be collected on environmental samples, such as soil or water, or from lab experiments looking at metabolomics.

Once chemical abundance data matrices are [uploaded](chemical-abundance-matrix.md#uploading-and-importing), they can be analyzed using [KBase Apps for metabolomics](../../apps/analysis/metabolic-modeling.md#metabolomics), such as Escher mapping. Additional statistical analysis of the chemical abundance attribute maps, such as PCA and clustering, can also be performed.

{% hint style="info" %}
A Chemical Abundance Matrix can be uploaded from a TSV (tab-separated values) file with a .tsv or .tab file extension, or from Excel spreadsheet with a .xls extension.

Each Chemical Type can be either a specific compound or element, aggregate (totals), exometabolites (measurements of compounds or elements that are consumed or excreted into the medium).&#x20;
{% endhint %}

## Formatting chemical abundance matrices

The minimal set of metadata in a chemical abundance matrix includes an ID field, a chemical type (aggregate, exometabolite, specific, etc), and one or more of the following: database ID, mass, formula, inchikey, inchistring, smiles, or compound name. Additional metadata are strongly encourage to provide more information for readers, but the columns are not validated so you are able enter the values as free text in whatever manner fits your uses.

The [Create Chemical Abundance Matrix Template App](https://kbase.us/applist/apps/GenericsAPI/build\_chemical\_abundance\_template/release) creates an Excel spreadsheet for direct download that can be populated with chemical abundance data. Chemical abundance data works best with an [existing SampleSet](sampleset.md).&#x20;

If a SampleSet exists, it can be applied to the chemical abundance data. Chemical abundance data needs to be formatted to ensure Samples are correctly linked.

![Create Chemical Abundance Matrix Template](../../.gitbook/assets/ChemicalAbundanceMatrix\_create.png)

This App generates a spreadsheet onto which you can copy your data to ensure it links to the SampleSet when uploaded.&#x20;

When creating the chemical abundance template, there are 10 columns in the default sheet shown in the sheet below. Column headings in italics come pre-filled with validated values to choose form a dropdown.

| Column Heading          | Description                                                                                                                                            |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ID (unique value)       | The identifier for the chemical or compound. This can be user-defined but must be unique for each compound.                                            |
| _Chemical Type_         | specific, aggregate, or exometabolite                                                                                                                  |
| _Measurement Type_      | unknown, FTICR, Orbitrap, Quadrapole                                                                                                                   |
| _Units_                 | mg/Kg, g/Kg, mg/L, mg/g DW, mM (millimolar), M (molar), % (percentage), Total Weight  %, unknown                                                       |
| _Unit Medium_           | soil, solvent, water                                                                                                                                   |
| Chemical Ontology Class | Used for grouping chemicals by their functional groups (e.g; aromatics) or could use according to ontologies defined in public databases (e.g; ChEBI). |
| _Chromatography Type_   | unknown, HPLC, MS/MS, LCMS, GS                                                                                                                         |
| Chemical Class          | Used for defining major classes like lanthanides                                                                                                       |
| Protocol                | Any term or sentence defining the protocol used in your lab                                                                                            |
| Identifier              | Identifier for the compound or element                                                                                                                 |



Select chemical data to include, such as aggregate M/Z, compound name, predicted formula, and more, depending on what data you have for upload.&#x20;

| Column Heading                  | Description                                                                                             |
| ------------------------------- | ------------------------------------------------------------------------------------------------------- |
| Aggregate M/Z                   | The ratio of mass to net charge of the chemical                                                         |
| Compound Name                   | Optional name for the compound                                                                          |
| Predicted Formula               | Predicted formula for the compound                                                                      |
| Predicted Structure (smiles)    | Predicted structure using Simplified Molecular Input Line Entry System (SMILES) notation                |
| Predicted Structure (inchi-key) | Predicted structure using International Chemical Identifier (InChi) key notation.                       |
| Theoretical Mass                | Theoretical molecular mass of the compound                                                              |
| Retention Time                  | The retention time of the chemical; not validated, so users can include units or not depending on needs |
| Polarity                        | Polarity of the chemical.                                                                               |

Finally, select at least one form of standard Chemical IDs to include in the template. These can be selected from the [KEGG](https://www.genome.jp/kegg/compound/), [ChEBI](https://www.ebi.ac.uk/chebi/), and [ModelSEED](https://modelseed.org/biochem/compounds) databases. You can use their respective websites to get the identifier for your compound. If you are creating a chemical abundance sheet from scratch, you don't have to include one of these chemical IDs, but it is recommended that you do so in order to compare similar chemical once uploaded.

## Uploading and Importing

&#x20;For full functionality of analysis tools using metadata, first [upload and import the SampleSet](sampleset.md).&#x20;

Once you have added and [formatted](../samples/ontology.md) your data to the Chemical Abundance Matrix template, you can upload it using the [Import Chemical Abundance Matrix from CSV/Excel/TSV File in Staging Area App](https://narrative.kbase.us/#catalog/apps/GenericsAPI/import\_chemical\_abundance/release).&#x20;

Using a file on your computer, open the [_Import_ tab within the **Data Browser**](../../getting-started/narrative/add-data.md)**.** Then drag & drop the chemical abundance matrix file into the Staging Area.

Once the matrix is in your Staging Area, you can import the data into your Narrative.

![Import Chemical Abundance Matrix](../../.gitbook/assets/ChemicalAbundanceMatrix\_import.png)

In the first section for Input Objects, select the previously imported SamplesSet file from the dropdown menu for linking metadata.&#x20;

Under Parameters, select the Chemical Abundance Matrix using the FilePath dropdown.&#x20;

Fill in the Matrix Object Name and click the "Run" button to add the metabolomics data to the Narrative.

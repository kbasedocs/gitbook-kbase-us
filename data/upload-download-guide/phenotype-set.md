---
description: >-
  The Phenotype Set data type represents experimental data about an organism’s
  ability to grow in specific media conditions, recorded as growth or no growth.
---

# Phenotype Set

## **Formatting Phenotype files**

{% hint style="info" %}
A Phenotype Set can be uploaded from a TSV (tab-separated values) file with a .tsv or .tab file extension, or from Excel spreadsheet with a .xls extension. The spreadsheet needs to have exactly these five columns:

* **Gene knockout (geneko)** – List of genes knocked out in the phenotype; use 'none' for wild-type phenotypes. Gene IDs should be in the same format that appears in your metabolic model (e.g., kb|g.220339.CDS.2927)
* **Workspace information (mediaws)** – Workspace where the media for the phenotype data was loaded into KBase. The workspace information can be found in the Narratives tab by clicking _Show Advanced Controls_ at the end of the list of Narratives
* **Media** – ID of the media condition loaded in KBase where the phenotype was observed.
* **Additional Compounds (addtlCpd)** – Additional media compound IDs to be added alongside the primary media formulation. See the [KBase ModelSEED Biochemistry Database ](https://github.com/ModelSEED/ModelSEEDDatabase/tree/v1.0/Biochemistry)for a reference list of reactions and compounds or use [Biochemistry Search](https://narrative.kbase.us/#biochem-search).
* **Growth** – Indication of whether or not the organism grew in the specified media with the specified knockouts. 1 meaning growth; 0 meaning no growth.
{% endhint %}

| geneko   | mediaws    | media       | addtlCpd | growth |
| -------- | ---------- | ----------- | -------- | ------ |
| SO\_0009 | KBaseMedia | C-D-Glucose |          | 0      |
| SO\_0009 | KBaseMedia | C-D-Lactate |          | 1      |
| SO\_0009 | KBaseMedia | C-acetate   |          | 1      |

To download an example phenotype set data table, go to the "Example" tab in the data Data Browser slide-out, add a Phenotype Data Object to the Narrative and download the TSV file.&#x20;

![Example Data Objects](../../.gitbook/assets/PhenotypeSet\_example.png)

## Importing a Phenotype Set

First [add the Genome](genome.md) that corresponds to referenced in the Phenotype Set. Add the Genome object to the Narrative before importing the Phenotype Set file.

Using a file on your computer, open the [_Import_ tab within the **Data Browser**](../../getting-started/narrative/add-data.md)**.** Then drag & drop the phenotype set file into your Staging Area. Open the pulldown menu to the right of the filename in the Staging Area and select “Phenotype Set."&#x20;

![Importing a Phenotype Set from the Staging Area](../../.gitbook/assets/PhenotypeSet\_StagingArea.png)

Click the import icon (up arrow) to the right of “Phenotype Set”. The data slide-out will close and the “Import TSV File as Phenotype Set From Staging Area” App will be added to your Narrative.

Notice that the name of the Phenotype TSV file is already filled in, as is a suggested name for the Phenotype Set data object that will be created by the import, which you can edit.

![Import Phenotype Set App](../../.gitbook/assets/PhenotypeSet\_Import.png)

Add the name of the Genome, click on the dropdown to select the corresponding genome that you added to your Narrative earlier.

Click the green "Run" button to start the import. When the import is finished, your Data Panel will update to show the new Phenotype Set object, and a report will appear in the Import App.

### **Drag & Drop Limitations**

The drag & drop from your local computer works for many files, but there is a size limit that depends on your computer and browser. For larger files around 20GB, use the [Globus Online transfer](../globus.md).

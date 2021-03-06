---
description: >-
  How to format reaction media files for KBase to use in FBA and modeling
  analysis.
---

# Media

KBase offers several options for defining specific growth or culture media for metabolic modeling. Within the Narrative Interface, you can use the [Edit Media](https://kbase.us/applist/apps/fba_tools/edit_media/release) tool to build media based on the hundreds of conditions available in KBase. You also can import your own custom media as a TSV or Excel file using the instructions below.

## Formatting Media TSV or Excel files

If you choose to upload a custom media or use media from an external source, please ensure that it is formatted properly for use with KBase. Media can be uploaded as a TSV \(tab-separated values\) or Excel file with four columns:

* **Compound identifier** \(e.g., ModelSEED ID, KEGG ID, PubChem ID, or compound name such as “glucose”\)
* **Concentration** \(concentration of compound in mol/L\)
* **Minflux** \(minimum allowed uptake/excretion of compound\)
* **Maxflux** \(maximum allowed uptake/excretion of compound\)

A list of all the biochemical _compounds_ is available in the [KBase ModelSEED Biochemistry Database ](https://github.com/ModelSEED/ModelSEEDDatabase/tree/v1.0/Biochemistry)for a reference list of reactions and compounds or use the [Biochemistry Search](https://narrative.kbase.us/#biochem-search). From the list you can find the IDs for compounds to include in custom media.

The _concentration_ field is not used by any of the the metabolic modeling tools in KBase. It is best to account for these values accurately so that your media files will retain their utility pending updates.

The _minflux_ and _maxflux_ columns connect media to a flux balance analysis \(FBA\) metabolic model. The values in these columns are absolute units representing the range of possible fluxes for reactions that transport the media compounds into and out of the cell. A negative flux value corresponds to excretion \(transport out of the cell\), and a positive flux value corresponds to uptake \(transport into the cell\). 

The combination of maximum and minimum flux will dictate whether uptake and/or excretion of a reagent is allowed. Assigning a positive number to _minflux_ for a particular compound essentially forces uptake of that compound. Conversely, assigning a negative number to _maxflux_ will force excretion of the compound.

Minimum and maximum flux are measured in mmol per gram cell dry weight per hour.

Note: ****When creating a media Excel file, the name of the worksheet that contains your media conditions **must** be named “MediaCompounds” or it will not upload. By default, the first sheet of any Excel file is called “Sheet1.” To rename it, find the worksheet tabs at the bottom left of the Excel file. Double-click on the default name and type in “MediaCompounds.”

Below is an example of a media file in TSV format. In this case, the compound IDs in the first column are from the [KBase ModelSEED Biochemistry Database](https://github.com/ModelSEED/ModelSEEDDatabase/tree/v1.0/Biochemistry):

| compounds | name | formula | minflux | maxflux | concentration |
| :--- | :--- | :--- | :--- | :--- | :--- |
| cpd00149 | Co2+ | Co | -100 | 100 | 0.001 |
| cpd00099 | Cl- | Cl | -100 | 100 | 0.001 |
| cpd00063 | Ca2+ | Ca | -100 | 100 | 0.001 |
| cpd00007 | O2 | O2 | -100 | 10 | 0.001 |
| cpd00027 | D-Glucose | C6H12O6 | -100 | 5 | 0.001 |

## Import media from a TSV or Excel file

For this example, you can click on either link to download a small media file onto your computer:

{% file src="../../.gitbook/assets/glucose\_minimal \(1\).xls" caption="Example Excel file" %}

{% file src="../../.gitbook/assets/glucose\_minimal.tsv" caption="Example TSV file" %}

Open the[ _Import_ tab](../../getting-started/narrative/add-data.md#uploading-data-from-external-sources) in the Data Browser and drag & drop your media file to upload it to your staging area

* Choose "Media" from the _Import As..._ data type dropdown menu in your Staging Area
* Click the upload icon next to the field that now says “Media”
* An app called “Import Media file \(TSV/Excel\) from Staging Area” will be added to your Narrative

![](../../.gitbook/assets/importmediafilefromstaging_run%20%281%29.png)

* You can change the name that will be assigned to the Media Object if you want. Then click the green "Run" button.
* After the import process has completed, the Media data object will appear in your Data Panel

## 


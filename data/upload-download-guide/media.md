---
description: >-
  How to format reaction media files for KBase to use in FBA and modeling
  analysis.
---

# Media

KBase offers several options for defining specific growth or culture media for metabolic modeling. Within the Narrative Interface, you can use the [Edit Media](https://kbase.us/applist/apps/fba\_tools/edit\_media/release) tool to build media based on the hundreds of conditions available in KBase or import your own custom media as a TSV or Excel file using the instructions below.

## Formatting Media TSV or Excel files

If you choose to upload a custom media or use media from an external source, please ensure that it is formatted properly for use with KBase.&#x20;

{% hint style="info" %}
Media can be uploaded as a TSV (tab-separated values) or Excel file using four columns:

* **Maxflux** (maximum allowed uptake/excretion of compound)
* **Minflux** (minimum allowed uptake/excretion of compound)
* **Concentration** (concentration of compound in mol/L)
* **Compound identifier** (e.g., ModelSEED ID, KEGG ID, PubChem ID, or compound name such as “glucose”)
{% endhint %}

A list of all the biochemical _compounds_ is available in the [KBase ModelSEED Biochemistry Database ](https://github.com/ModelSEED/ModelSEEDDatabase/tree/v1.0/Biochemistry)for a reference list of reactions and compounds or use the [Biochemistry Search](https://narrative.kbase.us/#biochem-search). From the list you can find the IDs for compounds to include in custom media.

The _concentration_ field is not used by any of the the metabolic modeling tools in KBase. It is best to account for these values accurately so that your media files will retain their utility pending updates.

The _minflux_ and _maxflux_ columns connect media to a flux balance analysis (FBA) metabolic model. The values in these columns are absolute units representing the range of possible fluxes for reactions that transport the media compounds into and out of the cell. A negative flux value corresponds to excretion (transport out of the cell), and a positive flux value corresponds to uptake (transport into the cell).&#x20;

The combination of maximum and minimum flux will dictate whether uptake and/or excretion of a reagent is allowed. Assigning a positive number to _minflux_ for a particular compound essentially forces uptake of that compound. Assigning a negative number to _maxflux_ will force excretion of the compound.

Minimum and maximum flux are measured in mmol per gram cell dry weight per hour.

Note: **** When creating a media Excel file, the name of the worksheet that contains your media conditions **must** be named “MediaCompounds” or it will not upload. By default, the first sheet of any Excel file is called “Sheet1.” To rename it, find the worksheet tabs at the bottom left of the Excel file. Double-click on the default name and type in “MediaCompounds.”

Below is an example of a media file in TSV format. In this case, the compound IDs in the first column are from the [KBase ModelSEED Biochemistry Database](https://github.com/ModelSEED/ModelSEEDDatabase/tree/v1.0/Biochemistry) (scroll to the right to see full table):

| compounds | name      | formula | minflux | maxflux | concentration |
| --------- | --------- | ------- | ------- | ------- | ------------- |
| cpd00149  | Co2+      | Co      | -100    | 100     | 0.001         |
| cpd00099  | Cl-       | Cl      | -100    | 100     | 0.001         |
| cpd00063  | Ca2+      | Ca      | -100    | 100     | 0.001         |
| cpd00007  | O2        | O2      | -100    | 10      | 0.001         |
| cpd00027  | D-Glucose | C6H12O6 | -100    | 5       | 0.001         |

## Import media from a TSV or Excel file

For this example, you can click on either link to download a small media file onto your computer:

{% file src="../../.gitbook/assets/glucose_minimal (1).xls" %}
Example Excel file
{% endfile %}

{% file src="../../.gitbook/assets/glucose_minimal.tsv" %}
Example TSV file
{% endfile %}

Using a file on your computer, open the [_Import_ tab within the **Data Browser**](../../getting-started/narrative/add-data.md)**.** Then drag & drop the media file to upload it to your Staging Area. Choose "Media" from the _Import As..._ data type dropdown menu in your Staging Area. Click the upload icon next to the field that now says “Media.”

![Selecting Media for import from the Staging Area](../../.gitbook/assets/Media\_Staging\_Import.png)

The “Import Media file (TSV/Excel) from Staging Area” App will be added to your Narrative.

![Import Media file App](../../.gitbook/assets/Media\_tsv\_import.png)

You can change the name that will be assigned to the Media Object. Then click the green "Run" button. After the import process has completed, the Media data object will appear in your Data Panel.

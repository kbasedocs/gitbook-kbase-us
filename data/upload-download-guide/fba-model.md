---
description: >-
  Data handling to create a model to predict biomass yield given a certain
  amount of input nutrient.
---

# Flux Balance Analysis (FBA) Model

{% hint style="info" %}
Flux Balance Analysis (FBA) models can be uploaded into KBase as a Systems Biology Markup Language (SBML) file using the .sbml or .xml file extension, an Excel file using the .xls extension, or a tab-separated values (TSV) file using the .tsv extension.&#x20;

When uploading an FBA model in the TSV format, there will be two files corresponding to chemical compounds and reactions.
{% endhint %}

## Formatting Flux Balance Analysis Models

#### SBML

More SBML FBA Models for various organisms can be found here: [http://systemsbiology.ucsd.edu/Downloads](http://systemsbiology.ucsd.edu/Downloads).\
For a description of how to create a COBRA-compliant SBML file that can be imported as an FBA model into KBase, please see [SBML Level Three Specifications](http://sbml.org/Documents/Specifications).

#### Excel

In the Excel format, the tables containing the information about the chemical compounds and reactions in an FBA model are stored in two separate tabs respectively. The most important requirement for the Excel file is naming the tabs “ModelCompounds” and “ModelReactions.”

#### TSV

For the Tab-Separated Values file format, the chemical compounds and reactions tables are saved as two separate files named “FBAModelCompounds.tsv” and “FBAModelReactions.tsv” that will be transformed

### **FBAModelCompounds**

<table data-header-hidden><thead><tr><th width="150">id</th><th width="301">name</th><th width="160">formula</th><th>charge</th><th>aliases</th></tr></thead><tbody><tr><td>id</td><td>name</td><td>formula</td><td>charge</td><td>aliases</td></tr><tr><td> cpd00113</td><td> Isopentenyldiphosphate</td><td> C5H10O7P2</td><td> -2</td><td></td></tr><tr><td> cpd02590</td><td> all-trans-Heptaprenyl diphosphate</td><td> C35H58O7P2</td><td> -2</td><td></td></tr></tbody></table>

* **id**: Compound identifier; see the KBase Biochemistry reference for a list of compounds \[link]
* **name**: Name of chemical compound
* **formula**: Chemical formula using the Hill system
* **charge**: Formal charge of the molecule
* **aliases**: Alternative names for chemical compound

### **FBAModelReactions**

Importing an FBA model into KBase requires specified reaction IDs for the biomass producing equations in the model. An individual organism FBA model needs a single biomass equation, while a community model may have multiple biomass producing equations. In the FBAModelReactions table, denote the biomass producing reaction of an individual organism, or the first in a community model, with an ID such as “bio1” so the reaction is easily identifiable. For subsequent biomass producing reactions in a community model, it is recommended that you use “bio2” for the second biomass producing reaction, “bio3” for the third, and so on.

{% hint style="info" %}
Scroll table below from left to right to see complete format
{% endhint %}

<table data-header-hidden><thead><tr><th width="162">id</th><th width="150">direction</th><th width="150">compartment</th><th width="150">gpr</th><th width="215">name</th><th width="150">enzyme</th><th width="150">pathway</th><th width="150">reference</th><th>equation</th></tr></thead><tbody><tr><td>id</td><td>direction</td><td>compartment</td><td>gpr</td><td>name</td><td>enzyme</td><td>pathway</td><td>reference</td><td>equation</td></tr><tr><td>rxn00001_c0</td><td>-></td><td>c0</td><td>fig|211586.9.peg.3751</td><td>Pyrophosphate phosphohydrolase_c0</td><td></td><td></td><td></td><td>(1) cpd00001[c0] + (1) cpd00012[c0] -> (2) cpd00067[c0] + (2) cpd00009[c0]</td></tr><tr><td>rxn00056_c0</td><td>&#x3C;-></td><td>c0</td><td>fig|211586.9.peg.1038</td><td>Fe(II):oxygen oxidoreductase_c0</td><td></td><td></td><td></td><td>(4) cpd00067[c0] + (4) cpd10515[c0] + (1) cpd00007[c0] &#x3C;-> (4) cpd10516[c0] + (2) cpd00001[c0]</td></tr></tbody></table>

* **id**: Reaction identifier; see the [KBase Biochemistry reference for a list of reactions](https://github.com/ModelSEED/ModelSEEDDatabase/tree/v1.0/Biochemistry)
* **direction**: Directionality of chemical reaction specified as forward (->), reversed (<-), or equilibrium (<->)
* **compartment**: Cellular compartment that the reaction takes place in; see the [Metabolic Modeling FAQ for more information](../../workflows/metabolic-models/faq-metabolic-modeling.md)
* **gpr**: Gene-Protein Reaction in PATRIC identifier format
* **name**: Protein associated with the reaction
* **enzyme**: Optional, can be left empty
* **pathway**: Optional, can be left empty
* **reference**: Optional, can be left empty
* **equation**: Chemical reaction equation specified with compound coefficients in parentheses, compound identifiers, and directional arrows

## Importing FBA Models

In order to successfully upload an FBA model into your KBase workspace, you first need to [add the Genome](genome.md) that corresponds to referenced in the FBA Model you wish to upload. Add the Genome to the Narrative before importing the FBA model file.

Using a file on your computer, open the [_Import_ tab within the **Data Browser**](../../getting-started/narrative/add-data.md)**.** Then drag & drop the FBA model file (plus compound file if using TSV format) into your Staging Area. Open the pulldown menu to the right of the filename in the Staging Area and select “FBA Model."&#x20;

![FBA Model selection from the Staging Area](../../.gitbook/assets/FBAModel\_import.png)

Now click the import icon (up arrow) to the right of “FBA Model." The Data Browser slide-out will close and an app called “Import TSV/XLS/SBML File as an FBAModel from Staging Area” will be added to your Narrative.

Notice that the Model file path is filled in, as is a suggested name for the FBA Model data object that will be created by the import (you can edit this).

![Import TSV/XLS/SBML File as an FBAModel from Staging Area App](../../.gitbook/assets/FBAModel\_tsv\_import.png)

At this point, the corresponding Genome needs to be linked to the FBA Model. Add the name of the Genome using the dropdown to select the Genome that you added to the Data Panel. Although specifying the Genome is optional, adding a Genome with gene IDs that match genes IDs in the model is required to import gene-protein-reactions (GPRs). GPRs are necessary to perform gene KO in the Run Flux Balance Analysis App.

Ensure the correct Model file type is selected (SBML, Excel, Tab-separated values). &#x20;

Click the "+" button to the right of Biomass and type in the name of the first biomass. If there are additional biomass values to enter, click the "+" button to open another parameter field for another biomass. _Note: If the biomass reaction name starts with “R\_”, do NOT include the “R\_” when entering the name in this field._ &#x20;

If importing a TSV-formatted model, select the corresponding Compounds file path from the dropdown.

Edit the FBA Model object name for the output if necessary. Click the green "Run" button to start the import.

When the import is finished, your Data Panel will update to show the new FBA Model object, and a report will appear in the Import App.

### **Drag & Drop Limitations**

Drag & drop upload from your local computer works for many files, but there is a size limit  dependent on your computer and browser. For larger files around 20GB or more, use [Globus Online transfer](../globus.md).

## Associating an FBA Model with Genome

For KBase Metabolic Modeling Apps, associating a genome with user uploaded models is necessary for ensuring fidelity between the genome annotations and gene-protein-reactions in the metabolic model. This means that the gene IDs between the model and genome need to match. Occasionally, researchers will use locus tags or gene IDs for constructing metabolic models that are different than those found commonly in reference genomes. If the gene IDs do not match, you will need to change either the model or the genome to ensure their gene IDs match.&#x20;

One way to accomplish this is to locate the genome used as the reference for building the model – based on shared gene IDs – and to upload this genome into KBase before uploading the model and associating it with the genome. If you cannot locate the genome with the gene IDs used to build the model, the best option for reconciling the gene IDs is to edit the model file (as SBML or TSV) to change the gene IDs contained therein to match the gene IDs of the genome.&#x20;

This [public Help Board ticket](https://kbase-jira.atlassian.net/browse/PUBLIC-20) has a detailed example of how to accomplish this.

---
description: >-
  Create a model to predict biomass yield given a certain amount of input
  nutrient.
---

# Flux Balance Analysis \(FBA\) Model

## **Upload FBA Model from a SBML formatted file**

Flux Balance Analysis \(FBA\) models can be uploaded into KBase as a Systems Biology Markup Language \(SBML\) file using the .sbml or .xml file extension. For this example, we will upload the file containing an FBA model for _Bacillus subtilis_ 168 that has been included in the supplementary materials for this publication:

Henry, C. S., Zinner, J. F., Cohoon, M. P., & Stevens, R. L. \(2009\). [iBsu1103: a new genome-scale metabolic model of _Bacillus subtilis_ based on SEED annotations](https://genomebiology.biomedcentral.com/articles/10.1186/gb-2009-10-6-r69). Genome Biology, 10\(6\), R69. doi:10.1186/gb-2009-10-6-r69

Go to the publication, find Additional file 4, right-click and select ‘_Save Link As…_’ to download and save this FBA model. 

Double-check that the _Bacillus subtilis_ 168 FBA Model completely downloaded by opening the file in a text or code editor and ensuring that the file is 47527 lines long and ends with “&lt;/sbml&gt;.” Otherwise, the data could be corrupted and will not import properly into KBase.

In order to successfully upload an FBA model into your KBase workspace, you first need to add the Genome that corresponds to referenced in the FBA Model you wish to upload. For this example, we’ll add the _Bacillus\_subtilis\_subsp.\_subtilis\_str.\_168_ Genome to our Narrative \(under the _Public_ tab in the **Data Browser**\) before importing the FBA model file.

To add the Genome to your Narrative, find the **Data Panel** along the left side of the screen and click the red "Add Data" \(or red “+”\) button. This will open the **Data Browser**. Select the _Example_ tab at the top of the Data Browser, and search for “Bacillus subtillis subsp. Subtillis str. 168” genome. Mouse over the genome name and click the blue "&lt; Add" button.

![Import FBA SBML](http://kbase.us/wp-content/uploads/2015/08/Import-FBA-SMBL.png)

After you’ve added the _Bacillus subtilis_ 168 genome to your Data Panel, open the Import tab in the Data Browser and drag the FBA model file into your Staging Area.

![](http://kbase.us/wp-content/uploads/2016/12/image3.png)

### **Drag & Drop Limitations**

Drag & drop upload from your local computer works for many files, but there is a size limit  dependent on your computer and browser. For larger files around 20GB or more, use [Globus Online transfer](http://kbase.us/transfer-data-from-globus-to-kbase/).

Now that the FBA model is in your Staging Area, it’s time to import it into your Narrative as a KBase FBA Model data object. Open the pulldown menu to the right of the filename in your Staging Area and select “FBA Model."

![](http://kbase.us/wp-content/uploads/2016/12/image9.png)

Now click the import icon \(up arrow\) to the right of “FBA Model." The Data Browser slide-out will close and an app called “Import TSV/XLS/SBML File as an FBAModel from Staging Area” will be added to your Narrative.

![](http://kbase.us/wp-content/uploads/2016/12/image4.png)

Notice that the Model file path is filled in, as is a suggested name for the FBA Model data object that will be created by the import \(you can edit this\). For this example, we will change it to "Bacillus\_subtilus\_168.xml\_model."

At this point, the corresponding Genome needs to be linked to the FBA model. To add the name of the Genome, use the dropdown to select the GCF\_000009045.1 genome \(Bacillus\_subtilis\_subsp.\_subtilis\_str.\_168\) in the Data Panel. Note that although specifying the Genome is optional in the app, adding a Genome with gene IDs that match genes IDs in the model is required to import gene-protein-reactions \(GPRs\). GPRs are necessary to perform gene KO in the Run Flux Balance Analysis App.

Next fill in the name of the biomass reaction in the SBML file, in this case “bio00006”. 

Note: If the biomass reaction name starts with “R\_”, do NOT include the “R\_” when entering the name in this field. 

Click the "+" button to the right of Biomass and type in the name of the first biomass. If there are additional biomass values to enter, click the "+" button to open another parameter field for another biomass.

Click “show advanced options” and select the Genome \(in this example, the subtilis 168 genome\) which contains features referenced in the FBAModel. Adjust any of the other advanced options if needed, then click the green "Run" button to start the import.

![](http://kbase.us/wp-content/uploads/2016/12/image7.png)

When the import is finished, your Data Panel will update to show the new FBA Model object, and a report will appear in the import app cell.

![](http://kbase.us/wp-content/uploads/2016/12/image8.png)

## **More Information**

More SBML FBA models for various organisms can be found here: [http://systemsbiology.ucsd.edu/Downloads](http://systemsbiology.ucsd.edu/Downloads).  
For a description of how to create a COBRA-compliant SBML file that can be imported as an FBA model into KBase, please see [SBML Level Three Specifications](http://sbml.org/Documents/Specifications).

## **Upload a FBA Model in Excel or TSV format**

FBA models can be uploaded into KBase as either an Excel file \(.xls\) or via a pair of Tab-Separated Values \(.tsv\) files containing the chemical compounds and reactions present in the FBA Model. In the Excel format, the tables containing the information about the chemical compounds and reactions in an FBA model are stored in two separate tabs respectively titled “FBAModelCompounds” and “FBAModelReactions.” For the Tab-Separated Values file format, the chemical compounds and reactions tables are saved as two separate files named “FBAModelCompounds.tsv” and “FBAModelReactions.tsv” that will be transformed into the FBA Model data object within KBase.

## **FBAModelCompounds**

| id | name | formula | charge | aliases |
| :--- | :--- | :--- | :--- | :--- |
|  cpd00113 |  Isopentenyldiphosphate |  C5H10O7P2 |  -2 |  |
|  cpd02590 |  all-trans-Heptaprenyl diphosphate |  C35H58O7P2 |  -2 |  |

* **id**: Compound identifier; see the KBase Biochemistry reference for a list of compounds \[link\]
* **name**: Name of chemical compound
* **formula**: Chemical formula using the Hill system
* **charge**: Formal charge of the molecule
* **aliases**: Alternative names for chemical compound

## **FBAModelReactions**

| id | direction | compartment | gpr | name | enzyme | pathway | reference | equation |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| rxn00001\_c0 | -&gt; | c0 | fig\|211586.9.peg.3751 | Pyrophosphate phosphohydrolase\_c0 |  |  |  | \(1\) cpd00001\[c0\] + \(1\) cpd00012\[c0\] -&gt; \(2\) cpd00067\[c0\] + \(2\) cpd00009\[c0\] |
| rxn00056\_c0 | &lt;-&gt; | c0 | fig\|211586.9.peg.1038 | Fe\(II\):oxygen oxidoreductase\_c0 |  |  |  | \(4\) cpd00067\[c0\] + \(4\) cpd10515\[c0\] + \(1\) cpd00007\[c0\] &lt;-&gt; \(4\) cpd10516\[c0\] + \(2\) cpd00001\[c0\] |

* **id**: Reaction identifier; see the [KBase Biochemistry reference for a list of reactions](ftp://ftp.kbase.us/assets/KBase_Reference_Data/Biochemistry)
* **direction**: Directionality of chemical reaction specified as forward \(-&gt;\), reversed \(&lt;-\), or equilibrium \(&lt;-&gt;\)
* **compartment**: Cellular compartment that the reaction takes place in; see the [Metabolic Modeling FAQ for more information](../../workflows/metabolic-modeling-in-kbase/faq-metabolic-modeling-in-kbase.md)
* **gpr**: Gene-Protein Reaction in PATRIC identifier format
* **name**: Protein associated with the reaction
* **enzyme**: Optional, can be left empty
* **pathway**: Optional, can be left empty
* **reference**: Optional, can be left empty
* **equation**: Chemical reaction equation specified with compound coefficients in parentheses, compound identifiers, and directional arrows

Importing an FBA model into KBase requires specified reaction IDs for the biomass producing equations in the model. An individual organism FBA model needs a single biomass equation, while a community model may have multiple biomass producing equations. In the FBAModelReactions table, denote the biomass producing reaction of an individual organism, or the first in a community model, with an ID such as “bio1” so the reaction is easily identifiable. For subsequent biomass producing reactions in a community model, it is recommended that you use “bio2” for the second biomass producing reaction, “bio3” for the third, and so on.

## **Upload FBA Model from an Excel formatted file**

Importing using an Excel file is similar to importing SBML files. The most important requirement for the Excel file is naming the tabs “ModelCompounds” and “ModelReactions.”

In the Import app most of the options are the same as for SBML. Select a Genome from the dropdown, add a Biomass \(remember, if the biomass reaction starts with “R\_”, do NOT include the “R\_” when entering the name in this field\) and modify the FBA Model object name. The primary difference is that the default _Model file type_ needs to be changed to “Excel”.

![](http://kbase.us/wp-content/uploads/2016/12/image10.png)

## **Upload FBA Model from a tab-delimited file**

Importing a Tab-Separated file requires two files, one for reactions and one for compounds. In your Staging area \(which you access from the Import tab in the Data Browser\), go to the line with the name of the reactions file and select “FBA Model” from the dropdown under _Import As..._ column.

![](http://kbase.us/wp-content/uploads/2016/12/image6.png)

Now click the import icon \(up arrow\) to the right of “FBA Model." The Data Browser will then close and an app called “Import TSV/XLS/SBML File as an FBAModel from Staging Area” will be added to your Narrative.

There are two important differences between importing an FBA model from an SBML file vs. importing in tab-delimited format. First, in the import app, the default Model file type needs to be changed from SBML to Excel. Second, the app needs the name of the compounds file. In the line for “Compounds File Path”, type in the name of the compounds file. There is no pulldown or other help to get the name of the file right. The name is usually a slight variation of the reactions file name.img src=”http://kbase.us/wp-content/uploads/2016/12/image12-1.png” alt=”” width=”637″ height=”630″ class=”screengrab alignnone size-full wp-image-13471″ /&gt;

## Associating Model with Genome

For metabolic modeling apps, correctly associating a genome with the user uploaded models is necessary for ensuring fidelity between the genome annotations and gene-protein-reactions in the metabolic model. This means that the gene IDs between the model and genome need to match. Occasionally, researchers will use locus tags or gene IDs for constructing metabolic models that are different than those found commonly in reference genomes. If the gene IDs do not match, you will need to change either the model or the genome to ensure their gene IDs match. 

One way to accomplish this is to locate the genome used as the reference for building the model – based on shared gene IDs – and to upload this genome into KBase before uploading the model and associating it with the genome. If the user cannot locate the genome with the gene IDs used to build the model, the best option for reconciling the gene IDs is to edit the model file \(as SBML or TSV\) to change the gene IDs contained therein to match the gene IDs of the genome. 

This [public Help Board ticket](https://kbase-jira.atlassian.net/browse/PUBLIC-20) has a detailed example of how to accomplish this.


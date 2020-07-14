---
description: >-
  The Phenotype Set data type represents experimental data about an organism’s
  ability to grow in specific media conditions, recorded as growth or no growth.
---

# Phenotype Set

## **Formatting Phenotype TSV or Excel files**

A Phenotype Set can be uploaded from a TSV \(tab-separated values\) file with a .tsv or .tab file extension, or from Excel spreadsheet with a .xls extension. The spreadsheet needs to have exactly these five columns:

* **Gene knockout \(geneko\)** – List of genes knocked out in the phenotype; use 'none' for wild-type phenotypes. Gene IDs should be in the same format that appears in your metabolic model \(e.g., kb\|g.220339.CDS.2927\)
* **Workspace information \(mediaws\)** – Workspace where the media for the phenotype data was loaded into KBase. The workspace information can be found in the Narratives tab by clicking _Show Advanced Controls_ at the end of the list of Narratives
* **Media** – ID of the media condition loaded in KBase where the phenotype was observed.
* **Additional Compounds \(addtlCpd\)** – Additional media compound IDs to be added alongside the primary media formulation. See the [KBase Biochemistry Database](ftp://ftp.kbase.us/assets/KBase_Reference_Data/Biochemistry) to download the compounds file and locate specific IDs.
* **Growth** – Indication of whether or not the organism grew in the specified media with the specified knockouts. 1 meaning growth; 0 meaning no growth.

| geneko | mediaws | media | addtlCpd | growth |
| :--- | :--- | :--- | :--- | :--- |
| SO\_0009 | KBaseMedia | C-D-Glucose |  | 0 |
| SO\_0009 | KBaseMedia | C-D-Lactate |  | 1 |
| SO\_0009 | KBaseMedia | C-acetate |  | 1 |

For this example, we will use the Shewanella\_oneidensis\_MR-1 Genome from the _Example_ data tab. To [add the Genome to your Narrative](../../getting-started/user-guide/add-data.md), find the Data Panel along the left side of the screen and click the Add Data \(or red “+”\) button. This will open the Data Browser slideout. Select the _Example_ tab at the top of the slideout, and search for “Shewanella\_oneidensis\_MR-1” genome. Mouse over the Genome name and click the blue Add button.

![](http://kbase.us/wp-content/uploads/2016/04/image5.png)

The S. oneidensis Genome object should appear in your Data Panel.

To download an example phenotype set data table, right-click [here](http://kbase.us/wp-content/uploads/2018/04/ExamplePhenotypeSet.tsv) and choose “Save as”.

Now open the new Import tab in the Data Slideout and drag the example phenotype set file that you just downloaded into your Staging area \(go [here](../../getting-started/user-guide/add-data.md#uploading-data-from-external-sources) if you need instructions on doing that\).

Now the phenotype set is in your Staging area–it’s time to import it into your Narrative as a KBase Phenotype Set data object. Open the pulldown menu to the right of the filename in your Staging Area and select “Phenotype Set”:

![](http://kbase.us/wp-content/uploads/2016/04/image1.png)

Now click the import icon \(up arrow\) to the right of “Phenotype Set”. The data slideout will close and an app called “Import TSV File as Phenotype Set From Staging Area” will be added to your Narrative.

![](http://kbase.us/wp-content/uploads/2016/04/image6.png)

Notice that the name of the Phenotype TSV file is already filled in, as is a suggested name for the Phenotype Set data object that will be created by the import \(you can change that if you like\).

At this point, the corresponding Genome hasn’t been linked to the phenotype set. To add the name of the Genome, click on the dropdown in the app to select the Shewanella\_oneidensis\_MR-1 genome that you added to your Narrative earlier. Then click the green Run button to start the import. When the import is finished, your Data Panel will update to show the new Phenotype Set object, and a report will appear in the import app cell.

![](http://kbase.us/wp-content/uploads/2016/04/image7.png)

In the example above, we used a Genome that was in the _Example_ data. You can also import your own Genome data from a file following instructions found [here](genome.md).


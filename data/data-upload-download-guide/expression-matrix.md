---
description: >-
  The Expression Matrix data type contains gene expression values taken under
  given sampling conditions.
---

# Expression Matrix

## **Formatting Expression Matrix TSV files**

If you are importing expression data from an external source or want to populate a file with your own data, please ensure that it is formatted properly for use with KBase. A tab-separated values \(TSV\) file is a tab delimited text file that has genes across the rows and sample observations across the columns. Make sure the first label in the first column is “feature\_ids” followed by tab-delimited labels for samples.

For this example, we will use the Shewanella\_oneidensis\_MR-1 genome and the Shewanella\_MR-1\_M3D\_ExpData expression data set from the _Example_ data tab. \(When working with your own data, you can start with an empty Expression Matrix template.\)

For this example, we will use the Shewanella\_oneidensis\_MR-1 Genome from the _Example_ data tab. To [add the Genome to your Narrative](../../getting-started/user-guide/add-data.md), find the **Data Panel** along the left side of the screen and click the "Add Data" \(or red “+”\) button. This will open the **Data Browser** slide-out. Select the _Example_ tab at the top of the slide-out, and search for “Shewanella\_oneidensis\_MR-1” genome. Mouse over the Genome name and click the blue "&lt; Add" button.

![](http://kbase.us/wp-content/uploads/2016/04/image5.png)

The _Shewanella oneidensis_ Genome object should now appear in your Data Panel.

Do the same for the Shewanella\_MR-1\_M3D\_ExpData expression data set: find it in the _Example_ tab and click the “&lt; Add” button to add it to your Narrative. You should now see both the Genome and the Expression Matrix in your Data Panel.

![](http://kbase.us/wp-content/uploads/2015/08/image4-3.png)

Each gene measured in the expression dataset should have an identifier listed in the first column of the TSV file. To ensure that the gene identifiers listed in your dataset correspond to the aliases in KBase, click the name of the Genome to open up the genome viewer. Click on the tab labeled _Browse Features_ and locate a gene of interest by searching for the name of the function or protein associated with the gene. 

In this example, we’ll search for ‘DNA Polymerase’ and identify SO\_0009 as a gene of interest. Click the _Feature ID_ of the gene of interest to open a new tab with additional information about the gene. 

![](http://kbase.us/wp-content/uploads/2015/08/image1-3.png)

Locate the section titled _Aliases_ and crosscheck the gene labels contained within your expression dataset with either the Feature ID or one of these aliases to ensure that these labels will correspond to features in KBase.

To see an example Expression Matrix format, [download](downloads.md) the Shewanella\_MR-1\_M3D\_ExpData expression data set from your Data Panel. Unzip the downloaded file and examine the file "matrix.tsv." 

In Excel, a few of the rows and columns are:

![](http://kbase.us/wp-content/uploads/2015/08/image7-1.png)

The first column matches Feature IDs from the genome. This column could have also been a gene alias. Some of the gene aliases supported by KBase include NCBI, EMBL, UniProt, BioCyc, and ASAP. The column headings are sample conditions. The remaining cells in the table contain expression values for the appropriate gene and sample. Be sure to exclude gene features that are missing all expressions or are composed of non-changing expressions across the samples.

Below is an example of a properly formatted expression data file in TSV format. In this case, the gene-ids in the first correspond to gene identifiers for _E. coli_ K-12 MG1655 genes and the sample conditions are derived from the [Many Microbe Microarrays Database \(M3D\)](http://m3d.mssm.edu/about.html).

| feature\_ids | dinI\_U\_N0025\_r1 | dinI\_U\_N0025\_r2 | dinI\_U\_N0025\_r3 |
| :--- | :--- | :--- | :--- |
| b4634 | 9.05367 | 9.07827 | 9.10114 |
| b3241 | 7.20924 | 7.08695 | 7.07071 |
| b3240 | 7.21535 | 7.14312 | 7.19478 |

If you want to build an expression matrix with your own data, download an [empty template](http://kbase.us/wp-content/uploads/2015/08/matrix.tsv) and populate it with your expression data.

## **Additional Information for Plant Expression Data**

For KBase plant genomes, the gene IDs retain the data structure from the external source databases \(Ensembl or Phytozome\) and do not have aliases as mentioned above. When constructing an expression dataset, append your gene IDs with the transcript IDs followed by “.CDS” as seen in the screenshot below. You can check that you have the correct gene IDs using the same method detailed in the **Formatting Expression Matrix TSV files** section.

![Plants1](http://kbase.us/wp-content/uploads/2015/08/Plants1.png)

## Upload an Expression Matrix from a TSV-formatted file

For this example, we will upload the expression dataset from above containing expression values for _Shewanella oniedensis_ MR-1.

Expression Matrices can be uploaded into KBase without a Genome, but they will have limited use. In order to successfully upload an Expression Matrix into KBase, you first need to add the Genome that corresponds to references in the Expression Matrix you wish to upload. For the example we’ve been using, the Genome was added above from the _Example_ tab.

Now open the _Import_ tab in the Data Browser slide-out and drag & drop the example expression matrix file that you just downloaded \(matrix.tsv\) into the Staging Area. Go [here](../../getting-started/user-guide/add-data.md#uploading-data-from-external-sources) if you need more instruction on drag & drop uploading.

### **Drag & Drop Limitations**

The drag & drop from your local computer works for many files, but there is a size limit that depends on your computer and browser. For larger files around 20GB, use the [Globus Online transfer](../globus.md). Now that the expression matrix is in your Staging Area and you can import it from there into your Narrative. Open the pulldown menu to the right of the filename under the _Import As..._ column in your Staging Area and select “Expression Matrix."

![](http://kbase.us/wp-content/uploads/2015/08/image9-1.png)

Click the import icon \(up arrow\) to the right of “Expression Matrix.” The Data Browser will close and the App “Import TSV File as Expression Matrix From Staging Area” will be added to your Narrative.

![](http://kbase.us/wp-content/uploads/2015/08/image10-1.png)

Notice that the name of the Tab-delimited \(TSV\) file is already filled in, as is a suggested name for the Expression Matrix data object that will be created by the import, which can be edited or changed.

At this point, the corresponding genome is optional and hasn’t been linked to the expression matrix. To add the name of the Genome, click on the ‘show advanced’ link to the right of ‘Input Objects’ in the Import app.

![](http://kbase.us/wp-content/uploads/2015/08/image11-2.png)

Use the Genome dropdown to select the Shewanella\_oneidensis\_MR-1 genome. Adjust any of the other advanced options if needed, then click the green "Run" button to start the import. When the import is finished, your Data Panel will update to show the new Expression Matrix object, and a report will appear in the Import App Cell. 


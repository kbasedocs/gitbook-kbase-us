---
description: >-
  The Expression Matrix data type contains gene expression values taken under
  given sampling conditions.
---

# Expression Matrix

{% hint style="info" %}
Expression Matrices can be uploaded and imported using the Tab-separated values (TSV) file extension .tsv or the Excel file extension .xls.
{% endhint %}

## **Formatting Expression Matrix files**

If you are importing expression data from an external source or want to populate a file with your own data, please ensure that it is formatted properly for use with KBase.&#x20;

#### TSV

A tab-separated values (TSV) file is a tab delimited text file that has genes across the rows and sample observations across the columns. Make sure the first label in the first column is “feature\_ids” followed by tab-delimited labels for samples.

#### Excel

In Excel, the first column matches _Feature IDs_ from the genome. This column could have also been a gene alias. Gene aliases supported by KBase include NCBI, EMBL, UniProt, BioCyc, and ASAP. The column headings are _sample conditions_.&#x20;

The remaining cells in the table contain expression values for the appropriate gene and sample. Be sure to exclude gene features that are missing all expressions or are composed of non-changing expressions across the samples.

Below is an example of a properly formatted expression data file in TSV format. In this case, the gene-ids in the first correspond to gene identifiers for _E. coli_ K-12 MG1655 genes and the sample conditions are derived from the [Many Microbe Microarrays Database (M3D)](http://m3d.mssm.edu/about.html).

| feature\_ids | dinI\_U\_N0025\_r1 | dinI\_U\_N0025\_r2 | dinI\_U\_N0025\_r3 |
| ------------ | ------------------ | ------------------ | ------------------ |
| b4634        | 9.05367            | 9.07827            | 9.10114            |
| b3241        | 7.20924            | 7.08695            | 7.07071            |
| b3240        | 7.21535            | 7.14312            | 7.19478            |

To see an example Expression Matrix format, [download](downloads.md) the "Shewanella\_MR-1\_M3D\_ExpData" ExpressionMatrix data set from the _Example_ tab in the Data Panel. Unzip the downloaded file and examine the "matrix.tsv" file.&#x20;

### **Plant Expression Data**

For KBase plant genomes, the gene IDs retain the data structure from the external source databases (Ensembl or Phytozome) and do not have aliases as mentioned above. When constructing an expression dataset, append gene IDs with the transcript IDs followed by “.CDS." You can check that you have the correct gene IDs&#x20;

## Upload and Import an Expression Matrix

Expression Matrices can be uploaded into KBase without a Genome, but they will have limited use. In order to successfully upload an Expression Matrix into KBase, you first need to add the [Genome](genome.md) that corresponds to references in the Expression Matrix.&#x20;

Using a file on your computer, open the [_Import_ tab within the **Data Browser**](../../getting-started/narrative/add-data.md)**.** Then drag & drop the expression matrix file into the Staging Area.

Now that the expression matrix is in your Staging Area and you can import it from there into your Narrative. Open the pulldown menu to the right of the filename under the _Import As..._ column in your Staging Area and select “Expression Matrix."

Click the import icon (up arrow) to the right of “Expression Matrix.” The Data Browser will close and the “Import TSV File as Expression Matrix From Staging Area” App will be added to your Narrative.

The name of the Tab-delimited (TSV) file is already filled in, as is a suggested name for the Expression Matrix data object that will be created by the import, which can be edited or changed.

![Import Expression Matrix App](../../.gitbook/assets/ExpressionMatrix\_TSV\_Import.png)

At this point, the corresponding genome is optional and hasn’t been linked to the expression matrix. To add the name of the Genome, click on the ‘show advanced’ link to the right of ‘Input Objects’ in the Import App.

![Import Expression Matrix App showing advanced parameters](../../.gitbook/assets/ExpressionMatrix\_TSV\_advanced\_import.png)

Use the Genome dropdown to select the corresponding genome. Adjust any of the other advanced options if needed, then click the green "Run" button to start the import. When the import is finished, your Data Panel will update to show the new Expression Matrix object, and a report will appear in the Import App.&#x20;

#### Expression Matrix Object

Each gene measured in the expression dataset should have an identifier listed in the first column of the TSV file. To ensure that the gene identifiers listed in your dataset correspond to the aliases in KBase, click the name of the Genome object to open up the genome viewer.&#x20;

* Click on the tab labeled _Browse Features_ and locate a gene of interest by searching for the name of the function or protein associated with the gene.&#x20;
* Click the _Feature ID_ of the gene of interest to open a new tab with additional information about the gene.&#x20;
* Locate the section titled _Aliases_ and crosscheck the gene labels contained within your expression dataset with either the Feature ID or one of these aliases to ensure that these labels will correspond to features in KBase.

### **Drag & Drop Limitations**

The drag & drop from your local computer works for many files, but there is a size limit that depends on your computer and browser. For larger files around 20GB, use the [Globus Online transfer](../globus.md).&#x20;

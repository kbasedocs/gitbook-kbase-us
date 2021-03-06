---
description: How to upload FASTA files into KBase.
---

# Assembly

An assembly file is a single file containing one or more contiguous DNA sequences in FASTA format. It can be uploaded to KBase from your local computer \(with file extension .fasta, .fna, .fa, or .fas\) or directly from a publicly accessible FTP or HTTP URL.

“Assembly” is the KBase data type for assembled, unannotated DNA sequence contigs. If you want to upload annotated sequences in GenBank or GFF format, please see the [Genome](genome.md) page.

![](../../.gitbook/assets/uploading-reads%20%281%29.gif)

## Importing a FASTA formatted assembly file from your computer

For this example, we will use an _Escherichia coli_ K12 MG1655 assembly file from NCBI as the source: [GCF\_000005845.2\_ASM584v2\_genomic.fna.gz](ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/000/005/845/GCF_000005845.2_ASM584v2/GCF_000005845.2_ASM584v2_genomic.fna.gz)

Download that file to your computer. Next open the [_Import_ tab within the **Data Browser**](../../getting-started/narrative/add-data.md) ****and drag the assembly file into the Staging Area.

![](../../.gitbook/assets/dragging-assembly-into-staging-1.jpg)

Open the _Select a format_ pulldown menu to the right of the filename in your Staging Area under the _Import As..._ column select “Assembly.”

![](../../.gitbook/assets/importasassembly.png)

Now click the import icon to the right of “Assembly”. The data slide-out will close and an app called “Import FASTA File as Assembly from Staging Area” will be added to your Narrative.

![](../../.gitbook/assets/importfastafileasassembly%20%281%29.png)

Notice that the name of the gzipped Assembly file is already filled in, as is a suggested name for the Assembly data object that will be created by the import \(you can change the Assembly object name\). Adjust the minimum contig length if needed and then click the green "Run" button to start the import. When the import is finished, your Data Panel will update to show the new Assembly object, and a report will appear in the import app cell.

![](../../.gitbook/assets/importfastaapp_successs.png)

### **Drag & Drop Limitations**

The drag & drop option from your local computer works for many files, but there is a size limit that depends on your computer and browser. For larger files \(around 20GB\), use [Globus Online transfer](../globus.md). 

## Import an Assembly from other sources

In the Staging Area, beneath the box for Drag & Drop, are other options for getting data.  
  
You can import data into your KBase workspace using [Globus](http://kbase.us/transfer-data-from-globus-to-kbase/), or by supplying a URL for a publicly accessible FTP location, Google Drive, Dropbox, or a direct HTTP link. Options for adding data to your Staging Area are described [here](../../getting-started/narrative/add-data.md).

![](../../.gitbook/assets/user_refresh.png)

## **Transfer assemblies from JGI**

If you are a JGI user, you can transfer public genome reads and assemblies \(as well as your private data and annotated genomes\) from JGI to your KBase account—see [this page](../jgi-transfer.md) for instructions.


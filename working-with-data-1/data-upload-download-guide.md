# Data Upload and Download Guide

[Data Upload and Download Guide](data-upload-download-guide.md#data-upload-and-download-guide)

[Data Type Descriptions](data-upload-download-guide.md#data-type-descriptions)

[Uploading Data](data-upload-download-guide.md#uploading-data)

[Assembly](data-upload-download-guide.md#assembly)

[Genome](data-upload-download-guide.md#genome)

[FASTQ/SRA Reads](data-upload-download-guide.md#fastq-sra-reads)

[Flux Balance Analysis \(FBA\) Model](data-upload-download-guide.md#flux-balance-analysis-fba-model)

[Media](data-upload-download-guide.md#media)

[Expression Matrix](data-upload-download-guide.md#expression-matrix)

[Phenotype Set](data-upload-download-guide.md#phenotype-set)

[Downloading Data](data-upload-download-guide.md#downloading-data)

## Data Upload and Download Guide

**Uploading and Downloading Your Own Data**

This guide provides instructions for uploading different types of data to your KBase account and downloading output data from your analysis results.

**Learn about KBase's new Staging Import**

The new Import tab lets you drag & drop data from your computer into your Staging Area to import into your Narrative, where you can then analyze it using KBase’s analysis apps. Please see [this page](../getting-started/narrative-user-guide/) of the Narrative User Guide for instructions on how to use the Staging Import.

![](http://kbase.us/wp-content/uploads/2018/01/image7.png)

**Public Data in KBase**

KBase periodically imports [data from many publicly accessible databases](public-data-in-kbase.md#data-summary) and also allows users to upload their own datasets for analysis. Data uploaded by a KBase user is stored within that individual’s account and can only be accessed by others if the owner includes the data in a shared or public Narrative. After performing analyses using [KBase apps](../using-apps-1/analysis-apps-in-kbase/#apps), the results can be downloaded to your computer in several standard formats. If you have requests for more download formats, please [contact us](http://kbase.us/contact-us/).

## Data Type Descriptions

Data in KBase covers a wide range of data types relevant to systems biology research, including genomes and their annotations, metagenomes, expression and protein-protein interaction data, inferred models of organismal and community metabolism and gene regulation, and even geographical information about populations. By “data type”, we mean the internal KBase representation of a particular sort of biological data. 

The [Data Type Catalog](https://narrative.kbase.us/#catalog/datatypes) lists and describes the key data types in KBase.

## Uploading Data

**New upload interface**

The new Import tab lets you drag & drop data from your computer into your Staging Area to import into your Narrative, where you can then analyze it using KBase’s analysis apps. Please see [this page](http://kbase.us/narrative-guide/add-data-to-your-narrative-2/#upload) of the Narrative User Guide for general instructions on how to use the Staging Import.

![](http://kbase.us/wp-content/uploads/2018/01/image7.png)

The first step in uploading your data is to locate the Data Panel along the left side of the Narrative Interface window and click either the “Add Data” button, the red “+” button, or the right arrow at the upper right of the panel to access the slideout Data Browser. The Data Browser has several tabs that allow you to access data already in KBase, as well as the “Import” tab for importing your own data. 

**Please see** [**this page of the Narrative Guide**](../getting-started/narrative-user-guide/) **for instructions on using the new \(early 2018\) import tab.**

To close the Import panel and return to the Narrative Interface, simply click the “Close” button on the bottom right of the import panel. If you have a small screen, you might not be able to see that button. Another way to close the Data Browser is to click the arrow on the top right of your Data Panel \(the same one that opens the Data Browser slideout\).

**Data privacy**

Any data that you upload to KBase is kept private unless you choose to share it. You can share any of your Narratives \(including their associated data\) with one or more specific users, or make it publicly available to all KBase users. Please see the [Sharing](../getting-started/narrative-user-guide/share-narratives.md) page for more information about how to do that. The [Terms and Conditions page](http://kbase.us/terms-and-conditions/) describes the KBase data policy.  


The next sections of this guide describe the specific steps involved in uploading the currently supported data types, and show examples for each type.

**Transferring JGI data to KBase**

If you are a JGI user, you can transfer public genome reads and assemblies \(as well as your private data and annotated genomes\) from JGI to your KBase account—see [this page](transferring-data-from-jgi.md) for instructions.

## Assembly

**New upload interface**

The new Import tab lets you drag & drop data from your computer into your Staging Area to import into your Narrative, where you can then analyze it using KBase’s analysis apps. Please see [this page](../getting-started/narrative-user-guide/) of the Narrative User Guide for general instructions on how to use the Staging Import.  


**Drag & Drop Limitations**

The drag & drop from your local computer works for many files, but there is a size limit that depends on your computer and browser. Some users have reported problems around 20 gigabases. For larger files, use the [Globus Online transfer](transferring-data-with-globus.md).

An assembly file is a single file containing one or more contiguous DNA sequences in FASTA format. It can be uploaded to KBase from your local computer \(with file extension .fasta, .fna, .fa, or .fas\) or directly from a publicly accessible FTP or HTTP URL.

“Assembly” is the KBase data type for assembled, unannotated DNA sequence contigs. If you want to upload annotated sequences in GenBank or GFF format, please see the [Genome](data-upload-download-guide.md#genome) page.

#### Importing a FASTA formatted assembly file from your computer

For this example, we will use an _Escherichia coli_ K12 MG1655 assembly file from NCBI as the source: [GCF\_000005845.2\_ASM584v2\_genomic.fna.gz](ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/000/005/845/GCF_000005845.2_ASM584v2/GCF_000005845.2_ASM584v2_genomic.fna.gz)

Download that file to your computer. Then open the [new Import tab in the Data Slideout](../getting-started/narrative-user-guide/add-data-to-your-narrative.md) and drag the assembly file into your Staging area.

![](http://kbase.us/wp-content/uploads/2018/02/dragging-assembly-into-staging-1.jpg)

Open the pulldown menu to the right of the filename in your Staging Area and select “Assembly”:

![](http://kbase.us/wp-content/uploads/2018/02/Screen-Shot-2018-02-16-at-1.24.22-PM.png)

Now click the import icon to the right of “Assembly”. The data slideout will close and an app called “Import FASTA File as Assembly from Staging Area” will be added to your Narrative.

![](http://kbase.us/wp-content/uploads/2018/02/Screen-Shot-2018-02-16-at-1.27.11-PM.png)

Notice that the name of the gzipped Assembly file is already filled in, as is a suggested name for the Assembly data object that will be created by the import \(you can change that if you like\). Adjust the minimum contig length if needed, then click the green Run button to start the import. When the import is finished, your Data Panel will update to show the new Assembly object, and a report will appear in the import app cell.

![](http://kbase.us/wp-content/uploads/2018/02/Screen-Shot-2018-02-16-at-1.36.37-PM.png)

**Compressed/zipped files**

The Assembly import app can handle gzipped \(.gz\) FASTA input files. However, .zip files and .Z files are not yet supported by the importers \(we are working on adding that\). You can upload a zip file to your Staging Area, but then you should use the “uncompress” button to its left \(the one with the diagonal arrows\) to unzip it before trying to import it.

![](http://kbase.us/wp-content/uploads/2015/08/image4.png)

#### Import an Assembly from other sources

In the Staging area, beneath the box for Drag and Drop, are other options for getting data.  
  
You can import data into your KBase workspace using [Globus](http://kbase.us/transfer-data-from-globus-to-kbase/), or by supplying a URL for a publicly accessible FTP location, Google Drive, Dropbox, or a direct HTTP link. Options for adding data to your staging area are described [here](../getting-started/narrative-user-guide/).

![](http://kbase.us/wp-content/uploads/2015/08/image6.png)

**Transfer assemblies from JGI**

If you are a JGI user, you can transfer public genome reads and assemblies \(as well as your private data and annotated genomes\) from JGI to your KBase account—see [this page](transferring-data-from-jgi.md) for instructions.

## Genome

In KBase, a DNA sequence is stored in an “Assembly” data object. **A “Genome” object is the annotated version of an Assembly** and can encompass several types of feature calls. If you want to upload just the DNA sequence from a FASTA file \(without annotations\), please go to the [Assembly](data-upload-download-guide.md#assembly) page instead.

Currently, the Genome importer supports only GenBank and GFF-formatted files. A GenBank-formatted input file should include the sequence contig\(s\), the feature calls \(annotations\), as well as the taxonomy information for the organism. KBase parses the input file into two data objects: an assembly object with the sequence and a genome object containing the original feature calls and annotations.

GenBank-formatted files with no features can be uploaded as Genomes but they aren’t very informative until they are annotated with a KBase app. Genomes with annotation can be used as input for several KBase analyses.

A GenBank-formatted file can be uploaded into your KBase staging area from your local computer \(files with.gb, .gbff, or .gbk extensions\) or directly from an FTP or HTTP URL.

A GFF-formatted file must be paired with a corresponding FASTA file of the DNA sequence. These also will be parsed into two data objects: an assembly object with the sequence and a genome object containing the original feature calls and annotations.

Instructions for adding data to your staging area can be found [here](../getting-started/narrative-user-guide/).

#### Importing a GenBank-formatted file from your computer

For this example, we will use the _E. coli_ K-12 MG1655 genome GenBank file from NCBI. By clicking on the following link you can download the _E. coli_ K-12 MG1655 genome to your computer: [ftp://ftp.ncbi.nlm.nih.gov/genomes/archive/old\_refseq/Bacteria/Escherichia\_coli\_K\_12\_substr\_\_MG1655\_uid57779/NC\_000913.gbk](ftp://ftp.ncbi.nlm.nih.gov/genomes/archive/old_refseq/Bacteria/Escherichia_coli_K_12_substr__MG1655_uid57779/NC_000913.gbk)

After downloading that file, open the [new Import tab in the Data Slideout](../getting-started/narrative-user-guide/) and drag the genome file into your Staging area.

![](http://kbase.us/wp-content/uploads/2015/08/image2.png)

**Drag & Drop Limitations**

The drag & drop from your local computer works for many files, but there is a size limit that depends on your computer and browser. Some users have reported problems around 20 gigabases. For larger files, use the [Globus Online transfer](http://kbase.us/transfer-data-from-globus-to-kbase/).Open the pulldown menu to the right of the filename in your Staging Area and select “GenBank Genome”:

![](http://kbase.us/wp-content/uploads/2015/08/image1.png)

Now click the import icon \(up arrow\) to the right of “GenBank Genome”. The data slideout will close and an app called “Import GenBank File as Genome from Staging Area” will be added to your Narrative.

![](http://kbase.us/wp-content/uploads/2015/08/image3.png)

Notice that the name of the Genome file is already filled in, as is a suggested name for the Genome and Assembly data objects that will be created by the import \(you can change that if you like\). Adjust the source of the GenBank file or any of the advanced options if needed, then click the green Run button to start the import. When the import is finished, your Data Panel will update to show the new Genome and Assembly objects, and a report will appear in the import app cell.

![](http://kbase.us/wp-content/uploads/2015/08/image5.png)

#### Compressed/zipped files

The Genome import can handle gzipped \(.gz\) input files. However, .zip files require special handling and .Z files are not yet supported by the importers \(we are working on adding that\). You can upload a zip file to your Staging Area, but it is recommended that you use the “uncompress” button to its left \(the one with the diagonal arrows\) to unzip it before trying to import it.

![](http://kbase.us/wp-content/uploads/2015/08/image4.png)

#### Import a GenBank-formatted file from other sources

In the Staging area, beneath the box for Drag and Drop, are other options for getting data.

![](http://kbase.us/wp-content/uploads/2015/08/image6.png)

You can import data into your KBase workspace using [Globus](transferring-data-with-globus.md), or by supplying a URL for a publicly accessible FTP location, Google Drive, Dropbox, or a direct HTTP link. Options for adding data to your staging area are described [here](../getting-started/narrative-user-guide/).

#### Uploading a GFF file to your Staging area from an FTP link

For this example, we will use the E. coli K-12 MG1655 genome GFF and FASTA files from NCBI.

Open the new Import tab in the Data Slideout and click on the ‘here’ link \(below the drag & drop area\) to open an upload app.

![](http://kbase.us/wp-content/uploads/2015/08/image9.png)

The data slideout will close and an app called “Upload a File to Staging from Web” will appear in your Narrative. \(An alternative is to open the app directly from the Apps panel.\) From the app, click on the dropdown for the URL Type and select ‘FTP Link’.

We will use the following two links for the GFF and FASTA files:  
[ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/000/005/845/GCA\_000005845.2\_ASM584v2/GCA\_000005845.2\_ASM584v2\_genomic.gff.gz](ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/000/005/845/GCA_000005845.2_ASM584v2/GCA_000005845.2_ASM584v2_genomic.gff.gz)  
[ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/000/005/845/GCA\_000005845.2\_ASM584v2/GCA\_000005845.2\_ASM584v2\_genomic.fna.gz](ftp://ftp.ncbi.nlm.nih.gov/genomes/all/GCA/000/005/845/GCA_000005845.2_ASM584v2/GCA_000005845.2_ASM584v2_genomic.fna.gz)

In the Upload app, click the plus for the URLs and copy in the name of the GFF file. Hit the plus again and copy in the name of the FASTA file.

![](http://kbase.us/wp-content/uploads/2015/08/image4-2.png)

Then click the green Run button to start the upload. After the app completes the files will appear in your Staging area, which you can access via the new Import tab in the Data Slideout.

![](http://kbase.us/wp-content/uploads/2015/08/image1-2.png)

#### Importing a GFF and FASTA file from Staging

The GFF and FASTA files are now in your Staging area. Now you need to import them to your Narrative so you can use them in analyses.

In your Staging area, open the pulldown menu to the right of the GFF filename and select “GFF Genome”:

![](http://kbase.us/wp-content/uploads/2015/08/image2-3.png)

TIP: Copy the name of the FASTA file while it is on the screen. It will be needed shortly.

Now click the import icon \(up arrow\) to the right of “GFF Genome”. The data slideout will close and an app called “Import GFF/FASTA File as Genome from Staging Area” will be added to your Narrative. The GFF File Path will be filled in.

![](http://kbase.us/wp-content/uploads/2015/08/image5-2.png)

You now need to fill in the name of the FASTA file. In the line for “FASTA File Path”, type or paste in the name of the FASTA file. There is no pulldown or other help to get the name of the file right. Luckily, the name is usually a slight variation of the first name and, if you followed the hint and copied the name from the Staging area, you should be able to paste it in.

![](http://kbase.us/wp-content/uploads/2015/08/image11.png)

Notice that the name of the Scientific name is already filled in, as is a suggested name for the Genome and Assembly data objects that will be created by the import \(you can change that if you like\). You can edit the name of the output Genome object, Scientific Name, and any advanced options as needed. When ready, click the green Run button. When the import is finished, your Data Panel will update to show the new Genome and Assembly objects, and a report will appear in the import app cell.  


![](http://kbase.us/wp-content/uploads/2015/08/image3-2.png)

## FASTQ/SRA Reads

**Instructions updated for new staging import**

NOTE: the user interface for uploading your data to KBase has been updated–please see [this page](../getting-started/narrative-user-guide/) of the Narrative User Guide for instructions on how to use the new Import tab to upload data to your staging area.  


In KBase, reads from FASTQ and SRA files can be imported to create reads library data objects. The objects will either be a SingleEndLibrary or a PairedEndLibrary. The tools in KBase can then be used to assemble reads into an “Assembly” data object or to align reads to an “Assembly”. After uploading and importing reads data, you may want to refer to the documentation about [Assembly and Annotation](../using-apps-1/analysis-apps-in-kbase/assembly-and-annotation-in-kbase.md). Reads can also be used in [RNA-seq and expression analysis](../using-apps-1/analysis-apps-in-kbase/transcriptomics-and-expression-analysis-in-kbase.md).

Single-end and paired-end reads can be uploaded in FASTQ or SRA format. For FASTQ files, please ensure that your filename ends with the .fastq, .fnq, or .fq file extension. SRA files should have an extension of .sra. The uploader also accepts compressed files in these formats: .zip, .gz, .bz2, .tar.gz, .tar.bz2.

Files can be uploaded into your KBase staging area from your local computer or directly from a publicly accessible FTP or HTTP URL.

### Importing reads files from your computer

**Drag & Drop Limitations**

The drag & drop from your local computer works for many files, but there is a size limit that depends on your computer and browser. Some users have reported problems around 20 gigabases. For larger files, use the [Globus Online transfer](transferring-data-with-globus.md).

#### Single-end library in FASTQ format

For this example, we will assume that you have a local copy of the RNA transcripts of the sample SRR228087 from GenBank. This is a single-end library from Illumina sequencing. Instructions for obtaining a local copy of data from the GenBank SRA with their sratoolkit are available [here](https://www.ncbi.nlm.nih.gov/books/NBK158900/) and [here](http://www.metagenomics.wiki/tools/short-read/ncbi-sra-file-format). Other methods for obtaining the data will vary from one data provider to the next.

Once the file is on your computer, open the [new Import tab in the Data Slideout](../getting-started/narrative-user-guide/) and drag the single-end library into your Staging area.

![](http://kbase.us/wp-content/uploads/2015/08/image6-1.png)

Open the pulldown menu to the right of the filename in your staging area and select “FASTQ Reads”:  
![](http://kbase.us/wp-content/uploads/2015/08/image4-1.png)  
Now click the import icon \(up arrow\) to the right of “FASTQ Read”. The data slideout will close and an app called “Import FASTQ/SRA File as Reads from Staging Area” will be added to your Narrative.

![](http://kbase.us/wp-content/uploads/2015/08/image2-1.png)

Notice that the name of the FASTA/FASTQ file is already filled in, as is a suggested name for the Reads object that will be created by the import \(you can change that if you like\). Adjust the Sequencing Technology or any of the advanced options if needed. If this had been a metagenomic sample, we would uncheck the box next to Single Genome. When ready, click the green Run button to start the import. When the import is finished, your Data Panel will update to show the new SingleEndLibrary object, and a report will appear in the import app cell.

![](http://kbase.us/wp-content/uploads/2015/08/image10.png)

#### Paired-end library in FASTQ format

There are two ways that KBase and [GenBank SRA](https://www.ncbi.nlm.nih.gov/sra/docs/submitformats/) recognize a paired-end library. In the legacy format, a paired-end library is two files which typically have the same name but have \_1 and \_2. For example, ERR760546\_1.fastq and ERR760546\_2.fastq. The other recognized format is called Interleaved. It is an 8-line format where forward and reverse reads alternate. The example above was imported as a SingleEndLibrary object because there was a single input file and the Interleaved box was un-checked.

In this example, we will upload and import a paired-end libraray for ERR760546 in the 2-file legacy format. Open the [new Import tab in the Data Slideout](../getting-started/narrative-user-guide/) and drag the two files into your Staging area.

Open the pulldown menu to the right of the filename in your Staging Area and select “FASTQ Reads” for the first file in the pair. Then click the import icon \(up arrow\) to the right of “FASTQ Reads”. The data slideout will close and an app called “Import FASTQ/SRA File as Reads from Staging Area” will be added.

![](http://kbase.us/wp-content/uploads/2015/08/image5-1.png)

Notice that the name of the FASTA/FASTQ file is already filled in, as is a suggested name for the Reads object that will be created by the import \(you can change that if you like\).

![](http://kbase.us/wp-content/uploads/2015/08/image3-1.png)

You now need to fill in the name of the second file. In the line for “Reverse/Right FASTA/FASTQ File Path”, type in the name of the second file. There is no pulldown list or other help to get the name of the file right. Luckily, the name is usually a slight variation of the first name.

![](http://kbase.us/wp-content/uploads/2015/08/image1-1.png)

As with the single-end library example, you can make adjustments to the available options. Adjust the Sequencing Technology or any of the advanced options if needed. If this had been a single paired-end library, we would have checked the box to the right of Interleaved.

When ready, click the green Run button to start the import. When the import is finished, your Data Panel will update to show the new PairedEndLibrary object, and a report will appear in the import app cell.

If you get an error because you had a typo in the name of the second file, it is easy to correct. Click the Reset button in the app cell to allow you to change fields in the app, make the correction, and click the green Run button again.

#### Compressed/zipped files

The Reads import can handle gzipped \(.gz\) input files. However, .zip files require special handling and .Z files are not yet supported by the importers \(we are working on adding that\). You can upload a zip file to your Staging Area, but you need to click the “uncompress” button to its left \(the one with the diagonal arrows\) to unzip it before trying to import it.

![](http://kbase.us/wp-content/uploads/2015/08/image7.png)

#### Import a reads library from other sources

In the Staging area, beneath the box for Drag and Drop, there are other options for adding data to your staging area. You can import reads into KBase using Globus Online, or by supplying a URL for a publicly accessible FTP location, Google Drive, Dropbox, or a direct HTTP link.

There is also an icon with two arrows in a circle that will refresh the list of genomes that have been uploaded to your staging area.

![](http://kbase.us/wp-content/uploads/2015/08/image6.png)

If your reads are in a publicly accessible URL, you can bypass the Staging area and directly import reads into your Narrative using one of these three apps \(which you can find in the Apps panel or the App Catalog\):

* Import SRA File as Reads From Web
* Load Single-End Reads From Web
* Load Paired-End Reads From Web

\(Note that these app names may change in the near future to be more consistent.\)

**Transfer reads from JGI**

If you are a JGI user, you can transfer public genome reads and assemblies \(as well as your private data and annotated genomes\) from JGI to your KBase account—see [this page](transferring-data-from-jgi.md) for instructions.

## Flux Balance Analysis \(FBA\) Model

#### **Upload FBA Model from a SBML formatted file**

Flux Balance Analysis models can be uploaded into KBase as a Systems Biology Markup Language \(SBML\) file using the .sbml or .xml file extension. For this example, we will upload the file containing an FBA Model for _Bacillus subtilis_ 168 that has been included in the supplementary materials for this publication:

Henry, C. S., Zinner, J. F., Cohoon, M. P., & Stevens, R. L. \(2009\). [iBsu1103: a new genome-scale metabolic model of _Bacillus subtilis_ based on SEED annotations](https://genomebiology.biomedcentral.com/articles/10.1186/gb-2009-10-6-r69). Genome Biology, 10\(6\), R69. doi:10.1186/gb-2009-10-6-r69

Go to the publication, find Additional file 4, right-click and select ‘Save Link As …’ to download and save FBA Model

Double-check that the _Bacillus subtilis_ 168 FBA Model completely downloaded by opening the file in a text or code editor and ensuring that the file is 47527 lines long and ends with “&lt;/sbml&gt;.” Otherwise, the data could be corrupted and will not import properly into KBase.

In order to successfully upload an FBA Model into your KBase workspace, you first need to add the Genome that corresponds to referenced in the FBA Model you wish to upload. For this example, we’ll add the _Bacillus\_subtilis\_subsp.\_subtilis\_str.\_168_ Genome to our Narrative \(from the Public tab of the Data Browser\) before importing the FBA Model file.

To add the Genome to your Narrative, find the Data Panel along the left side of the screen and click the Add Data \(or red “+”\) button. This will open the Data Browser slideout. Select the **Example** tab at the top of the slideout, and search for “Bacillus subtillis subsp. Subtillis str. 168” genome. Mouse over the genome name and click the blue Add button.

![Import FBA SBML](http://kbase.us/wp-content/uploads/2015/08/Import-FBA-SMBL.png)

After you’ve added the _Bacillus subtilis_ 168 genome to your Data Panel, open the new Import tab in the Data Slideout and drag the FBA Model file into your Staging area.

![](http://kbase.us/wp-content/uploads/2016/12/image3.png)

**Drag & Drop Limitations**

The drag & drop from your local computer works for many files, but there is a size limit that depends on your computer and browser. Some users have reported problems around 20 gigabases. For larger files, use the [Globus Online transfer](http://kbase.us/transfer-data-from-globus-to-kbase/).

Now the FBA model is in your Staging area–it’s time to import it into your Narrative as a KBase FBA Model data object. Open the pulldown menu to the right of the filename in your Staging Area and select “FBA Model”:

![](http://kbase.us/wp-content/uploads/2016/12/image9.png)

Now click the import icon \(up arrow\) to the right of “FBA Model”. The data slideout will close and an app called “Import TSV/XLS/SBML File as an FBAModel from Staging Area” will be added to your Narrative.

![](http://kbase.us/wp-content/uploads/2016/12/image4.png)

Notice that the name of the Model file is already filled in, as is a suggested name for the FBA Model data object that will be created by the import \(you can change that if you like\). For this example, we will change it to Bacillus\_subtilus\_168.xml\_model.

At this point, the corresponding Genome needs to be linked to the FBA Model. To add the name of the Genome, use the dropdown to select the GCF\_000009045.1 genome \(Bacillus\_subtilis\_subsp.\_subtilis\_str.\_168\) in the Data Panel. Note that although specifying the Genome is optional in the app, adding a Genome with gene IDs that match genes IDs in the model is required to import gene-protein-reactions \(GPRs\). GPRs are necessary to perform gene KO in the “Run Flux Balance Analysis” App.

Next, provide the name of the biomass reaction in the SBML file, in this case “bio00006”. **NOTE: if the biomass reaction starts with “R\_”, do NOT include the “R\_” when entering the name in this field\)**. Click the + to the right of Biomass and type in the name of the first biomass. If there are additional biomass values to enter, click the + to open another parameter field for another biomass.

Click “show advanced options” and select the Genome \(in this example, the subtilis 168 genome\) which contains features referenced in the FBAModel. Adjust any of the other advanced options if needed, then click the green Run button to start the import.

![](http://kbase.us/wp-content/uploads/2016/12/image7.png)

When the import is finished, your Data Panel will update to show the new FBA Model object, and a report will appear in the import app cell.

![](http://kbase.us/wp-content/uploads/2016/12/image8.png)

**More Information**

More SBML FBA Models for various organisms can be found here: [http://systemsbiology.ucsd.edu/Downloads](http://systemsbiology.ucsd.edu/Downloads).  
For a description of how to create a COBRA-compliant SBML file that can be imported as an FBA model into KBase, please see [SBML Level Three Specifications](http://sbml.org/Documents/Specifications).

#### **Upload a FBA Model in Excel or TSV format**

Flux Balance Analysis models can be uploaded into KBase as either an Excel file \(.xls\) or via a pair of Tab-Separated Values \(.tsv\) files containing the chemical compounds and reactions present in the FBA Model. In the Excel format, the tables containing the information about the chemical compounds and reactions in an FBA Model are stored in two separate tabs respectively titled “FBAModelCompounds” and “FBAModelReactions.” For the Tab-Separated Values file format, the chemical compounds and reactions tables are saved as two separate files named “FBAModelCompounds.tsv” and “FBAModelReactions.tsv” that will be transformed into the FBA Model data object within KBase.

**FBAModelCompounds**

| id | name | formula | charge | aliases |
| :--- | :--- | :--- | :--- | :--- |
|  cpd00113 |  Isopentenyldiphosphate |  C5H10O7P2 |  -2 |  |
|  cpd02590 |  all-trans-Heptaprenyl diphosphate |  C35H58O7P2 |  -2 |  |

* id: Compound identifier; see the KBase Biochemistry reference for a list of compounds \[link\]
* name: Name of chemical compound
* formula: Chemical formula using the Hill system
* charge: Formal charge of the molecule
* aliases: Alternative names for chemical compound

**FBAModelReactions**

| id | direction | compartment | gpr | name | enzyme | pathway | reference | equation |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| rxn00001\_c0 | -&gt; | c0 | fig\|211586.9.peg.3751 | Pyrophosphate phosphohydrolase\_c0 |  |  |  | \(1\) cpd00001\[c0\] + \(1\) cpd00012\[c0\] -&gt; \(2\) cpd00067\[c0\] + \(2\) cpd00009\[c0\] |
| rxn00056\_c0 | &lt;-&gt; | c0 | fig\|211586.9.peg.1038 | Fe\(II\):oxygen oxidoreductase\_c0 |  |  |  | \(4\) cpd00067\[c0\] + \(4\) cpd10515\[c0\] + \(1\) cpd00007\[c0\] &lt;-&gt; \(4\) cpd10516\[c0\] + \(2\) cpd00001\[c0\] |

* id: Reaction identifier; see the [KBase Biochemistry reference for a list of reactions](ftp://ftp.kbase.us/assets/KBase_Reference_Data/Biochemistry)
* direction: Directionality of chemical reaction specified as forward \(-&gt;\), reversed \(&lt;-\), or equilibrium \(&lt;-&gt;\)
* compartment: Cellular compartment that the reaction takes place in; see the [Metabolic Modeling FAQ for more information](../running-common-workflows-1/faq-metabolic-modeling-in-kbase.md)
* gpr: Gene-Protein Reaction in PATRIC identifier format
* name: Protein associated with the reaction
* enzyme: Optional, can be left empty
* pathway: Optional, can be left empty
* reference: Optional, can be left empty
* equation: Chemical reaction equation specified with compound coefficients in parentheses, compound identifiers, and directional arrows

Importing an FBA Model into KBase requires you to specify reaction IDs for the biomass producing equations in the model. For a FBA Model of an individual organism, there will be a single biomass equation, while a community model may have multiple biomass producing equations. In the FBAModelReactions table, denote the biomass producing reaction of an individual organism, or the first in a community model, with an ID such as “bio1” so that this reaction is easily identifiable. For subsequent biomass producing reactions in a community model, it is recommended that you use “bio2” for the second biomass producing reaction, “bio3” for the third, and so on.

**Upload FBA Model from an Excel formatted file**

Importing using an Excel file is similar to importing SBML files. The most important requirement for the Excel file is naming the tabs “ModelCompounds” and “ModelReactions.”

In the Import app most of the options are the same as for SBML. Select a Genome from the dropdown, add a Biomass \(remember, if the biomass reaction starts with “R\_”, do NOT include the “R\_” when entering the name in this field\) and modify the FBA Model object name. The primary difference is that the default Model file type needs to be changed to “Excel”.

![](http://kbase.us/wp-content/uploads/2016/12/image10.png)

**Upload FBA Model from a tab-delimited file**

Importing a Tab-Separated file requires two files, one for reactions and one for compounds. In your Staging area \(which you access from the Import tab in the Data slideout\), go to the line with the name of the reactions file and select “FBA Model” from the dropdown.

![](http://kbase.us/wp-content/uploads/2016/12/image6.png)

Now click the import icon \(up arrow\) to the right of “FBA Model”. The data slideout will close and an app called “Import TSV/XLS/SBML File as an FBAModel from Staging Area” will be added to your Narrative.

There are two important differences between importing an FBA model from an SBML file vs. importing in tab-delimited format. First, in the import app, the default Model file type needs to be changed from SBML to Excel. Second, the app needs the name of the compounds file. In the line for “Compounds File Path”, type in the name of the compounds file. There is no pulldown or other help to get the name of the file right. Luckily, the name is usually a slight variation of the reactions file name.img src=”http://kbase.us/wp-content/uploads/2016/12/image12-1.png” alt=”” width=”637″ height=”630″ class=”screengrab alignnone size-full wp-image-13471″ /&gt;

**Compressed/zipped files**

In the example above, we used a Genome that was in the Example data. You can also import your own Genome data from a file \(go [here](data-upload-download-guide.md#genome) for more information\).

The Genome import can handle gzipped \(.gz\) input files. However, .zip files require special handling and .Z files are not yet supported by the importers \(we are working on adding that\). You can upload a zip file to your Staging Area, but it is recommended that you use the “uncompress” button to its left \(the one with the diagonal arrows\) to unzip it before trying to import it.

![](http://kbase.us/wp-content/uploads/2015/08/image4.png)

#### Associating Model with Genome

For metabolic modeling apps, correctly associating a genome with the user uploaded models is necessary for ensuring fidelity between the genome annotations and gene-protein-reactions in the metabolic model. This means that the gene IDs between the model and genome need to match. Occasionally, researchers will use locus tags or gene IDs for constructing metabolic models that are different than those found commonly in reference genomes. If the gene IDs do not match, you will need to change either the model or the genome to ensure their gene IDs match. One way to accomplish this is to locate the genome used as the reference for building the model – based on shared gene IDs – and to upload this genome into KBase before uploading the model and associating it with the genome. If the user cannot locate the genome with the gene IDs used to build the model, the best option for reconciling the gene IDs is to edit the model file \(as SBML or TSV\) to change the gene IDs contained therein to match the gene IDs of the genome. See this [public Help Board ticket](https://kbase-jira.atlassian.net/browse/PUBLIC-20) for a detailed example of how to accomplish this.

## Media

KBase offers several options for defining your own media for metabolic modeling. Within the Narrative Interface, you can use the [Create or Edit Media](https://narrative.kbase.us/#catalog/apps/fba_tools/edit_media/release) tool to build media based on the hundreds of media conditions available in KBase. You also can import your own custom media as a TSV or Excel file using the instructions below.

#### Formatting Media TSV or Excel files

If you choose to upload a custom media or use media from an external source, please ensure that it is formatted properly for use with KBase. Media can be uploaded as a TSV \(tab-separated values\) or Excel file with four columns:

* **Compound identifier** \(e.g., ModelSEED ID, KEGG ID, PubChem ID, or compound name such as “glucose”\)
* **Concentration** \(concentration of compound in mol/L\)
* **Min flux** \(minimum allowed uptake/excretion of compound\)
* **Max flux** \(maximum allowed uptake/excretion of compound\)

Currently, the concentration field is not used by any of the the metabolic modeling tools in KBase. However, it will be utilized in the future as these tools are continually developed. For now, it is best to account for these values accurately so that your media files will retain their utility pending future updates.

The “minflux” and “maxflux” columns connect media to a flux balance analysis \(FBA\) metabolic model. The values in these columns are absolute units representing the range of possible fluxes for reactions that transport the media compounds into and out of the cell. A negative flux value corresponds to excretion \(transport out of the cell\), and a positive flux value corresponds to uptake \(transport into the cell\). 

The combination of maximum and minimum flux will dictate whether uptake and/or excretion of a reagent is allowed. Assigning a positive number to “minflux” for a particular compound essentially forces uptake of that compound. Conversely, assigning a negative number to “maxflux” will force excretion of the compound.

Minimum and maximum flux are measured in mmol per gram cell dry weight per hour.

A list of all the biochemical compounds in KBase can be downloaded \(as a 4.1 MB Excel file\) here: [ftp://ftp.kbase.us/assets/KBase\_Reference\_Data/Biochemistry](ftp://ftp.kbase.us/assets/KBase_Reference_Data/Biochemistry). From this list you can find the IDs for compounds you wish to include in your custom media.

**Note:** When creating a media Excel file, the name of the worksheet that contains your media conditions must be named “MediaCompounds” or it will not upload. By default, the first sheet of any Excel file is called “Sheet1.” To rename it, find the worksheet tabs at the bottom left of the Excel file. Double-click on the default name and type in “MediaCompounds.”

Below is an example of a media file in TSV format. In this case, the compound IDs in the first column are from the KBase biochemistry database:

| compounds | concentration | minflux | maxflux |
| :--- | :--- | :--- | :--- |
| cpd00036 | 0.001 | -100 | 5 |
| cpd00048 | 0.001 | -100 | 5 |
| cpd00063 | 0.001 | -100 | 100 |
| cpd00011 | 0.001 | -100 | 100 |
| cpd10515 | 0.001 | -100 | 100 |
| cpd00104 | 0.001 | -100 | 0.1 |

#### Import media from a TSV or Excel file

For this example, you can click on this link to download a small media file onto your computer: [Fprau\_minimal\_media.tsv](http://kbase.us/wp-content/uploads/2018/03/Fprau_minimal_media.tsv)

* Open the [new Import tab](../getting-started/narrative-user-guide/) and drag & drop your media file to upload it to your staging area
* Choose Media from the data type dropdown menu in your staging area

![](http://kbase.us/wp-content/uploads/2015/08/Screen-Shot-2018-03-10-at-5.49.25-PM.png)

* Click the upload icon next to the field that now says “Media”
* An app called “Import Media file \(TSV/Excel\) from Staging Area” will be added to your Narrative

![](http://kbase.us/wp-content/uploads/2015/08/Screen-Shot-2018-03-10-at-5.49.47-PM.png)

* You can change the name that will be assigned to the Media Object if you want. Then click the green Run button.
* After the import process has completed, the Media data object will appear in your Data Panel

![](http://kbase.us/wp-content/uploads/2015/08/Screen-Shot-2018-03-10-at-5.57.29-PM.png)

## Expression Matrix

The Expression Matrix data type contains gene expression values taken under given sampling conditions.

#### **Formatting Expression Matrix TSV files**

If you are importing expression data from an external source or want to populate a file with your own data, please ensure that it is formatted properly for use with KBase. A tab-separated values \(TSV\) file is a tab delimited text file that has genes across the rows and sample observations across the columns. Make sure the first label in the first column is “feature\_ids” followed by tab-delimited labels for samples.

For this example, we will use the Shewanella\_oneidensis\_MR-1 genome and the Shewanella\_MR-1\_M3D\_ExpData expression data set from the Example data tab. \(When working with your own data, you can start with an empty Expression Matrix template.\)

For this example, we will use the Shewanella\_oneidensis\_MR-1 Genome from the **Example** data tab. To [add the Genome to your Narrative](../getting-started/narrative-user-guide/), find the Data Panel along the left side of the screen and click the Add Data \(or red “+”\) button. This will open the Data Browser slideout. Select the **Example** tab at the top of the slideout, and search for “Shewanella\_oneidensis\_MR-1” genome. Mouse over the Genome name and click the blue Add button.

![](http://kbase.us/wp-content/uploads/2016/04/image5.png)

The S. oneidensis Genome object should appear in your Data Panel.

Do the same for the Shewanella\_MR-1\_M3D\_ExpData expression data set: find it in the Example tab and click the “Add” button to add it to your Narrative. You should now see both the Genome and the Expression Matrix in your Data Panel.

![](http://kbase.us/wp-content/uploads/2015/08/image4-3.png)

Each gene measured in the expression dataset should have an identifier listed in the first column of the TSV file. To ensure that the gene identifiers listed in your dataset correspond to the aliases in KBase, click the name of the Genome to open up the genome viewer. Click on the tab labeled Browse Features and locate a gene of interest by searching for the name of the function or protein associated with the gene. In this example, we’ll search for ‘DNA Polymerase’ and identify SO\_0009 as a gene of interest.

![](http://kbase.us/wp-content/uploads/2015/08/image1-3.png)

Click the Feature ID of the gene of interest to open up a new tab with additional information about the gene. Locate the section titled Aliases and crosscheck the gene labels contained within your expression dataset with either the Feature ID or one of these aliases to ensure that these labels will correspond to features in KBase.

To see an example Expression Matrix format, [download](data-upload-download-guide.md#downloading-data) the Shewanella\_MR-1\_M3D\_ExpData expression data set from your Data Panel. Unzip the downloaded file and examine the file matrix.tsv. In Excel, a few of the rows and columns are:

![](http://kbase.us/wp-content/uploads/2015/08/image7-1.png)

The first column matches feature IDs from the genome. This column could have also been a gene alias. Some of the gene aliases supported by KBase include NCBI, EMBL, UniProt, BioCyc, and ASAP. The column heading are sample conditions. The remaining cells in the table contain expression values for the appropriate gene and sample. Be sure to exclude gene features that are missing all expressions or are composed of non-changing expressions across the samples.

Below is an example of a properly formatted expression data file in TSV format. In this case, the gene-ids in the first correspond to gene identifiers for _E. coli_ K-12 MG1655 genes and the sample conditions are derived from the [Many Microbe Microarrays Database \(M3D\)](http://m3d.mssm.edu/about.html).

| feature\_ids | dinI\_U\_N0025\_r1 | dinI\_U\_N0025\_r2 | dinI\_U\_N0025\_r3 |
| :--- | :--- | :--- | :--- |
| b4634 | 9.05367 | 9.07827 | 9.10114 |
| b3241 | 7.20924 | 7.08695 | 7.07071 |
| b3240 | 7.21535 | 7.14312 | 7.19478 |

If you want to build an expression matrix with your own data, download an [empty template](http://kbase.us/wp-content/uploads/2015/08/matrix.tsv) and populate it with your expression data.

**Additional Information for Plant Expression Data**

For KBase plant genomes, the gene IDs retain the data structure from the external source databases \(Ensembl or Phytozome\) and do not have aliases as mentioned above. When constructing an expression dataset, append your gene IDs with the transcript IDs followed by “.CDS” as seen in the screenshot below. You can check that you have the correct gene IDs using the same method detailed in the **Formatting Expression Matrix TSV files** section.

![Plants1](http://kbase.us/wp-content/uploads/2015/08/Plants1.png)

#### Upload an Expression Matrix from a TSV-formatted file

For this example, we will upload the expression dataset from above containing expression values for Shewanella oniedensis MR-1.

Expression Matrices can be uploaded into KBase without a Genome, but they will have limited use. In order to successfully upload an Expression Matrix into KBase, you first need to add the Genome that corresponds to references in the Expression Matrix you wish to upload. For the example we’ve been using, the Genome was added above from the Example data tab.

Now open the new Import tab in the Data Slideout and drag into your Staging area the example expression matrix file that you just downloaded \(matrix.tsv\). \(Go [here](../getting-started/narrative-user-guide/) if you need instructions on doing that.\)  


**Drag & Drop Limitations**

The drag & drop from your local computer works for many files, but there is a size limit that depends on your computer and browser. Some users have reported problems around 20 gigabases. For larger files, use the [Globus Online transfer](transferring-data-with-globus.md).Now the expression matrix is in your Staging area and you can import it from there into your Narrative. Open the pulldown menu to the right of the filename in your Staging Area and select “Expression Matrix”:

![](http://kbase.us/wp-content/uploads/2015/08/image9-1.png)

Click the import icon \(up arrow\) to the right of “Expression Matrix”. The data slideout will close and an app called “Import TSV File as Expression Matrix From Staging Area” will be added to your Narrative.

![](http://kbase.us/wp-content/uploads/2015/08/image10-1.png)

Notice that the name of the Tab-delimited \(TSV\) file is already filled in, as is a suggested name for the Expression Matrix data object that will be created by the import \(you can change that if you like\).

At this point, the corresponding genome is optional and hasn’t been linked to the expression matrix. To add the name of the Genome, click on the ‘show advanced’ link to the right of ‘Input Objects’ in the Import app:

![](http://kbase.us/wp-content/uploads/2015/08/image11-2.png)

Use the Genome dropdown to select the Shewanella\_oneidensis\_MR-1 genome. Adjust any of the other advanced options if needed, then click the green Run button to start the import. When the import is finished, your Data Panel will update to show the new Expression Matrix object, and a report will appear in the import app cell.

**Compressed/zipped files**

In the example above, we used a Genome that was in the Example data. You can also import your own Genome data from a file \(go [here](data-upload-download-guide.md#genome) for more information\).

The Genome import can handle gzipped \(.gz\) input files. However, .zip files require special handling and .Z files are not yet supported by the importers \(we are working on adding that\). You can upload a zip file to your Staging Area, but it is recommended that you use the “uncompress” button to its left \(the one with the diagonal arrows\) to unzip it before trying to import it.

## Phenotype Set

The Phenotype Set data type represents experimental data about an organism’s ability to grow on a specific media condition, recorded as either growth or no growth.

**Formatting Phenotype TSV or Excel files**

A Phenotype Set can be uploaded from a TSV \(tab-separated values\) file with a .tsv or .tab file extension, or from Excel spreadsheet with a .xls extension. The spreadsheet needs to have exactly these five columns:

* Gene knockout \(geneko\) – List of genes knocked out in the phenotype; use none for wild-type phenotypes. Gene IDs should be in the same format that appears in your metabolic model \(e.g., kb\|g.220339.CDS.2927\)
* Workspace information \(mediaws\) – Workspace where the media for the phenotype data was loaded into KBase. The workspace information can be found in the Narratives tab by clicking _Show Advanced Controls_ at the end of the list of Narratives
* Media – ID of the media condition loaded in KBase where the phenotype was observed.
* Additional Compounds \(addtlCpd\) – Additional media compound IDs to be added alongside the primary media formulation. See the [KBase biochemistry database](ftp://ftp.kbase.us/assets/KBase_Reference_Data/Biochemistry/compounds.xls) to locate specific compound IDs.
* Growth – Indication of whether or not the organism grew in the specified media with the specified knockouts. 1 means growth; 0 means no growth.

| geneko | mediaws | media | addtlCpd | growth |
| :--- | :--- | :--- | :--- | :--- |
| SO\_0009 | KBaseMedia | C-D-Glucose |  | 0 |
| SO\_0009 | KBaseMedia | C-D-Lactate |  | 1 |
| SO\_0009 | KBaseMedia | C-acetate |  | 1 |

For this example, we will use the Shewanella\_oneidensis\_MR-1 Genome from the **Example** data tab. To [add the Genome to your Narrative](../getting-started/narrative-user-guide/), find the Data Panel along the left side of the screen and click the Add Data \(or red “+”\) button. This will open the Data Browser slideout. Select the **Example** tab at the top of the slideout, and search for “Shewanella\_oneidensis\_MR-1” genome. Mouse over the Genome name and click the blue Add button.

![](http://kbase.us/wp-content/uploads/2016/04/image5.png)

The S. oneidensis Genome object should appear in your Data Panel.

To download an example phenotype set data table, right-click [here](http://kbase.us/wp-content/uploads/2018/04/ExamplePhenotypeSet.tsv) and choose “Save as”.

Now open the new Import tab in the Data Slideout and drag the example phenotype set file that you just downloaded into your Staging area \(go [here](../getting-started/narrative-user-guide/) if you need instructions on doing that\).

Now the phenotype set is in your Staging area–it’s time to import it into your Narrative as a KBase Phenotype Set data object. Open the pulldown menu to the right of the filename in your Staging Area and select “Phenotype Set”:

![](http://kbase.us/wp-content/uploads/2016/04/image1.png)

Now click the import icon \(up arrow\) to the right of “Phenotype Set”. The data slideout will close and an app called “Import TSV File as Phenotype Set From Staging Area” will be added to your Narrative.

![](http://kbase.us/wp-content/uploads/2016/04/image6.png)

Notice that the name of the Phenotype TSV file is already filled in, as is a suggested name for the Phenotype Set data object that will be created by the import \(you can change that if you like\).

At this point, the corresponding Genome hasn’t been linked to the phenotype set. To add the name of the Genome, click on the dropdown in the app to select the Shewanella\_oneidensis\_MR-1 genome that you added to your Narrative earlier. Then click the green Run button to start the import. When the import is finished, your Data Panel will update to show the new Phenotype Set object, and a report will appear in the import app cell.

![](http://kbase.us/wp-content/uploads/2016/04/image7.png)

In the example above, we used a Genome that was in the Example data. You can also import your own Genome data from a file \(go [here](data-upload-download-guide.md#genome) for more information\).

**Compressed/zipped files**

The Genome import can handle gzipped \(.gz\) input files. However, .zip files require special handling and .Z files are not yet supported by the importers \(we are working on adding that\). You can upload a zip file to your Staging Area, but it is recommended that you use the “uncompress” button to its left \(the one with the diagonal arrows\) to unzip it before trying to import it.  


![](http://kbase.us/wp-content/uploads/2015/08/image4.png)

## Downloading Data

After analyzing data in KBase, you may wish to download the results to your local computer. The Narrative Interface offers the ability to download many of the data types stored in KBase in common formats. Additional data types and output formats will be supported soon.

**Download data from your Narrative**

* * Locate the data you wish to download in the Data panel under the Analyze tab
  * Hover your mouse over the data object until a “…” symbol appears to the right of its name
  * Click the “…” symbol to reveal advanced options
  * Click the sixth icon from the left, Export / Download Data
  * Select a format for exporting and downloading the data
  * Your data will download to the default downloads folder on your computer

![Download](http://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-01-at-1.44.53-PM.png)

When downloading data from KBase, the data will be compressed into a Zip file \(.zip\) containing files \(or a directory containing files\) in the format you selected and a metadata file \(in JSON format\). If you choose to re-upload data you have downloaded from the system, take note that you cannot directly import the Zip file – you must first extract the file and then re-upload using the specified uploader for the data type.

**Downloading Large Data Objects**

Large data objects include many Reads, Assemblies, Genomes, and Alignment \(BAM\) objects. They encounter many of the same obstacles as uploading large data sets. Just like uploading, this is a 2-stage process; copy the file to the Staging area and download from Staging to your local computer with [Globus](http://kbase.us/transfer-data-from-globus-to-kbase/).

_Copy the file to the Staging area \(version 1\)_

* Locate the data you wish to download in the Data panel under the Analyze Tab
* Hover your mouse over the data object until a “…” symbol appears to the right of its name
* Click the “…” symbol to reveal advanced options
* Click the sixth icon from the left, Export/Download Data
* Select Staging

![Download](http://kbase.us/wp-content/uploads/2019/01/Picture1.png)

This will open the app for “Export Data Object to Staging Area”

![Download](http://kbase.us/wp-content/uploads/2019/01/Picture2.png)

The name of the Input Object has already been filled in. A default Destination Directory is filled in but can be changed. A directory will be created in the Staging area, and all the created files will be copied to the directory. The advanced options may have more options that are relevant to your object.

Once in the Staging area, large files \(&gt;10GB\) should be transferred to your local machine using [Globus](transferring-data-with-globus.md). Instead of “To” the “KBase Bulk Share” endpoint, this will be a transfer “From” the “KBase Bulk Share” endpoint.

_Copy the file to the Staging area \(version 2\)_

* In the App Panel, search for the app “Export Data Object to Staging Area,” put in the name of your Input Object, and follow the instructions above.

**Download links in App Cells**

A few apps have file links as part of the output at the bottom of the App Cell.

![Download](http://kbase.us/wp-content/uploads/2019/01/Picture3.png)

Right click on the file name you want to download and choose “Save Link As.”

**Bulk Download Coming Soon**

By popular request, KBase will be rolling out new apps soon that enable Bulk Download of multiple data objects.


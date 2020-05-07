# FASTQ/SRA Reads

In KBase, reads from FASTQ and SRA files can be imported to create reads library data objects. The objects will either be a SingleEndLibrary or a PairedEndLibrary. The tools in KBase can then be used to assemble reads into an “Assembly” data object or to align reads to an “Assembly." After uploading and importing reads data, you may want to refer to the documentation about [Assembly and Annotation](../../using-apps-1/analysis-apps-in-kbase/assembly-and-annotation-in-kbase.md). Reads can also be used in [RNA-seq and expression analysis](../../using-apps-1/analysis-apps-in-kbase/transcriptomics-and-expression-analysis-in-kbase.md).

Single-end and paired-end reads can be uploaded in FASTQ or SRA format. For FASTQ files, please ensure that your filename ends with the .fastq, .fnq, or .fq file extension. SRA files should have an extension of .sra. The uploader also accepts compressed files in these formats: .zip, .gz, .bz2, .tar.gz, .tar.bz2.

Files can be uploaded into your KBase staging area from your local computer or directly from a publicly accessible FTP or HTTP URL.

## Importing reads files from your computer

## **Drag & Drop Limitations**

The drag & drop from your local computer works for many files, but there is a size limit that depends on your computer and browser. Some users have reported problems around 20 gigabases. For larger files, use the [Globus Online transfer](../transferring-data-with-globus.md).

## Single-end library in FASTQ format

For this example, we will assume that you have a local copy of the RNA transcripts of the sample SRR228087 from GenBank. This is a single-end library from Illumina sequencing. Instructions for obtaining a local copy of data from the GenBank SRA with their sratoolkit are available [here](https://www.ncbi.nlm.nih.gov/books/NBK158900/) and [here](http://www.metagenomics.wiki/tools/short-read/ncbi-sra-file-format). Other methods for obtaining the data will vary from one data provider to the next.

Once the file is on your computer, open the [new Import tab in the Data Slideout](../../getting-started/narrative-user-guide/add-data-to-your-narrative.md#uploading-data-from-external-sources) and drag the single-end library into your Staging area.

![](http://kbase.us/wp-content/uploads/2015/08/image6-1.png)

Open the pulldown menu to the right of the filename in your staging area and select “FASTQ Reads”:  
![](http://kbase.us/wp-content/uploads/2015/08/image4-1.png)  
Now click the import icon \(up arrow\) to the right of “FASTQ Read”. The data slideout will close and an app called “Import FASTQ/SRA File as Reads from Staging Area” will be added to your Narrative.

![](http://kbase.us/wp-content/uploads/2015/08/image2-1.png)

Notice that the name of the FASTA/FASTQ file is already filled in, as is a suggested name for the Reads object that will be created by the import \(you can change that if you like\). Adjust the Sequencing Technology or any of the advanced options if needed. If this had been a metagenomic sample, we would uncheck the box next to Single Genome. When ready, click the green Run button to start the import. When the import is finished, your Data Panel will update to show the new SingleEndLibrary object, and a report will appear in the import app cell.

![](http://kbase.us/wp-content/uploads/2015/08/image10.png)

## Paired-end library in FASTQ format

There are two ways that KBase and [GenBank SRA](https://www.ncbi.nlm.nih.gov/sra/docs/submitformats/) recognize a paired-end library. In the legacy format, a paired-end library is two files which typically have the same name but have \_1 and \_2. For example, ERR760546\_1.fastq and ERR760546\_2.fastq. The other recognized format is called Interleaved. It is an 8-line format where forward and reverse reads alternate. The example above was imported as a SingleEndLibrary object because there was a single input file and the Interleaved box was un-checked.

In this example, we will upload and import a paired-end libraray for ERR760546 in the 2-file legacy format. Open the [new Import tab in the Data Slideout](../../getting-started/narrative-user-guide/add-data-to-your-narrative.md#uploading-data-from-external-sources) and drag the two files into your Staging area.

Open the pulldown menu to the right of the filename in your Staging Area and select “FASTQ Reads” for the first file in the pair. Then click the import icon \(up arrow\) to the right of “FASTQ Reads”. The data slideout will close and an app called “Import FASTQ/SRA File as Reads from Staging Area” will be added.

![](http://kbase.us/wp-content/uploads/2015/08/image5-1.png)

Notice that the name of the FASTA/FASTQ file is already filled in, as is a suggested name for the Reads object that will be created by the import \(you can change that if you like\).

![](http://kbase.us/wp-content/uploads/2015/08/image3-1.png)

You now need to fill in the name of the second file. In the line for “Reverse/Right FASTA/FASTQ File Path”, type in the name of the second file. There is no pulldown list or other help to get the name of the file right. Luckily, the name is usually a slight variation of the first name.

![](http://kbase.us/wp-content/uploads/2015/08/image1-1.png)

As with the single-end library example, you can make adjustments to the available options. Adjust the Sequencing Technology or any of the advanced options if needed. If this had been a single paired-end library, we would have checked the box to the right of Interleaved.

When ready, click the green Run button to start the import. When the import is finished, your Data Panel will update to show the new PairedEndLibrary object, and a report will appear in the import app cell.

If you get an error because you had a typo in the name of the second file, it is easy to correct. Click the Reset button in the app cell to allow you to change fields in the app, make the correction, and click the green Run button again.

## Compressed/zipped files

The Reads import can handle gzipped \(.gz\) input files. However, .zip files require special handling and .Z files are not yet supported by the importers \(we are working on adding that\). You can upload a zip file to your Staging Area, but you need to click the “uncompress” button to its left \(the one with the diagonal arrows\) to unzip it before trying to import it.

![](http://kbase.us/wp-content/uploads/2015/08/image7.png)

## Import a reads library from other sources

In the Staging area, beneath the box for Drag and Drop, there are other options for adding data to your staging area. You can import reads into KBase using Globus Online, or by supplying a URL for a publicly accessible FTP location, Google Drive, Dropbox, or a direct HTTP link.

There is also an icon with two arrows in a circle that will refresh the list of genomes that have been uploaded to your staging area.

![](http://kbase.us/wp-content/uploads/2015/08/image6.png)

If your reads are in a publicly accessible URL, you can bypass the Staging area and directly import reads into your Narrative using one of these three apps \(which you can find in the Apps panel or the App Catalog\):

* Import SRA File as Reads From Web
* Load Single-End Reads From Web
* Load Paired-End Reads From Web

\(Note that these app names may change in the near future to be more consistent.\)

## **Transfer reads from JGI**

If you are a JGI user, you can transfer public genome reads and assemblies \(as well as your private data and annotated genomes\) from JGI to your KBase account—see [this page](../transferring-data-from-jgi.md) for instructions.

## 


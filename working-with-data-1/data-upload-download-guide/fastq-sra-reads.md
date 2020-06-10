# FASTQ/SRA Reads

In KBase, reads from FASTQ and SRA files can be imported to create reads library data objects. The objects will either be a SingleEndLibrary or a PairedEndLibrary. The tools in KBase can then be used to assemble reads into an “Assembly” data object or to align reads to an “Assembly." After uploading and importing reads data, you may want to refer to the documentation about [Assembly and Annotation](../../using-apps-1/analysis-apps-in-kbase/assembly-and-annotation-in-kbase.md). Reads can also be used in [RNA-seq and expression analysis](../../using-apps-1/analysis-apps-in-kbase/transcriptomics-and-expression-analysis-in-kbase.md).

Single-end and paired-end reads can be uploaded in FASTQ or SRA format. For FASTQ files, please ensure that your filename ends with the .fastq, .fnq, or .fq file extension. SRA files should have the .sra file extension. The uploader also accepts compressed files in .zip, .gz, .bz2, .tar.gz, .tar.bz2 formats.

Files can be uploaded into your KBase Staging Area from your local computer or directly from a publicly accessible FTP or HTTP URL.

## Importing reads files from your computer

### **Drag & Drop Limitations**

The drag & drop from your local computer works for many files, but there is a size limit that depends on your computer and browser. Some users have reported problems around 20GB. For larger files, use [Globus Online transfer](../transferring-data-with-globus.md).

### Single-end library in FASTQ format

For this example, we will assume that you have a local copy of the RNA transcripts of the sample SRR228087 from GenBank. This is a single-end library from Illumina sequencing. Follow instructions for obtaining a local copy of data from the [GenBank SRA](http://www.metagenomics.wiki/tools/short-read/ncbi-sra-file-format) with their [sratoolkit](https://www.ncbi.nlm.nih.gov/books/NBK158900/). Other methods for obtaining the data will vary from one data provider to the next.

Once the file is on your computer, open the __[_Import_ tab in the **Data Browser**](../../getting-started/narrative-user-guide/add-data-to-your-narrative.md#uploading-data-from-external-sources) and drag the single-end library into your Staging area.

![](http://kbase.us/wp-content/uploads/2015/08/image6-1.png)

Open the pulldown menu to the right of the filename in your staging area and select “FASTQ Reads."

  
![](http://kbase.us/wp-content/uploads/2015/08/image4-1.png)  
Now click the import icon \(up arrow\) to the right of “FASTQ Read”. The slide-out Data Browser will close and an app called “Import FASTQ/SRA File as Reads from Staging Area” will be added to your Narrative.

![](http://kbase.us/wp-content/uploads/2015/08/image2-1.png)

Notice that the name of the FASTA/FASTQ file is already filled in, as is a suggested Reads Object Name that will be created by the import \(you can change that if you like\). Adjust the Sequencing Technology and any of the advanced options if needed. Note that this was a metagenomic sample, we would _uncheck_ the box next to Single Genome. When ready, click the green "Run" button to start the import. When the import is finished, your Data Panel will update to show the new SingleEndLibrary object, and a report will appear in the import app cell.

![](http://kbase.us/wp-content/uploads/2015/08/image10.png)

### Paired-end library in FASTQ format

There are two ways that KBase and [GenBank SRA](https://www.ncbi.nlm.nih.gov/sra/docs/submitformats/) recognize a paired-end library. In the legacy format, a paired-end library is two files which typically have the same name but have \_1 and \_2. For example, ERR760546\_1.fastq and ERR760546\_2.fastq. The other recognized format is called Interleaved. It is an 8-line format where forward and reverse reads alternate. The example above was imported as a SingleEndLibrary object because there was a single input file and the Interleaved box was un-checked.

In this example, we will upload and import a paired-end library for ERR760546 in the 2-file legacy format. Open the __[_Import_ tab in the **Data Browser**](../../getting-started/narrative-user-guide/add-data-to-your-narrative.md#uploading-data-from-external-sources) and drag the two files into the Staging Area.

Copy the reverse reads file name to paste in a later stage.

Open the pulldown menu to the right of the filename under the _Import As..._ column in your Staging Area and select “FASTQ Reads” for the first file in the pair. Then click the import icon \(up arrow\) to the right of “FASTQ Reads”. The Data Browser slide-out will close and an app called “Import FASTQ/SRA File as Reads from Staging Area” will be added.

![](http://kbase.us/wp-content/uploads/2015/08/image5-1.png)

Notice that the name of the FASTA/FASTQ file is filled in. A suggested Reads Object Name is also created by the import and can be changed.

![](http://kbase.us/wp-content/uploads/2015/08/image3-1.png)

You now need to fill in the name of the second file. In the line for “Reverse/Right FASTA/FASTQ File Path”, either paste or type in the name of the second file. The reverse file name is usually a slight variation of the forward file name.

![](http://kbase.us/wp-content/uploads/2015/08/image1-1.png)

As with the single-end library example, you can make adjustments to the available options. Adjust the Sequencing Technology and any of the advanced options if needed. If this was a single paired-end library, we would have checked the box to the right of Interleaved.

When ready, click the green "Run" button to start the import. When the import is finished, your Data Panel will update to show the new PairedEndLibrary object, and a report will appear in the import app cell.

If you get an error due to a typo in the name of the second file, it is easy to correct. Click the Reset button in the App Cell to allow you to change fields in the app, make the correction, and click the green "Run" button again.

## Import a reads library from other sources

In the Staging Area, beneath the box for Drag and Drop, there are other options for adding data to your staging area. You can import reads into KBase using [Globus Online](../transferring-data-with-globus.md), or by supplying a URL for a publicly accessible FTP location, Google Drive, Dropbox, or a direct HTTP link.

There is also an icon with two arrows in a clockwise circle that refreshes the list of genomes that have been uploaded to the Staging Area.

![](../../.gitbook/assets/user_refresh.png)

If your reads are in a publicly accessible URL, you can bypass the Staging Area and directly import reads into your Narrative using one of these three apps \(which you can find in the Apps panel or the [App Catalog](https://kbase.us/applist/)\):

* [Import SRA File as Reads From Web](https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_sra_as_reads_from_web/release)
* [Import Single-End Reads From Web](https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/load_single_end_reads_from_URL/release)
* [Import Paired-End Reads From Web](https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/load_paired_end_reads_from_URL/release)

## **Transfer reads from JGI**

If you are a JGI user, you can transfer public genome reads and assemblies \(as well as your private data and annotated genomes\) from JGI to your KBase account—see [this page](../transferring-data-from-jgi.md) for instructions.

## 


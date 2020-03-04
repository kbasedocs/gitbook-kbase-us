# Genome

In KBase, a DNA sequence is stored in an “Assembly” data object. **A “Genome” object is the annotated version of an Assembly** and can encompass several types of feature calls. If you want to upload just the DNA sequence from a FASTA file \(without annotations\), please go to the [Assembly](assembly.md) page instead.

Currently, the Genome importer supports only GenBank and GFF-formatted files. A GenBank-formatted input file should include the sequence contig\(s\), the feature calls \(annotations\), as well as the taxonomy information for the organism. KBase parses the input file into two data objects: an assembly object with the sequence and a genome object containing the original feature calls and annotations.

GenBank-formatted files with no features can be uploaded as Genomes but they aren’t very informative until they are annotated with a KBase app. Genomes with annotation can be used as input for several KBase analyses.

A GenBank-formatted file can be uploaded into your KBase staging area from your local computer \(files with.gb, .gbff, or .gbk extensions\) or directly from an FTP or HTTP URL.

A GFF-formatted file must be paired with a corresponding FASTA file of the DNA sequence. These also will be parsed into two data objects: an assembly object with the sequence and a genome object containing the original feature calls and annotations.

Instructions for adding data to your staging area can be found [here](../../getting-started/narrative-user-guide/add-data-to-your-narrative.md#uploading-data-from-external-sources).

## Importing a GenBank-formatted file from your computer

For this example, we will use the _E. coli_ K-12 MG1655 genome GenBank file from NCBI. By clicking on the following link you can download the _E. coli_ K-12 MG1655 genome to your computer: [ftp://ftp.ncbi.nlm.nih.gov/genomes/archive/old\_refseq/Bacteria/Escherichia\_coli\_K\_12\_substr\_\_MG1655\_uid57779/NC\_000913.gbk](ftp://ftp.ncbi.nlm.nih.gov/genomes/archive/old_refseq/Bacteria/Escherichia_coli_K_12_substr__MG1655_uid57779/NC_000913.gbk)

After downloading that file, open the [new Import tab in the Data Slideout](../../getting-started/narrative-user-guide/add-data-to-your-narrative.md) and drag the genome file into your Staging area.

![](http://kbase.us/wp-content/uploads/2015/08/image2.png)

## **Drag & Drop Limitations**

The drag & drop from your local computer works for many files, but there is a size limit that depends on your computer and browser. Some users have reported problems around 20 gigabases. For larger files, use the [Globus Online transfer](../transferring-data-with-globus.md).Open the pulldown menu to the right of the filename in your Staging Area and select “GenBank Genome”:

![](http://kbase.us/wp-content/uploads/2015/08/image1.png)

Now click the import icon \(up arrow\) to the right of “GenBank Genome”. The data slideout will close and an app called “Import GenBank File as Genome from Staging Area” will be added to your Narrative.

![](http://kbase.us/wp-content/uploads/2015/08/image3.png)

Notice that the name of the Genome file is already filled in, as is a suggested name for the Genome and Assembly data objects that will be created by the import \(you can change that if you like\). Adjust the source of the GenBank file or any of the advanced options if needed, then click the green Run button to start the import. When the import is finished, your Data Panel will update to show the new Genome and Assembly objects, and a report will appear in the import app cell.

![](http://kbase.us/wp-content/uploads/2015/08/image5.png)

## Compressed/zipped files

The Genome import can handle gzipped \(.gz\) input files. However, .zip files require special handling and .Z files are not yet supported by the importers \(we are working on adding that\). You can upload a zip file to your Staging Area, but it is recommended that you use the “uncompress” button to its left \(the one with the diagonal arrows\) to unzip it before trying to import it.

![](http://kbase.us/wp-content/uploads/2015/08/image4.png)

## Import a GenBank-formatted file from other sources

In the Staging area, beneath the box for Drag and Drop, are other options for getting data.

![](http://kbase.us/wp-content/uploads/2015/08/image6.png)

You can import data into your KBase workspace using [Globus](../transferring-data-with-globus.md), or by supplying a URL for a publicly accessible FTP location, Google Drive, Dropbox, or a direct HTTP link. Options for adding data to your staging area are described [here](../../getting-started/narrative-user-guide/add-data-to-your-narrative.md).

## Uploading a GFF file to your Staging area from an FTP link

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

## Importing a GFF and FASTA file from Staging

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

## 


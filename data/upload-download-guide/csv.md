---
description: >-
  Import multiple files at once through bulk upload using a CSV file with
  extension .csv following the instructions below.
---

# CSV - prototyping

#### Prototyping and Usability: If you are interested in being a usability tester and providing feedback on the Narrative interface, fill out [this google form](https://docs.google.com/forms/d/e/1FAIpQLSdFJT3vAR0DR8UZir29nhFujCh-B0AXczhw6oylht7r9JVPRQ/viewform). 

## File Formatting

Using a CSV to upload treats the CSV as a directory containing the upload information for multiple files. The CSV must be formatted exactly for the importer to interpret it correctly. Follow the [guidelines below](csv.md#importing-a-csv-file-from-your-computer) once formatting the CSV file. 

#### CSV files require _four_ columns for uploading sequencing data when selecting files: 

1. **File Type** - In the first column, include the file type, which can be SRA Reads, Interleaved FastQ Reads, Non-interleaved FASTQ Reads, GenBank Genome, and GFF Genome. 
2. **File 1** - This column should be the name of the file including the extension and the path to the file, if it is different from the CSV. 
3. **File 2** \( as needed\) - If a second file is needed, for instance when importing a .gff or non-interleaved reads. Use the same format of file name and extension. 
4. **Output name** - The fourth column is reserved to include the output for the reads object, which will be the object name to use as the input for analysis Apps. 

#### For _parameters_, _three_ columns need to be filled:

1. **Importer Type -** In the first column, declare which importer app the parameter applies to.
2. **Parameter name -** The second column is used to indicate which parameter defined on the row
3. **Parameter value -** The third column indicates the value of the parameter

Using CSV, files of multiple types can be imported simultaneously, provided the correct formatting is used, e.g.,

| File Type or Importer Type | File 1 or Parameter name | File 2 \(if required\) or Parameter value | Output name |
| :--- | :--- | :--- | :--- |
| **SRA Reads** | sam\_smith/folder-files/file.sra |  | sra\_reads |
| SRA Reads Parameters | Sequencing Technology | _Illumina_ or _PacBio_ |  |
| SRA Reads Parameters | Single Genome | _Yes_ or _No_ |  |
| **Interleaved FASTQ** | sam\_smith/folder-files/file.fastq |  | fastq\_reads |
| Interleaved FASTQ Reads Parameters | Sequencing Technology | _Illumina_ or _PacBio_ |  |
| Interleaved FASTQ Reads Parameters | Single Genome | _Yes_ or _No_ |  |
| **Non-Interleaved FASTQ** | sam\_smith/folder-files/forward.fastq | sam\_smith/folder-files/reverse.fastq | fastq\_F\_R |
| Non-Interleaved FASTQ Parameters | Sequencing Technology | _Illumina PacBio_ |  |
| Non-Interleaved FASTQ Parameters | Single Genome | _Yes_ or _No_ |  |
| **GenBank Genome** | sam\_smith/folder-files/file.gbk |  | genome\_gbk |
| GenBank Genome Parameters | Genome Type | _Draft Isolate_ |  |
| GenBank Genome Parameters | Source of Genbank File | _RefSeq_ |  |
| **GFF Genome** | sam\_smith/folder-files/file.gff | sam\_smith/folder-files/file.fasta | genome\_gff |
| GFF Genome Parameters | Genome Type | _Draft Isolate_ |  |
| GFF Genome Parameters | Scientific Name | scientific-name |  |
| GFF Genome Parameters | Source of GFF File | Other |  |
| **Media File** | sam\_smith/folder-files/file.tsv |  | media\_tsv |

### Download a template and example of a valid import CSV: 

{% file src="../../.gitbook/assets/copyable-csv-template-template.csv" caption="CSV template / example file" %}

## Formatting - An example

Say you are importing a pair of non-interleaved FASTQ reads test\_R1.fastq and test\_R2.fastq as an object called test\_reads, you would have a row to select the files and another row for each parameter, e.g.,

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>Type</p>
        <p></p>
      </th>
      <th style="text-align:left">File 1 / Parameter</th>
      <th style="text-align:left">File 2 / Parameter value</th>
      <th style="text-align:left">Output name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Non-interleaved FASTQ Reads</td>
      <td style="text-align:left">sam_smith/folder-files/test_R1.fastq</td>
      <td style="text-align:left">sam_smith/folder-files/test_R2.fastq</td>
      <td style="text-align:left">test_reads</td>
    </tr>
    <tr>
      <td style="text-align:left">Non-interleaved FASTQ Reads Parameters</td>
      <td style="text-align:left">Sequencing Technology</td>
      <td style="text-align:left">PacBio CLR</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Non-interleaved FASTQ Reads Parameters</td>
      <td style="text-align:left">Single Genome</td>
      <td style="text-align:left">Yes</td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

## Importing a CSV file from your computer

Open the Data Browser slide-out by either clicking the Add Data or Plus buttons in the DATA Panel. Then Drag & Drop the .csv file along with the files to be imported into the drop box.

![Drag and Drop a CSV file](../../.gitbook/assets/screen-shot-2020-10-20-at-9.43.48-am.png)

Once the file appears in the Staging Area, click the check box next to the file name to select it. Click Import Selected at the bottom right corner.  

![Select file once it populates the Staging Area](../../.gitbook/assets/screen-shot-2020-10-20-at-9.44.20-am.png)

This will open the Import from CSV App. In the App, you can see the contents of the CSV file within the App to verify the file names and import settings. Click "Run" on the upper lefthand corner of the App to import the files from the .csv to the Data Panel. 



​

![When the Import from CSV Importer App opens, the file will show within the App](../../.gitbook/assets/screen-shot-2020-10-20-at-9.44.38-am.png)

![When the Import from CSV Importer App opens, the file will show within the App](../../.gitbook/assets/screen-shot-2020-10-22-at-1.32.37-pm%20%281%29.png)

​

![Import from CSV will signal that the files have been successfully imported](../../.gitbook/assets/screen-shot-2020-10-20-at-9.45.18-am.png)

Once the Importer App has run, the App will signal that the files have been imported. 

![Import from CSV will signal that the files have been successfully imported](../../.gitbook/assets/screen-shot-2020-10-22-at-1.33.12-pm.png)


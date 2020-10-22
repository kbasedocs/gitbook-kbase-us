---
description: >-
  Prototyping and Usability: Importing multiple files through bulk upload using
  CSV.
---

# CSV - prototyping

Import multiple files at once through bulk upload using a CSV file with extension .csv following the instructions below. 

## File formatting

CSV files require four columns for uploading sequencing data: 

1. **File Type** - In the first column, include the file type, which can be SRA Reads, Interleaved FastQ Reads, Non-interleaved FastQ Reads, GenBank Genome, and GFF Genome. 
2. **File 1** - This column should be the name of the file including the extension and the path to the file, if it is different from the CSV. 
3. **File 2** \( as needed\) - If a second file is needed, for instance when importing a .gff or non-interleaved reads. Use the same format of file name and extension. 
4. **Output name** - The fourth column is reserved to include the output for the reads object, which will be the object name to use as the input for analysis Apps. 

| Type | File 1 | File 2 \(if required\) | Output name |
| :--- | :--- | :--- | :--- |
| SRA Reads | sam\_smith/folder-files/file.sra |  | sra\_reads |
| Interleaved FASTQ | sam\_smith/folder-files/file.fastq |  | fastq\_reads |
| Non-Interleaved FASTQ | sam\_smith/folder-files/forward.fastq | sam\_smith/folder-files/reverse.fastq | fastq\_F\_R |
| GenBank Genome | sam\_smith/folder-files/file.gbk |  | genome\_gbk |
| GFF Genome | sam\_smith/folder-files/file.gff | sam\_smith/folder-files/file.fasta | genome\_gff |
| Media File | sam\_smith/folder-files/file.tsv |  | media\_tsv |

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


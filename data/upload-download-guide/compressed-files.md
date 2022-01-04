---
description: How to handle compressed files when uploading and importing data.
---

# Compressed/Zipped Files

### Compressed Format Types

Data importers accept compressed files in these formats: .zip, .gz, .bz, .bzip2, .bz2, .tar, .tgz.&#x20;

### Uploading and Importing Compressed Files

To add compressed data files from your computer to the KBase Narrative, follow the same three-step process for all data files.&#x20;

1. Drag & drop the data file(s) from your computer to the new Import tab to upload them to your Staging Area.
2. Choose a format for importing data from your Staging Area into your Narrative.
3. Run the Import App that is created.

When files have been uploaded to the Staging Area, compressed files have an outward-facing double arrow icon to the left of the file name.&#x20;

Click the uncompress icon to the left of the file name to uncompress the compressed/zip uploaded files before clicking the import icon. To ensure this works, the file extension must match the type of packing/compression.&#x20;

Note that importers will accept compressed files, but not archives, as imports. For instance, you can import a single reads file as reads.fastq.gz or decompress it in the staging area and import reads.fastq; however, if you have a series of files in an archive (e.g. reads1.fastq, reads2.fastq,  and reads3.fastq inside all-reads.zip), the archive will first have to be unpacked and then the files can be imported. This applies to both single and bulk imports.




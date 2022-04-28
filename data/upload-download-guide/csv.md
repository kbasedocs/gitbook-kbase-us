---
description: >-
  Import multiple files at once through bulk upload using a directory file with
  the extension .csv, .tsv, or .xls following the instructions below.
---

# Bulk Import Directory - prototyping

{% hint style="danger" %}
Import using a directory is still under development. The templates and process are subject to change prior to release.
{% endhint %}

#### Prototyping and Usability: If you are interested in being a usability tester and providing feedback on the Narrative interface, fill out [this google form](https://docs.google.com/forms/d/e/1FAIpQLSdFJT3vAR0DR8UZir29nhFujCh-B0AXczhw6oylht7r9JVPRQ/viewform).&#x20;

{% hint style="info" %}
A TSV (tab-separated values) file with a .tsv or .tab file extension, a CSV (comma-separated values) file with a .csv extension, or an Excel spreadsheet with a .xls extension can be used to upload multiple files at once.&#x20;

This approach treats the file as a directory or manifest containing the upload information for multiple files. The TSV, CSV, or Excel file must be formatted exactly to import correctly.&#x20;
{% endhint %}

#### Directory files (TSV, CSV, Excel) require _several_ columns for uploading sequencing data when selecting files. These will vary for each data type,  but make sure you have the following information:&#x20;

1. **File Path(s)** – These will be relative to your home directory of the Staging Area, so only need to include the file name if the files are at the top level. If they are within a folder called “folder1” then the file input fields should be "folder1/file1", "folder1/file2", etc.
2. **Object name** – Designate an object name for the imported file, which will be the object name to use as the input for analysis Apps.
3. **Parameters** – Any required input parameters.&#x20;

#### Assembly Example

| Assembly Example | FASTA file path             | Assembly object name | Assembly Type | Minimum contig length |
| ---------------- | --------------------------- | -------------------- | ------------- | --------------------- |
|                  | folder/assembly\_file.fasta | assembly\_object     | Draft Isolate | 500                   |

## Formatting the bulk import directory file

To create your bulk import file, you can begin by downloading the template files here:

{% file src="../../.gitbook/assets/bulk_import_csv_templates.zip" %}
Templates for Bulk Import Directory Files
{% endfile %}

{% file src="../../.gitbook/assets/working_fasta.zip" %}
Example Assemblies for Testing
{% endfile %}

Use either the plain-text CSV or TSV file or the Excel file template. In the template files 3 rows are already filled; these are required for the staging service to parse the file. In the Excel file, the top two rows are hidden to simplify the view. The third row displays the column headers for inputs, outputs, and parameters included in the Importer App.&#x20;

From here, fill out the spreadsheet as if you were filling out the Importer App. Each row corresponds to one data object to import. Some data objects will include more than one file, such as a GFF Genome. All text fields should match exactly to the display text in the Importer. For the file path, it will be relative to the home directory. If the files are at the top level, only include the file name i.e., "file.extension". If they are within a folder called “folder1” then the file input fields should be "folder1/file1.ext", "folder1/file2.ext", etc.

{% hint style="info" %}
To import multiple data types at once, either create a CSV/TSV for each type, or a tab for each type in a single Excel file.&#x20;
{% endhint %}

## Creating a template from the Narrative

To create a template CSV, TSV or Excel file from the Narrative, follow Bulk Import directions. Drag and drop your files or folders to upload to Staging. Once the files appear in the Staging Area, select at least one that represents each file type you wish to import, select the Import As file type and make sure the check box is active, then click "Import Selected." Note - if you are selecting only one file type, ensure you select two files of this type to trigger the Bulk Import App.&#x20;

This will create a Bulk Import App. Fill out the parameters for the import. Then click on the "Generate CSV Template" button. &#x20;

![Import from Staging Area Bulk Import App](../../.gitbook/assets/template\_creation\_draft.png)

This will create a pop-up file to prompt the template creation. Select the import type(s), if multiple use key controls (such as command-hold and select with Mac or control-shift and select on Microsoft). Choose the output type as either Comma-separated (CSV), Tab-separated (TSV), or Excel (XLS). Then select the appropriate output destination within the Staging Area. Click Generate template! to create the templates selected. &#x20;

![](../../.gitbook/assets/template\_generation\_csv.png)

Navigate back to the Staging Area through the "Add Data" or plus button in the Data Panel. Refresh the Staging Area if you do not see the template file in the destination you designated in the step before. Now you can download the file using the download button between to the Import As selection and trash icon.

![](../../.gitbook/assets/template\_download\_draft.png)

Open the downloaded template file. In the template files 3 rows are already filled; these are required for the staging service to parse the file. In the Excel file, the top two rows are hidden to simplify the view. The third row displays the column headers for inputs, outputs, and parameters included in the Importer App. The following rows are for each of the files to import, the files selected before will be included here.&#x20;

From here, continue out the spreadsheet as if you were filling out the Importer App with the remaining files to import. Each row corresponds to one data object to import. Some data objects will include more than one file, such as a GFF Genome. All text fields should match exactly to the display text in the Importer. Use the pre-filled rows for parameters to fill out the rest of the rows that have designated file paths.&#x20;

## Importing a CSV file

Using a file on your computer, open the [_Import_ tab within the **Data Browser**](../../getting-started/narrative/add-data.md)**.** Then drag & drop the directory file along with the files to be imported.

![Drag and Drop a CSV file](../../.gitbook/assets/screen-shot-2020-10-20-at-9.43.48-am.png)

Once the file appears in the Staging Area, select "_**Import Specification**_" from the dropdown in the _Import As..._ column. Make sure only the directory file is selected with a filled checkbox (do not select the independent files). Click _**Import Selected**_ at the bottom right corner. &#x20;

![](<../../.gitbook/assets/Screen Shot 2022-04-21 at 12.55.45 PM.png>)

Once the import specifications file has been read, it will create a bulk import cell in your Narrative and you can proceed as usual following[ the bulk import](uploads/#bulk-import-guide) directions. Verify the file names and import settings within the App. Click "Run" on the upper lefthand corner of the App to import the files from the directory into the Narrative.&#x20;

![](<../../.gitbook/assets/Screen Shot 2022-04-21 at 12.56.11 PM.png>)

Once the Importer App has run, the App will signal that the files have been imported.&#x20;

### Limitations

If you upload an invalid file, you will receive an error that lists the problem encountered. For some errors that can be fixed through the GUI, the app cell will still be created but you must correct the error before running the import.

At this stage of development only a single set of parameters can be used per import job. While we plan to add multi-parameter support in the future and have made the spreadsheet templates forward-compatible, the import specifications will only interpret the first row’s parameters.

_Troubleshooting tips:_

* Do not change the first 3 rows of the TSV or CSV file or the first row or hidden rows of Excel files. This will cause errors or incorrect data.&#x20;
* Be careful of stray cells in Excel - ensure that all the cells outside your data block are empty. Consider deleting all the rows and columns outside your data block.&#x20;
* For CSV and TSV files, be careful to always include the correct number of separator characters for every row, even if some values are blank. The importer is picky about this to help the user avoid off-by-one (or more) errors in their data.&#x20;
* Only one file or Excel tab is allowed per data type. Do not include rows for the same data type in more than one Excel tab, more than one file, a tab and an Excel file, etc.&#x20;
* In CSV and TSV files, white space around non-numerical data is ignored, and whitespace prior to numerical data is ignored.&#x20;
* In CSV and TSV files, you can use quotes (") to surround text that contains the separator character (respectively a comma or a tab).

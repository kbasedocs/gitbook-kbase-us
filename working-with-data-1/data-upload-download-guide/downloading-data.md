# Downloading Data

After analyzing data in KBase, you may wish to download the results to your local computer. The Narrative Interface offers the ability to download many of the data types stored in KBase in common formats. Additional data types and output formats will be supported soon.

## **Download data from your Narrative**

* * Locate the data you wish to download in the Data panel under the Analyze tab
  * Hover your mouse over the data object until a “…” symbol appears to the right of its name
  * Click the “…” symbol to reveal advanced options
  * Click the sixth icon from the left, Export / Download Data
  * Select a format for exporting and downloading the data
  * Your data will download to the default downloads folder on your computer

![Download](http://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-01-at-1.44.53-PM.png)

When downloading data from KBase, the data will be compressed into a Zip file \(.zip\) containing files \(or a directory containing files\) in the format you selected and a metadata file \(in JSON format\). If you choose to re-upload data you have downloaded from the system, take note that you cannot directly import the Zip file – you must first extract the file and then re-upload using the specified uploader for the data type.

## **Downloading Large Data Objects**

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

Once in the Staging area, large files \(&gt;10GB\) should be transferred to your local machine using [Globus](../transferring-data-with-globus.md). Instead of “To” the “KBase Bulk Share” endpoint, this will be a transfer “From” the “KBase Bulk Share” endpoint.

_Copy the file to the Staging area \(version 2\)_

* In the App Panel, search for the app “Export Data Object to Staging Area,” put in the name of your Input Object, and follow the instructions above.

## **Download links in App Cells**

A few apps have file links as part of the output at the bottom of the App Cell.

![Download](http://kbase.us/wp-content/uploads/2019/01/Picture3.png)

Right click on the file name you want to download and choose “Save Link As.”

## **Bulk Download Coming Soon**

By popular request, KBase will be rolling out new apps soon that enable Bulk Download of multiple data objects.


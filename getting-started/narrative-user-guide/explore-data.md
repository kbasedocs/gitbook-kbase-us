# Explore Data

There are several ways to find data and add it to your Narrative. You can select data available within KBase, [upload your own files, or import datasets from external resources](https://kbase.us/data-upload-download-guide/uploading-data/) such as the DOE Joint Genome Institute \(JGI\) or NCBI. This section will describe how to explore data already in KBase. Instructions for adding data to your Narrative and importing external files are provided in the next section, “[Add Data to Your Narrative](https://kbase.us/narrative-guide/add-data-to-your-narrative/).”

## The Data Slideout

There are several ways to explore the [wide range of data available in KBase](https://kbase.us/data-summary/).

The Data Slideout is accessed by clicking the right arrow or Add Data button in the Data Panel.

![](../../.gitbook/assets/screen-shot-2017-01-30-at-11.11.52-am.png)  
The Data Slideout will slide out, with tabs that show several data sources that will be discussed in more detail later:

* **My Data** — data you have already loaded or analyzed in another Narrative
* **Shared With Me** — data included in Narratives that have been shared with you
* **Public** — data in KBase that is accessible to everyone
* **Example** — example datasets that can be used as inputs to apps and methods
* **Import** — mechanism allowing you to import your own data \(of supported types\) to your Narrative

![](../../.gitbook/assets/screen-shot-2017-01-30-at-11.14.27-am.png)

For now, we will find a public reference genome available under the Public tab and then examine information and metadata about that genome.

Clicking the Public tab displays a list of data objects available in KBase’s reference collection.

![](../../.gitbook/assets/screen-shot-2015-02-07-at-3.49.38-pm.png)

![](../../.gitbook/assets/screen-shot-2017-01-30-at-11.19.14-am.png)  
The data-type selector at the top left of the browser window defaults to Genomes \(Note that Phytozome plant genomes are currently listed as another data type–this will change soon.\) You can change which type of data is displayed under the _Public_ tab by using this pulldown menu. More data types will be added soon.

You can also use the “Search data” field in the Data Browser to find data objects whose names include the text you’ve typed in the search box. \(Note that searches are not case-sensitive\). Enter “Vibrio brasiliensis” in the search field.

If you hover over a data object in the Data Browser panel, three small images appear: an Add button to the left of the object name and binoculars and a graph-like icon to the right. These latter two icons open a Data Landing page and a Provenance page, respectively \(see below for details\).

![](../../.gitbook/assets/screen-shot-2015-02-12-at-9.17.28-pm-e1423804700430.png)

Go ahead and click the Add button to add the Vibrio brasiliensis LMG 20546 genome to your Narrative. Notice that this genome now shows up in your Data Panel \(see image\).

[![](../../.gitbook/assets/screen-shot-2017-01-30-at-11.52.34-am.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-11.52.34-AM.png)

## Information in the Data Panel

The Data Panel shows all the data that you’ve added to your Narrative. \(The [next section](https://kbase.us/narrative-guide/add-data-to-your-narrative/) of this guide discusses in more detail how to add data to your Narrative.\)

You should have at least one object \(Vibrio brasiliensis LMG 20546\) in your Data Panel. As you add or generate more data during the course of your analyses, the number of objects in this panel will increase. You can search, sort, or filter the list using the icons in the Data Panel header.

![](../../.gitbook/assets/assets-lres-tqcrledlhbwqs-lvn_mpksnct1wpfepdt-lvnxhwckqdrazzylz_4-screen-shot-2017-01-30-at-12.01.44.png)  
You can access more details about a particular data object by hovering over the object and clicking the ” . . .” that appears to its right.

This expanded view of the data object also reveals icons that let you examine or manage the data.

* The first two icons show Apps \(in the App Panel\) that take this type of data as input or generate it as object.
* As in the Data Browser, clicking the binoculars icon opens a Data Landing page for the data object.
* The history icon allows you to see and revert to previous versions of the data.
* The graph-like icon opens the Provenance page \(described below\).
* The download icon lets you download a data object to your local computer. \(Note: This capability is still in development; most data objects currently can be downloaded only in the JSON format. In the future, you will be able to choose from a variety of common formats such as GenBank.\)
* The “A” icon lets you rename your data object. Use caution when doing this, though. If a Narrative was already using the old object name in analyses, they might stop working. Also note that object names can contain only letters, digits, and underscores; no spaces or other special characters are allowed.
* Finally, the trash icon lets you delete a data object from your Narrative. \(If the data came from a public or shared data source, the original will not be deleted, just the copy that’s in your Narrative.\)

## Data viewers

Many \(but not yet all\) types of data in KBase have viewers that allow you to find out more about the data. These viewers can be accessed two ways from the Data Panel:

1. Click the name of a data object, and its viewer will be added to your Narrative.
2. Drag the object from the Data Panel and drop it into the main part of your Narrative.

Below is the genome viewer for the Vibrio brasiliensis LMG 20546 genome that is in our Data Panel.

[![](../../.gitbook/assets/screen-shot-2017-01-30-at-12.15.29-pm.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-12.15.29-PM.png)

Notice that this genome viewer has tabs for an overview \(including GC content, taxonomy information, size, and more\) and a list of contigs and genes. Each contig and gene entry in these lists is clickable, opening either a contig browser or a tab with expanded information about the gene \(see image.\)

![](../../.gitbook/assets/image24.png)

**Sorting table entries in the viewer**

You can sort the table entries by clicking on a column header to sort by that field \(e.g., Length\). Clicking the same column header again will reverse the sort order. For example, the screenshots below show the table sorted in descending order by Contig name and then in descending order by length:  
![Screen Shot 2015-02-09 at 12.48.23 PM](../../.gitbook/assets/screen-shot-2015-02-09-at-12.48.23-pm.png)

![Screen Shot 2015-02-09 at 12.48.36 PM](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2015-02-09-at-12.48.36-PM.png)

You can even sort by more than one column at a time by clicking one column header and then Shift-clicking other column headers. For example, here we have sorted in ascending order by contig length, and then \(by shift-clicking the Genes column header\) in ascending or descending order by number of genes. Notice how the two rows with length=253 \(the bottom two, in these screenshots\) have switched places.

![](../../.gitbook/assets/screen-shot-2015-02-09-at-12.49.05-pm-e1423803707173.png)![](../../.gitbook/assets/screen-shot-2015-02-09-at-12.49.21-pm-e1423803657964.png)

There are many other types of viewers in KBase in addition to the Genome viewer discussed here. \(Documentation on these other viewers is coming soon.\) Different viewers may have different options; give them a whirl! Don’t be afraid to click on anything you see in a viewer.

To remove a viewer from your Narrative, click the trashcan icon in the top right of the viewer cell. \(You can always re-add the viewer; removing it from your Narrative doesn’t delete the data object itself.\)

## Data Landing and Provenance pages

Data Landing \(also known as Data Summary\) and Provenance pages are ways to find out even more information about a data object. You can access these pages using the icons that appear when you hover over a data object in the Data Browser or click on one of the objects in your Data Panel. The binoculars icon opens \(in a new browser tab\) a Data Landing page about that particular data object, while the graph-like icon opens a Provenance page.

**Data Landing pages** \(which are still in development\) provide both known and contextual information about a data object, allowing users to examine various particulars about the data and, eventually, compare it to other data objects. Depending on the type of data and where it came from, different sorts of information might be presented. For example, for a genome already in KBase \(such as the one we loaded earlier, [Vibrio brasilensis LMG 20546](https://narrative.kbase.us#dataview/KBasePublicGenomesV4/kb%7Cg.3791)\), you will see:

* A data object summary
* A data provenance and reference network \(collapsed by default; open it by clicking the &gt; on the left\)
* A genome overview panel that lists information about the genome, including its biological domain, DNA length, etc.
* A description of the species \(including photo, if available\)
* Publications that mention this genome
* The taxonomic lineage
* A species tree \(with the option to create a tree if one doesn’t yet exist for this species\)
* A contig browser
* Functional categories
* and more

**Provenance pages** are one way to facilitate reproducibility and transparency of scientific results, two key principles of KBase design. All data in KBase is versioned, and older versions of a data object can be accessed from the Provenance page. This page records and illustrates how data is derived and modified in KBase, including how it entered the system, whether it was produced through analysis of other objects, who generated the data, and when. You also can identify the original “owners” of the data, allowing you to contact them or see their shared analyses.

The image below shows the Provenance page for a flux balance analysis model that was generated in KBase.

![](../../.gitbook/assets/image13-1024x575.png)

In the [next section](https://kbase.us/narrative-guide/add-data-to-your-narrative/) of this guide, we will discuss in more detail how to add data to your Narrative.


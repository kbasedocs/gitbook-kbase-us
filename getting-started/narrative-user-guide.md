---
description: A more leisurely introduction to KBase's narrative interface
---

# Narrative User Guide

1. [ About This Guide](narrative-user-guide.md)
2. [ ](https://kbase.us/narrative-guide/before-getting-started/)[Access the Narrative Interface](narrative-user-guide.md)
3. [ Tour the Narrative Interface](https://kbase.us/narrative-guide/tour-the-narrative-interface/)
4. [ Your Dashboard](https://kbase.us/narrative-guide/your-dashboard/)
5. [ Job Browser](https://kbase.us/narrative-guide/job-browser/)
6. [ Create a Narrative](https://kbase.us/narrative-guide/create-a-narrative/)
7. [ Explore Data](https://kbase.us/narrative-guide/explore-data/)
8. [ Add Data to Your Narrative](https://kbase.us/narrative-guide/add-data-to-your-narrative-2/)
9. [ Browse KBase Analysis Tools](https://kbase.us/narrative-guide/browse-apps-and-methods/)
10. [ Analyze Data Using KBase Apps](https://kbase.us/narrative-guide/run-apps-and-methods-to-analyze-your-data/)
11. [ Revise Your Narrative](https://kbase.us/narrative-guide/revise-your-narrative/)
12. [ Share Narratives](https://kbase.us/narrative-guide/share-narratives/)
13. [ Access and Copy Narratives](https://kbase.us/narrative-guide/access-and-copy-narratives/)

{% tabs %}
{% tab title="1" %}
### About This Guide

This is the user guide for the Narrative Interface, the graphical user interface for accessing KBase’s functionality and data. If you are looking for a very quick \(one-page\) introduction to the Narrative Interface, please see the [Narrative Quick Start](https://kbase.us/narrative-quick-start/).

### What is the Narrative Interface?

The Narrative Interface enables researchers to design and carry out computational experiments while creating interactive, reproducible records of the data, computational steps, and thought processes underpinning their results. These records can be shared with collaborators and published as **“active papers,” called Narratives,** that let others repeat the computational experiment and even alter parameters or input data to achieve different or improved results. The Narrative Interface is built on top of the [Jupyter Notebook](http://jupyter.org/) framework.    


![](../.gitbook/assets/narrative-quickstart-11-17-small.png)
{% endtab %}

{% tab title="2" %}
### Access the Narrative Interface

The Narrative Interface is available at [narrative.kbase.us](https://narrative.kbase.us/). Once you sign in, you will see your Dashboard.

There are several ways to enter the Narrative Interface from your Dashboard:

* Use the menu at the top left of the Dashboard and select “Narrative Interface”.
* Open a public Narrative or one that has been shared with you
* Start a new Narrative by clicking the “+ New Narrative” button

{% hint style="warning" %}
#### Make sure you have the latest version

New versions of the Narrative Interface are released periodically. In most cases, KBase will automatically update to the latest version. However, if you had an older version already running, you will see a green button near the top right of your Narrative that says “New Version Available.”  
![Screen Shot 2015-02-03 at 8.16.19 PM](https://kbase.us/wp-content/uploads/2014/11/Screen-Shot-2015-02-03-at-8.16.19-PM.png)  
Click this button to update and reload the interface. You also may need to do a hard refresh \(shift-reload\) in your browser window.
{% endhint %}

#### 
{% endtab %}

{% tab title="3" %}
### Tour the Narrative Interface

{% hint style="info" %}
**Take the tour!**

To start the tour, select “Narrative Tour” from the “?” menu. This new feature walks you through the user interface, pointing out various useful aspects of it. We recommend taking the tour even if you’ve used KBase before, as it will help familiarize you with the new version.
{% endhint %}

When you open a new Narrative, a “Welcome” cell will appear at the top, offering quick tips for getting started and links for accessing help. You can collapse this cell using the “v” icon at the top left, or delete it with the trashcan icon.

Before adding data and analysis steps to your Narrative, take some time to explore a few high-level features of the Narrative Interface.

![](https://kbase.us/wp-content/uploads/2014/12/Tour-Narrative-Multicolor.png)

#### Managing Narratives and accessing resources

**1. Top menu**

* _Dashboard_ lets you access your [Dashboard](https://kbase.us/narrative-guide/your-dashboard/) from a Narrative.
* _About the Narrative_ opens a window describing Narrative Interface properties \(including version number\) and provides a link to notes about the latest KBase release.
* _Shutdown and Restart_ closes and relaunches the Narrative Interface \(which can be useful if your content fails to load or the Narrative appears frozen\).

**2. KBase logo** — Links to the KBase home page, kbase.us.

**3. Narrative title and creator** — Click in this space to name \(or rename\) your Narrative.

**4. Toggle view-only mode** — In [view-only mode](https://kbase.us/narrative-guide/access-and-copy-narratives/), you can look at the Narrative but not run or change it.

**5. Narrative controls**

* Help menu \(“?”\) links to documentation as well as to the Narrative Tour.
* Kernel menu \(intended for developers; do not use\).
* Share button lets you make your Narrative public or give specific KBase users the ability to view, edit, or share it further.
* Save — Be sure to save your work often.
* Person icon lets you sign in/out or access your user profile.

**6. Narrative tabs**

* _Analyze_ tab consists of the Data Panel \(see \#8\) and the Apps Panel below it \(see \#11\).
* _Narratives_ tab allows you to create a new Narrative, copy an existing Narrative, and see a list of other Narratives created by or shared with you.

#### Adding data and apps

**7.** **Data Panel** — You can add data to your Narrative by searching KBase’s reference collection, importing datasets from external sources, or generating new data from KBase analyses. All data objects from these activities will be listed in this panel, which is empty when you create or open a new Narrative.

**8. Data Panel controls —** Use these icons to search, filter, sort, and refresh the data in your panel. The right arrow will open the Data Browser \(see \#10\).

**9. Data object** — Each data object in the panel can be expanded to see more information about the data and several options for downloading, viewing data provenance, and more. The “[Add Data to your Narrative](https://kbase.us/narrative-guide/add-data-to-your-narrative/)” section describes how to get more information about each data object.

**10.** **Add Data** — This opens the Data browser, described in detail in the “[Explore Data](https://kbase.us/narrative-guide/explore-data/)” and “[Add Data to your Narrative](https://kbase.us/narrative-guide/add-data-to-your-narrative/)” sections, provides options for working with your own data or data from KBase’s reference collection.

**11. Apps Panel** — This panel lists KBase analysis functions. Clicking the app name or icon beside it will add an analysis cell to your Narrative \(see “[Analyze Your Data Using KBase Apps](https://kbase.us/narrative-guide/run-apps-and-methods-to-analyze-your-data/)” for details\).

**12. App controls** — ****Use these icons to search and refresh the list of apps, as well as expose apps that are available but still in beta. The right arrow will open the [App Catalog](https://narrative.kbase.us/#appcatalog), which provides advanced options for browsing apps; designating them as favorites; and filtering them based on analysis type, popularity, and more. For additional information, see [Browse KBase Analysis Tools](https://kbase.us/narrative-guide/browse-apps-and-methods/).

#### Running analyses and adding commentary

**13. Markdown cell** — Use [Markdown language](https://blog.ghost.org/markdown/) to add rich text commentary and graphics to your Narrative.

**14.** App cell — There are several types of cells, including those displaying app inputs and outputs, text and commentary, and code cells for writing custom scripts. The cell controls are at the top right of each cell.

**15.** **Markdown and code cell buttons** — Click to add these types of cells to your Narrative. Stay tuned for more documentation on how to use code cells in the future!
{% endtab %}

{% tab title="4" %}
### Your Dashboard

After signing into the Narrative Interface, you will be taken to your Dashboard, which provides an overview of your work in and use of KBase. From the Dashboard you can access existing Narratives, create new ones, contact collaborators, update your profile, and more. Main features of the Dashboard are described below.

![](https://kbase.us/wp-content/uploads/2015/02/Dashboard1-1.png)

### What’s in my Dashboard?

**Narratives**

* There are four panels for exploring and locating existing Narratives: **Your Narratives, Tutorial Narratives, Narratives Shared with You, and Public Narratives.**
* The most recently modified Narratives appear first in the panels.
* Click on any Narrative name to open it.
* Icons under a name indicate which apps the Narrative includes, how many markdown and code cells it contains, the number of times the Narrative has been shared, whether there are any running jobs, total running time for all completed jobs, and more.
* [![Screen Shot 2016-03-10 at 9.40.28 PM](https://kbase.us/wp-content/uploads/2015/02/Narrative1.png)](https://kbase.us/wp-content/uploads/2015/02/Narrative1.png) Icons under a name indicate which apps the Narrative includes, how many markdown and code cells it contains, the number of times the Narrative has been shared, whether there are any running jobs, total running time for all completed jobs, and more.
* You can use the search box at the top of each panel to find a particular Narrative within that category.
* In the **Your Narratives** panel, you can click the blue button at the top to create a new Narrative.

[![Screen Shot 2016-03-10 at 10.59.33 PM](https://kbase.us/wp-content/uploads/2015/02/Screen-Shot-2016-03-10-at-10.59.33-PM-300x43.png)](https://kbase.us/wp-content/uploads/2015/02/Screen-Shot-2016-03-10-at-10.59.33-PM.png)

Note that **Public Narratives** have not necessarily been reviewed or tested by the KBase team; they are simply Narratives that have been made public by their owners

**Metrics**

* Snapshot that shows how you’re using the system \(e.g., how many Narratives you’ve created and shared compared to other users\).
* Other metrics will be added soon, as part of KBase’s expansion of its social features.

**Common Collaborator Network**

*  People with whom you share Narratives.

### Where can I go from here?

The Dashboard offers many launch points. To the left of the **Your Narratives** panel you will see five icons allowing you to toggle between the **Dashboard**, **Catalog**, **Search**, **Jobs**, and **Account** tabs.

[![](https://kbase.us/wp-content/uploads/2015/02/Side-Bar-Toggle.png)](https://kbase.us/wp-content/uploads/2015/02/Side-Bar-Toggle.png)

**Dashboard**

* Takes you to your **Dashboard**, the features of which are described above.

**Catalog**

* You can use the **App Catalog** to browse, search for, and see the specifications of each app KBase has to offer.

**Search**

* The **Data Search** tab \(still in beta\) gives you the ability to search JGI data as well as KBase user and reference data.
* It allows you to search for data present in your own Narratives, those shared with you, and those made public by their owners.
* It also enables you to search for reads and assemblies contained in the Joint Genome Institute \(JGI\) Genomes Online Database \(GOLD\) and add them directly to your Narratives.

**Jobs**

* The [**Job Browser**](https://kbase.us/narrative-guide/job-browser/) allows you to view apps that you have run recently, see their progress, search for specific runs, and more.
* You can filter the runs by _Finished_, _Queued_, _Running_, _Success_, and _Error_
* Query results also display basic information surround the runs such as the Narrative they can be found in, App ID, Submission Time, Queue Time, Run Time, and Status

**Account**

* In the **Account Manager** you have access to edit your profile information.
* From this tab you can also get to your Profile Page which gives an overview of your Narratives and your Collaborators.
* You can access the user profile of any of your Collaborators by simply clicking on the name under the **Your Collaborators** panel while in your Profile Page.

### Top-Level Menu

The top-level menu \(accessed by clicking the three small horizontal lines on the upper left of the window\) offers additional possibilities:

[![](https://kbase.us/wp-content/uploads/2015/02/TopLevel2.png)](https://kbase.us/wp-content/uploads/2015/02/TopLevel2.png)

_Narrative Interface_ goes to the main [Narrative Interface](https://kbase.us/narrative-guide/tour-the-narrative-interface/), which allows you to create, edit, run, and share Narratives.

_JGI Search_ goes to the [Data Search](https://narrative.kbase.us/#jgi-search?q=) tab that can also be reached by the Search icon in the side bar.

_About_ goes to [a page that describes the KBase system](https://kbase.us/what-is-kbase/).

_KBase Services Status_ goes to [a page that describes the current version of KBase’s Narrative Interface](https://narrative.kbase.us/#about/services).

_Contact KBase_ lets you [contact the KBase Help Desk](https://kbase.us/contact-us/) with your question, bug report, or feature suggestion.

_Help_ brings you to the Narrative User Guide.

In the next section, we’ll discuss [how to create a new Narrative](https://kbase.us/narrative-guide/create-a-narrative/).
{% endtab %}

{% tab title="5" %}
### Job Browser

The Job Browser is one of the buttons on the left sidebar of the Dashboard. In addition to watching jobs within the narratives, the Job Browser allows you to monitor and manage your jobs. By default, it shows all jobs submitted within the last 48 hours. You can change the timeframe to an hour, a week, a month, or a custom range of dates.

![Download](https://kbase.us/wp-content/uploads/2019/01/job-browser.png)

The check boxes allow you to filter the jobs by _Finished_, _Queued_, _Running_, _Success_, and _Error._ You can check as many filters you want. Clicking one of the filters or changing the timeframe will update the page. Otherwise, the table does not auto-refresh. The two arrows in a circle to the right and below the timeframe will refresh the results in the table.

The results display basic information for the jobs such as the Narrative they can be found in, App ID, Submission Time, Queue Time, Run Time, and Status. The name of the Narrative is hot-linked, and clicking on it will open a new tab with the Narrative. The App ID is hot-linked and clicking on it will open a new tab with the catalog page for the app.

The job status cell has the status, an icon for the log, and a red cancel button. Click the log icon to expand the table and show the contents of the log. Click the icon again to collapse the table. Canceling the job will prompt you to make sure you didn’t click it accidentally.  Jobs that have been canceled may continue to show up as “Queued” or “Running” until they clear the system.
{% endtab %}

{% tab title="6" %}
### Create a Narrative

[![](https://kbase.us/wp-content/uploads/2014/11/Screen-Shot-2017-01-30-at-11.06.58-AM.png)](https://kbase.us/wp-content/uploads/2014/11/Screen-Shot-2017-01-30-at-11.06.58-AM.png)  
You can create a new Narrative from your [Dashboard](https://kbase.us/narrative-guide/your-dashboard/) by clicking the “+ New Narrative” button, which will take you to the main Narrative Interface. If you are already in the Narrative Interface, you can start a new Narrative by selecting the _Narratives_ tab \(next to  _Analyze_\) and clicking the button labeled “+ New Narrative.”

Your Narrative will open in a new browser tab and contain a default “Welcome” cell that provides brief instructions for using the Narrative Interface. You can retain this cell or delete it with the “Delete cell” item in the “…” menu in the upper right corner of the cell.

You can name your Narrative now \(by clicking on “Untitled” and entering a new name\) or wait until later. **Note that your Narrative won’t appear in your Narratives list until it is named something other than ‘Untitled’ and you have clicked the** _**Save**_ **button to save it.**

We hope that after working on your Narrative, you will want to [share it](https://kbase.us/narrative-guide/share-narratives/) with other users, but **any Narrative you create is private until you choose to share it**.

In the sections that follow, we will explain how to [explore data](https://kbase.us/narrative-guide/explore-data/), [add data to your Narrative](https://kbase.us/narrative-guide/add-data-to-your-narrative/), and use [apps](https://kbase.us/narrative-guide/browse-apps-and-methods/) to analyze it.

#### Copy and run Narratives created by others

If you don’t feel quite ready to create your own Narrative, you can copy and run a Narrative that someone else has shared with you. Please see the [Access and Copy Narratives](https://kbase.us/narrative-guide/access-and-copy-narratives/) section for more information.
{% endtab %}

{% tab title="7" %}
### Explore Data

There are several ways to find data and add it to your Narrative. You can select data available within KBase, [upload your own files, or import datasets from external resources](https://kbase.us/data-upload-download-guide/uploading-data/) such as the DOE Joint Genome Institute \(JGI\) or NCBI. This section will describe how to explore data already in KBase. Instructions for adding data to your Narrative and importing external files are provided in the next section, “[Add Data to Your Narrative](https://kbase.us/narrative-guide/add-data-to-your-narrative/).”

#### The Data Slideout

There are several ways to explore the [wide range of data available in KBase](https://kbase.us/data-summary/).

The Data Slideout is accessed by clicking the right arrow or Add Data button in the Data Panel.

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-11.11.52-AM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-11.11.52-AM.png)  
The Data Slideout will slide out, with tabs that show several data sources that will be discussed in more detail later:

* **My Data** — data you have already loaded or analyzed in another Narrative
* **Shared With Me** — data included in Narratives that have been shared with you
* **Public** — data in KBase that is accessible to everyone
* **Example** — example datasets that can be used as inputs to apps and methods
* **Import** — mechanism allowing you to import your own data \(of supported types\) to your Narrative

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-11.14.27-AM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-11.14.27-AM.png)

For now, we will find a public reference genome available under the Public tab and then examine information and metadata about that genome.

Clicking the Public tab displays a list of data objects available in KBase’s reference collection.

![Screen Shot 2015-02-07 at 3.49.38 PM](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2015-02-07-at-3.49.38-PM.png)

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-11.19.14-AM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-11.19.14-AM.png)  
The data-type selector at the top left of the browser window defaults to Genomes \(Note that Phytozome plant genomes are currently listed as another data type–this will change soon.\) You can change which type of data is displayed under the _Public_ tab by using this pulldown menu. More data types will be added soon.

You can also use the “Search data” field in the Data Browser to find data objects whose names include the text you’ve typed in the search box. \(Note that searches are not case-sensitive\). Enter “Vibrio brasiliensis” in the search field.

If you hover over a data object in the Data Browser panel, three small images appear: an Add button to the left of the object name and binoculars and a graph-like icon to the right. These latter two icons open a  Data Landing page and a Provenance page, respectively \(see below for details\).

![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2015-02-12-at-9.17.28-PM-e1423804700430.png)

Go ahead and click the Add  button to add the Vibrio brasiliensis LMG 20546 genome to your Narrative. Notice that this genome now shows up in your Data Panel \(see image\).

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-11.52.34-AM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-11.52.34-AM.png)

#### Information in the Data Panel

The Data Panel shows all the data that you’ve added to your Narrative. \(The [next section](https://kbase.us/narrative-guide/add-data-to-your-narrative/) of  this guide discusses in more detail how to add data to your Narrative.\)

You should have at least one object \(Vibrio brasiliensis LMG 20546\) in your Data Panel. As you add or generate more data during the course of your analyses, the number of objects in this panel will increase. You can search, sort, or filter the list using the icons in the Data Panel header.

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-12.01.44-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-12.01.44-PM.png)  
You can access more details about a particular data object by hovering over the object and clicking the ” . . .” that appears to its right.

This expanded view of the data object also reveals icons that let you examine or manage the data.

* The first two icons show Apps \(in the App Panel\) that take this type of data as input or generate it as object.
* As in the Data Browser, clicking the binoculars icon opens a Data Landing page for the data object.
* The history icon allows you to see and revert to previous versions of the data.
* The graph-like icon opens the Provenance page \(described below\).
* The download icon lets you download a data object to your local computer. \(Note: This capability is still in development; most data objects currently can be downloaded only in the JSON format. In the future, you will be able to choose from a variety of common formats such as GenBank.\)
* The “A” icon lets you rename your data object. Use caution when doing this, though. If a Narrative was already using the old object name in analyses, they might stop working. Also note that object names can contain only letters, digits, and underscores; no spaces or other special characters are allowed.
* Finally, the trash icon lets you delete a data object from your Narrative. \(If the data came from a public or shared data source, the original will not be deleted, just the copy that’s in your Narrative.\)

#### Data viewers

Many \(but not yet all\) types of data in KBase have viewers that allow you to find out more about the data. These viewers can be accessed two ways from the Data Panel:

1. Click the name of a data object, and its viewer will be added to your Narrative.
2. Drag the object from the Data Panel and drop it into the main part of your Narrative.

Below is the genome viewer for the Vibrio brasiliensis LMG 20546 genome that is in our Data Panel.

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-12.15.29-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-12.15.29-PM.png)

Notice that this genome viewer has tabs for an overview \(including GC content, taxonomy information, size, and more\) and a list of contigs and genes. Each contig and gene entry in these lists is clickable, opening either a contig browser or a tab with expanded information about the gene \(see image.\)

![image24](https://kbase.us/wp-content/uploads/2014/12/image24.png)

**Sorting table entries in the viewer**

You can sort the table entries by clicking on a column header to sort by that field \(e.g., Length\). Clicking the same column header again will reverse the sort order. For example, the screenshots below show the table sorted in descending order by Contig name and then in descending order by length:  
 ![Screen Shot 2015-02-09 at 12.48.23 PM](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2015-02-09-at-12.48.23-PM.png)

![Screen Shot 2015-02-09 at 12.48.36 PM](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2015-02-09-at-12.48.36-PM.png)

You can even sort by more than one column at a time by clicking one column header and then Shift-clicking other column headers. For example, here we have sorted in ascending order by contig length, and then \(by shift-clicking the Genes column header\) in ascending or descending order by number of genes. Notice how the two rows with length=253 \(the bottom two, in these screenshots\) have switched places.

![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2015-02-09-at-12.49.05-PM-e1423803707173.png)![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2015-02-09-at-12.49.21-PM-e1423803657964.png)

There are many other types of viewers in KBase in addition to the Genome viewer discussed here. \(Documentation on these other viewers is coming soon.\) Different viewers may have different options; give them a whirl! Don’t be afraid to click on anything you see in a viewer.

To remove a viewer from your Narrative, click the trashcan icon in the top right of the viewer cell. \(You can always re-add the viewer; removing it from your Narrative doesn’t delete the data object itself.\)

#### Data Landing and Provenance pages

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

**Provenance pages** are one way to facilitate reproducibility and transparency of scientific results, two key principles of KBase design. All data in KBase is versioned, and older versions of a data object can be accessed from the Provenance page. This page records and illustrates how data is derived and modified in KBase, including how it entered the system, whether it was produced through analysis of other objects, who generated the data, and when. You also can identify the original “owners”  of the data, allowing you to contact them or see their shared analyses.

The image below shows the Provenance page for a flux balance analysis model that was generated in KBase.

![image13](https://kbase.us/wp-content/uploads/2014/12/image13-1024x575.png)

In the [next section](https://kbase.us/narrative-guide/add-data-to-your-narrative/) of this guide, we will discuss in more detail how to add data to your Narrative.
{% endtab %}

{% tab title="8" %}
### Add Data to Your Narrative

Now that you are familiar with ways to find and explore data in KBase, you can select or upload data to analyze. The Data Panel in a Narrative shows the data objects that are currently available in that particular Narrative. From the Data Panel, you can access the data slideout, which allows you to search for data of interest and add it to your Narrative. In the Data Panel, click the Add Data button, the red “+” button, or the right arrow at the upper right of the panel to access the data slideout \(also referred to as the “data browser”\).

[![](https://kbase.us/wp-content/uploads/2018/01/image9.png)](https://kbase.us/wp-content/uploads/2018/01/image9.png)

{% hint style="info" %}
**Data Privacy**  
Any data that you upload to KBase is kept private unless you explicitly choose to share it. You can share any of your Narratives \(including their associated data\) with one or more specific users, or make it publicly available to all KBase users. Please see the [Sharing](https://kbase.us/narrative-guide/share-narratives/) page for more information about how to do that. The [Terms and Conditions page](https://kbase.us/terms-and-conditions/) describes the KBase data policy.
{% endhint %}

The first four tabs of the data slideout \(“My Data”, “Shared With Me”, “Public”, and “Example”\) let you search data that is already in KBase. The last tab lets you import data from your computer to your Narrative so that you can analyze it in KBase. This tab was labeled “Staging \(beta\)” and then became “Import \(New\)” and soon will become simply “Import.”

* The **My Data** tab shows data objects that you have added to your project. You may need to refresh this tab to see your most recently added data.
* The **Shared With Me** and **Public** tabs display datasets that others have loaded and made accessible to you \(or to everyone\). Data within each group is searchable and can be filtered. Since there are a large number of public datasets, you may wish to filter them by data type \(using the pulldown selector on the left\) or narrow the list by searching \(in the “Search data” text box\) for specific text in the data objects’ names.
* The **Example** tab shows datasets that have been pre-loaded for use with particular apps. These can be handy for trying out the Narrative Interface.
* The tab that’s labeled Import is the legacy importer that will soon be retired. Please use the new import tab \(see next bullet point\) instead.
* Finally, the **new Import** tab allows you to upload your own datasets for analysis. \(This capability is still under development.\) This is explained in more detail below.

#### Data available in KBase

If you hover your cursor over any data object under the first four tabs, options will appear allowing you to add that object to your Narrative or find out more about it.

![Screen Shot 2015-02-07 at 4.27.28 PM](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2015-02-07-at-4.27.28-PM.png)

In the [previous section](https://kbase.us/narrative-guide/explore-data/), we described the process of adding a genome to your Narrative from the public data in KBase. Now let’s check out the different data types available under the Example tab. The icon to the left of each data object represents its data type.

![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-30-at-12.25.07-PM.png)

As described in the previous section, the Add button next to these icons lets you add the data object to your Narrative. You can add more more data to your Narrative from the Example tab to try out various KBase apps.

#### Uploading data from external sources

The new \(early 2018\) Import tab lets you drag & drop data from your computer into your Staging Area to import into your Narrative, where you can then analyze it using KBase’s analysis apps.

![](https://kbase.us/wp-content/uploads/2018/01/image7.png)

To upload data from your computer \(or a [Globus endpoint](https://kbase.us/transfer-data-from-globus-to-kbase/) or URL\), choose the rightmost tab of the data slideout to open the new Import tab.

You can then click the “?” button just below the drop zone to launch a short interactive tour that shows the different parts of this user interface.

Getting data from your computer to your KBase Narrative is a three-step process:

1. Drag and drop the data file\(s\) from your computer to the new Import tab to upload them to your Staging Area.
2. Choose a format for importing data from your Staging Area into your Narrative.
3. Run the Import app that is created.

{% hint style="info" %}
**What is a Staging Area?**  
Your Staging Area is a sort of “halfway house” for your uploaded data files. It is private to you–no one else can see the data in your Staging Area. The files in your Staging Area stay there and can be seen from any of your Narratives. When you’re ready to add data to a Narrative, you can choose a data type from the pulldown menu next to a data file in your staging area in order to add it to your Narrative as an object of that type–see below for instructions.
{% endhint %}

{% hint style="info" %}
**Why have a Staging Area?**  
It’s more robust and extensible this way. Unlike our previous importer, the staging upload can handle large data files without timing out. The user interface is more intuitive: you can drag and drop one or more data files into your Staging Area, or even whole directories or zip files. Finally, the new importer is easier for our developers to extend to new data types.
{% endhint %}

{% hint style="info" %}
**What's the difference between 'Upload' and 'Import'?**  
In this documentation, we will use “Upload” to refer to getting data from your computer into your Staging Area and “Import” to refer to the process of converting a data file from your Staging Area into a data object in your Narrative that you can analyze with any of our analysis apps. Sometimes we use the term “Import” to cover the whole Upload+Import process.
{% endhint %}

#### Drag & drop data files into your Staging Area

{% hint style="warning" %}
**Drag & Drop Limitations**  
The drag & drop from your local computer works for many files, but there is a size limit that depends on your computer and browser. Some users have reported problems around 20 gigabases. For larger files, use the [Globus Online transfer](https://kbase.us/transfer-data-from-globus-to-kbase/).
{% endhint %}

Find the file\(s\) you want to import into your KBase account, and drag them into the drop zone \(the rectangular area surrounded by a dashed line\). You can select multiple files from your computer and drag them all at once. \(In the example below, the user is dragging two files into the dashed area.\) You can also select a folder of data files and drag the folder into the Staging Area drop zone.

![](https://kbase.us/wp-content/uploads/2018/01/image10.jpg)

If you don’t like using drag & drop, you can instead click in the upload area to open a file chooser and select a file from your computer to upload.

While files are being uploaded to your Staging Area, you’ll see a green progress bar. The upload is usually quite fast.

![](https://kbase.us/wp-content/uploads/2018/01/image5.png)

When the file is done uploading, you will see it appear in the list of files in your Staging Area. \(If you don’t see your file, try clicking the reload icon on the left above the file list to refresh the view.\) By default, these are sorted by age, with the most recently uploaded file at the top. To sort the list by other fields, such as name or size, click a column header.

![](https://kbase.us/wp-content/uploads/2018/01/image21.png)

{% hint style="warning" %}
**90-day lifetime for files in your Staging Area**  
Your Staging Area is meant to be a temporary holding area for data you want to import into your KBase account. After adding files to your Staging Area, be sure to import them into your Narrative soon, as files in the Staging Area are automatically removed after 90 days. \(Data objects that you have imported to your Narrative last indefinitely.\)
{% endhint %}

#### Transferring data from a Globus endpoint

Globus is a data management and file transfer system that can facilitate bulk transfer of data \(either large data files or a large number of files\) between two endpoints. The endpoints that apply here are KBase, JGI, and your local computer. The KBase endpoint is called “KBase Bulk Share,” and JGI has their own way to link to Globus. To do any transfer using Globus, you will [need a Globus account](https://www.globusid.org/create).

![](https://kbase.us/wp-content/uploads/2018/01/Screen-Shot-2018-01-24-at-1.54.06-PM-2.png)

[This page](https://kbase.us/transfer-data-from-globus/) has more documentation on transferring data from Globus.

{% hint style="info" %}
**Uploading data from JGI**  
If you are a JGI user, you can transfer public genome reads and assemblies \(as well as your private data and annotated genomes\) from JGI to your KBase account—see [this page](https://kbase.us/transfer-jgi-data/) for instructions.  
{% endhint %}

#### Uploading data from a URL

Below the link to Globus, another link says “Click here to use an App to upload from a public URL” \(for example, a GenBank ftp URL, or a Dropbox or Google Drive URL that is publicly accessible\).  
 

![](https://kbase.us/wp-content/uploads/2018/01/load-from-url.png)

Clicking this link adds the “Upload File to Staging from Web” app to your Narrative:

![](https://kbase.us/wp-content/uploads/2018/01/image23-1.png)

There are also several apps that import specific file types \(single- or paired-end reads or SRA files\) from a URL directly to your Narrative, bypassing your Staging Area. These are available from the Apps panel and the [App Catalog](https://narrative.kbase.us/#appcatalog).

#### Importing files from your Staging Area to your KBase Narrative

The files in your Staging Area are ready to import into your Narrative as KBase data objects that can be used in your analyses. \(You can think of a Narrative as a project or folder, which includes data that you will analyze, as well as results from those analyses.\)  
 To import a file from your Staging Area, choose a format \(data type\) from the pulldown menu to the right of the file’s age. \(You can find out more about KBase data types and accepted formats in the [Upload/Download Guide](https://kbase.us/data-upload-download-guide/).\) Then click the “import” icon to the right of the format menu.

![](https://kbase.us/wp-content/uploads/2018/01/image11.png)

When you click the “import” icon, the data slideout slides shut and an Import app cell \(tailored to the chosen format\) is created in your Narrative, with the appropriate parameters filled in. For example, here’s an import app created by choosing “GenBank” as the import format:

![](https://kbase.us/wp-content/uploads/2018/01/image6.png)

{% hint style="info" %}
**Importing different types of data**  
This example shows how to import GenBank data. Please see the [Upload/Download Guide](https://kbase.us/data-upload-download-guide/) for detailed instructions for other supported data types.  
{% endhint %}

If the GenBank file came from a different source, use the pulldown menu to select it. You can change the output object name, if desired, and then click the Run button to start the import. When the import is done, you should see the message “Finished with success” near the top of the app cell, and some information about the app run.

![](https://kbase.us/wp-content/uploads/2018/01/image2.png)

If you look at your Data Panel, you should see the new data object created by the import:  
 [![](https://kbase.us/wp-content/uploads/2018/01/image1.png)](https://kbase.us/wp-content/uploads/2018/01/image1.png)

You can now use this data object as input into the relevant KBase apps. If you want to see which apps accept a particular data type as input, you can click the “…” menu in the data object cell that appears when you hover over it, and then use the “Show Apps with this as input” icon to filter the apps in the Apps Panel:

![](https://kbase.us/wp-content/uploads/2018/01/image14.png)

{% hint style="warning" %}
**What if my import fails?**  
Sometimes an import doesn’t work. One of the most common causes of failure is attempting to import a file that’s the wrong data type, or not the expected format for that data type. For example, the screenshot below shows what a user got when they tried to import a GenBank file as Media.
{% endhint %}

![](https://kbase.us/wp-content/uploads/2018/01/image4.png)

If the importer objected to something in your file, check the [Data Upload/Download guide](https://kbase.us/data-upload-download-guide/) for details about the relevant format.  
 In some cases, the cause of an import error will not be obvious. If you can’t figure out why your import isn’t working, please contact us \(via the Help Board\) for help. Note, however, that no one besides you has access to your Staging Area, so we will not be able to see the files you uploaded to your Staging Area. You may need to attach your input file to your Help Board ticket in order for us to diagnose the problem.

#### Getting more information about files in your Staging Area

The list of files in your Staging Area includes their name, size, and age \(when they were uploaded\). If you have a lot of files in your Staging Area, you may want to use the Search box to locate specific files.

![](https://kbase.us/wp-content/uploads/2018/01/image21.png)

Compressed or zipped files have a little double-arrow icon next to the filename. You can click that icon to unpack them. You don’t need to uncompress compressed files, as they will automatically be uncompressed during import, but if you have uploaded a zip file, you can use the button to unzip it in order to access the individual files in it.

For more information about a file in your staging area, click the arrow to the left of the filename to open a tab like this:

![](https://kbase.us/wp-content/uploads/2018/01/image22.png)

You can click “First 10 lines” or “Last 10 lines” to see that portion of the file:

![](https://kbase.us/wp-content/uploads/2018/01/image13.png)

Opening the information about a file in your Staging Area also reveals a trash can icon that allows you to remove the file from your staging area.  
 [![](https://kbase.us/wp-content/uploads/2018/01/image18.png)](https://kbase.us/wp-content/uploads/2018/01/image18.png)  
 You will be asked to confirm that you want to delete the file. This action is not reversible.  
 Note that if you had already imported the file to your Narrative as a data object, that object won’t go away when you delete the file in your Staging Area. If you want to delete a data object, you can do that in your Data Panel.

{% hint style="info" %}
**In progress**  
KBase’s import functionality and user interface are under active development. We [welcome your bug reports and suggestions](https://kbase.us/contact-us/) for future upload functionality.  
{% endhint %}

#### Now what?

Once you have added data–your own data or reference data that is already in KBase–to your Narrative, you will be ready for the exciting part: analyzing it! The next two sections describe how to [choose](https://kbase.us/narrative-guide/browse-apps-and-methods/) and [run an app](https://kbase.us/narrative-guide/run-apps-and-methods-to-analyze-your-data/) to analyze your data.
{% endtab %}

{% tab title="9" %}
### Browse KBase Analysis Tools

A Narrative can include any number of analysis steps that are added by selecting one or more apps from the Apps Panel directly below your data. The apps are grouped by category. Click the arrow to the left of a category name to see the individual apps in that category.

[![](https://kbase.us/wp-content/uploads/2015/03/App-Panel-Open.png)](https://kbase.us/wp-content/uploads/2015/03/App-Panel-Open.png)

You can browse KBase apps by \(1\) scrolling through the list in the Apps Panel; \(2\) searching for an app by name; or \(3\) using the App Catalog \(click the right arrow in the top right corner of the Apps Panel to open it\)  to further explore, filter, and designate apps as favorites.

#### **Search for Apps in the Apps Panel**

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-11-28-at-3.03.38-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-11-28-at-3.03.38-PM.png)

Click the search icon at the top of the panel to begin a text search for apps. Once you enter a term, the list will show only the categories that have apps whose names include the text you typed. As before, click the right-arrow to the left of a category name to see matching apps in that category. \(To see the complete list again, click the x to the right of the search box.\)

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-11-28-at-3.05.09-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-11-28-at-3.05.09-PM.png)

Clicking the “more…” link opens an app details page featuring an expanded description of the app, along with technical information about its inputs, outputs, parameters, and more. Links to additional documentation such as tutorials or FAQs also may be provided.

#### **Access the App Catalog**

All available apps can be found in the App Catalog, which is accessible two ways:

* From [https://narrative.kbase.us/\#appcatalog](https://narrative.kbase.us/#appcatalog) \(no user account or sign-in required for browsing\).
* From the Narrative Interface, by clicking the right arrow at the top of the Apps Panel.

Much like the [Data Browser](https://kbase.us/narrative-guide/add-data-to-your-narrative/), the App Catalog will slide out, showing the available apps. \(The “View App Catalog” link at the top opens the App Catalog in a separate web browser window.\)

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-31-at-10.08.43-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-31-at-10.08.43-PM.png)

**Add your own app!**

The App Catalog is growing to contain not only the apps generated by KBase staff, but also those created and contributed by outside developers. KBase’s [software development toolkit \(SDK\)](https://kbase.us/developer/), provides a mechanism for users to add their own open-source, open-license tools to the system as new KBase apps.  


#### **Sort and Filter Apps**

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-31-at-10.11.24-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-31-at-10.11.24-PM.png)From the App Catalog, you can search for apps by name and use several options to organize and filter how they are displayed \(the default sort is by category\). Click the “Organize by” drop-down menu to see these options.

* **My Favorites** — Lists your favorite apps \(those you’ve clicked the star icon to “favorite”\) at the top of the catalog.
* **Favorites Count and Run Count** — Suggests some of the most popular and frequently used apps in KBase.
* **Name** — Filters apps by name \(alphabetically or reverse alphabetically\).
* **Category** \(default sort\) ****— Displays apps in groups by analysis type including annotation, assembly, communities, comparative genomics, expression, metabolic modeling, and more.
* **Module** — Sorts apps based on which SDK module they belong to.
* **Developer** — Displays apps alphabetically by developers’ KBase usernames, which are linked to their profile pages.[![apps\_organized\_by\_input\_type](https://kbase.us/wp-content/uploads/2014/12/apps_organized_by_input_type-300x230.png)](https://kbase.us/wp-content/uploads/2014/12/apps_organized_by_input_type.png)
* **Input Types and Output Types** —Groups apps based on the type of data that they take as input or generate as output. Each data type is linked to a specification page that provides some technical details, including version, description, structure, and more. This sort can be useful for determining the data you must add to your Narrative before using a specific app. The _**Example**_ tab of the [Data Browser](https://kbase.us/narrative-guide/add-data-to-your-narrative/) provides access to various data types to help you get started.

#### **Explore Individual Apps**

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-31-at-10.20.03-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-31-at-10.20.03-PM.png)[![Screen Shot 2017-01-31 at 10.20.11 PM](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-31-at-10.20.11-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-01-31-at-10.20.11-PM.png)

Similar to the App Panel, the App Catalog lets you \(1\) see a short description of each app \(by hovering over the “i”–see second screenshot at right\), \(2\) access the app detail page using the “more” link, and \(3\) add an app to your favorites by clicking the star.

The number beside the star icon indicates how many other users have selected the app as a favorite, while the next number shows how many times the app has been run.

You can access the app module \(a group of related apps\) by clicking its hyperlink \(in this example, “fba\_tools”\). Also, some apps will link to the KBase profile pages of their developers \(in this case, chenry\).

**Feeling adventurous?**

 [![Bucking\_Horse\_and\_Rider\_logo](https://kbase.us/wp-content/uploads/2014/12/Bucking_Horse_and_Rider_logo.png)](https://kbase.us/wp-content/uploads/2014/12/Bucking_Horse_and_Rider_logo.png)

If you want to try out apps that are still in development, you can click the little “R” in the Apps Panel, changing it to a “B”. This will show apps that are in Beta \(i.e., still being tested and debugged\). Click the “B” again to go back to “R” \(show only released apps\).  
 [![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-10-19-at-11.43.02-AM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-10-19-at-11.43.02-AM.png)

Now that you know how to find an app of interest, the [next section](https://kbase.us/narrative-guide/run-apps-and-methods-to-analyze-your-data/) will discuss how to add it to your Narrative so you can begin analyzing data.
{% endtab %}

{% tab title="10" %}
### Analyze Data Using KBase Apps

Now that you have explored the available apps and determined which ones work with the data objects in your Narrative, you can begin analyzing your data.

#### Add an app to your Narrative

To add an app to your Narrative, find the app of interest and click its name or the icon to the left of the app  name. A box \(called a _cell_\) containing the chosen app will appear in the main Narrative panel.

[![](https://kbase.us/wp-content/uploads/2015/03/Screen-Shot-2017-03-13-at-9.47.25-AM.png)](https://kbase.us/wp-content/uploads/2015/03/Screen-Shot-2017-03-13-at-9.47.25-AM.png)

A few things to notice about the app cell:

* App cells have three tabs: Configure \(which is where you set the parameters; it’s what you see when you add a new app cell\), Job Status and Result. The last two tabs are filled in once you run the app; these are discussed later.
* The up and down arrows let you move the cell up or down in your Narrative.

  [![Screen Shot 2017-02-01 at 12.56.50 PM](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-01-at-12.56.50-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-01-at-12.56.50-PM.png)

* The “…” menu offers several options for collapsing/expanding the cell; showing the code that will execute the app; getting more info \(in a separate browser window\) about the app; and deleting the cell. These are discussed more in the section called “[Revise Your Narrative](https://kbase.us/narrative-guide/revise-your-narrative/)“.
* Every app has some parameters \(fields\) that must be filled in before you can run the app.

#### Fill in parameters

After you add an app to your Narrative, the required parameters must be filled in before you can run it. For example, for most apps, you will need to select the input data object\(s\). Other parameters may also need to be set. A red arrow to the right of a field indicates that it is a required field and you have not yet entered a valid value in it. Once you enter a value, the red arrow should disappear.

Some app fields are “smart” and know which data in your Narrative is valid for that field. These “smart” fields have a pulldown list of data objects that you can choose from. \(Remember, only data \(of the appropriate type\) that you have already added to this particular Narrative will be shown in that list. You can access your data from other Narratives via the My Data and Shared with me tabs in the [Data Panel](https://kbase.us/narrative-guide/add-data-to-your-narrative/).\)

In the example app shown above, the input object field, which is required, has a pulldown list that will be populated with data objects of the appropriate type that you have added to your Narrative. Scientific Name, on the other hand, is a free text field and is optional. The next two fields \(Domain and Genetic Code\) are also required, but they are pre-filled with default values. You could change their values if you chose, or leave them as they are. Finally, the last field \(Output Genome Name\) is another free text field. In the screenshot, the Output Genome Name, is not yet filled in; it has a red arrow to the right. The Run button is not enabled until all required fields are filled in and the red arrows are gone.

Some apps have optional “advanced options” that you can reveal by clicking on the “advanced options” link at the bottom of the cell.

**Save Your Work**

![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2015-02-07-at-9.22.17-PM.png)

As you add to your Narrative, be sure to save your work frequently, using the Save button at the top right of the screen.

#### Run the app

When you have filled in all the required fields, the _Run_ button on the left side of the app will be enabled; click it to start running the app. Once clicked, the green _Run_ button will turn to a red _Cancel_ button. When the analysis starts running, you will see information in the _Job Status_ tab_**.**_

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-03-18-at-2.23.25-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-03-18-at-2.23.25-PM.png)

Depending on the analysis, the analysis might finish within a few seconds or could take hours to run. You can save your Narrative and come back to it later–the analysis will continue running even if you don’t have the Narrative open.

**Examine and download results**

When an app finishes running, you will see a summary in the Results tab, as well as an output cell below your app cell. Also, if the analysis generates a new data object, that object will be added to your Data Panel.

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-01-at-1.39.36-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-01-at-1.39.36-PM.png)

In the example, the “Annotate Microbial Contigs” app, once run, produced an output cell that provides information about the newly annotated Shewanella genome object.

This output cell has three tabs: Overview \(displayed above\), _Browse_ Contigs, which lists the large assembled pieces of a genome, and _Browse Features_, which allows browsing of all the annotated genes.

Different apps create different types of output cells when they run, depending on which type of data object is output by the app. The genome output cell shown above is an example of a _Data Viewer._ Data Viewers are described in the “[Explore Data](https://kbase.us/narrative-guide/explore-data/)” section of this guide.

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-01-at-1.42.23-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-01-at-1.42.23-PM.png)

In addition to creating a new output cell, the app we ran created a new data object and added it to our Narrative. The newly annotated genome object now appears at the top of the Data Panel.

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-01-at-1.44.53-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-01-at-1.44.53-PM.png)

Remember that you can hover over an object in the Data Panel and click the “. . .” that appears to see more information and options, including an option \(see image\) for downloading the object in GenBank or JSON format \(see the [Download Guide](https://kbase.us/data-upload-download-guide/downloading-data/) for more information\). In the future, you will be able to choose from a wider variety of common formats, allowing you to download results to use with other tools and send to colleagues.

 **KBase’s download functionality is still in development–please check back soon for new download options and improvements, and report any problems to us.**

#### **Conduct further analyses**

Once you have reviewed your results, you can use your newly generated data in additional analysis steps. Remember, you can click on the data object in the Data Panel to see which KBase apps work with that data type.

For example, our annotated genome can be used in a number of analyses because it now includes the standard KBase annotations. If you click on the genome in the Data Panel, you see several apps that apply. Among them are the [_Insert Genomes into Species Tree_ app](https://kbase.us/insert-genomes-into-species-tree-app/) that constructs a phylogenetic tree allowing you to see species closely related to your genome. You also can use the [_Build a Metabolic Model_ app](https://kbase.us/metabolic-modeling-in-kbase/) to draft a metabolic model from the annotated genome.

#### **Re-run apps with the same or different parameters**

App input cells that have already been run have a “Reset” button that allows you to redo the analysis, with the option to change any of the parameter settings \(including, perhaps, the input data\) before rerunning. Rerunning an app will overwrite the information in the app cells, but will not overwrite any data objects in your Narrative _unless_ you use the same output object name again.

#### **Report errors**

If a job fails, you will see an error message in the output cell and/or in the _Result_ tab. If you need help figuring out what went wrong, please [contact us](https://kbase.us/contact-us/) with details about what you were doing when the error occurred and what the error message said. Including the contents of the _Job Status_ tab and the URL of your Narrative will help us debug the problem. We are here to help and appreciate your feedback and error reports!

In the [next section](https://kbase.us/narrative-guide/revise-your-narrative/), we will discuss how you can revise your Narratives.
{% endtab %}

{% tab title="11" %}
### Revise Your Narrative

 You can browse a list of your Narratives in the Narratives tab:

[![Screen Shot 2017-02-02 at 11.14.14 AM](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-02-at-11.14.14-AM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-02-at-11.14.14-AM.png)

Your Narratives are shown in the _Narratives_ tab in reverse chronological order, with the most recently changed Narratives first. After your Narratives, Narratives owned by others and shared with you are listed.

#### View Narrative history and revert to earlier versions

KBase stores a history of everything you’ve done to your Narrative, so if you want, you can revert changes and go back to an earlier version. When you hover your cursor over one of your Narratives in the Narratives panel, three icons will appear.

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-02-at-11.40.57-AM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-02-at-11.40.57-AM.png)

The first of these icons lets you expose the entire history of autosaves of your Narrative.

You can then, if you wish, choose an earlier version to revert to. This capability is still in the early phase of development and should become easier to use soon.

#### Add text to your Narrative

Adding text cells to your Narrative to explain what you were doing and what the results might mean will help others understand your computational experiments, as well as helping to remind you what you were doing. You can add formatted text to your Narrative in “Markdown Cells”. Markdown is a markup language \(like, for example, HTML\). It’s pretty easy to learn but does require knowing some syntax. A good “cheat sheet” for Markdown language can be found [here](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

You can add Markdown cells to a Narrative using the translucent blue buttons at the bottom right of the main Narrative panel.

![Screen Shot 2015-02-10 at 10.01.21 PM](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2015-02-10-at-10.01.21-PM.png) 

The button on the right is the “Add Markdown Cell” button and will add a Markdown cell under the currently selected Narrative cell.

New Markdown cells contain the placeholder text “\[Empty Markdown / LaTeX cell\]” \(LaTeX is another formatting language\). To edit a Markdown cell, double-click it to enter edit mode. When you’re done, press Shift-Return to exit the cell. 

\(The &gt;\_ button adds a code cell, which is beyond the scope of this user guide. However, we will share one useful tip if you do want to try using a code cell: press Shift-Return in the cell to execute the code.\)

#### [![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-02-at-11.16.05-AM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-02-at-11.16.05-AM.png)Cell commands: move, delete, etc.

Via the arrows and menu items in a Narrative cell, you can move the cell up or down, collapse or expand it, show the code that runs the analysis, get more info about the app, or delete the app cell. The cell menu can be opened by clicking the “…” in the upper right corner of a cell.

#### Rename or delete a Narrative

To rename a Narrative, click on its name at the top of the Narrative window. A window will pop up to let you change the name.

If you decide to delete a Narrative that you own, click the trashcan icon. Delete with caution, because currently there’s no way to get your deleted Narrative back.

![](https://kbase.us/wp-content/uploads/2014/12/image31.png)

#### Advanced controls

The “Show Advanced Controls” option under the “Narratives” tab lets you “Set the Active Narrative for a Workspace”. \(Workspace is an older term for a project–a collection of data and analyses.\) You will probably not need to use this option, unless you are trying to retrieve old Narratives that you created in an old version of the Narrative Interface.

**Save your work!**

 Although your Narrative is periodically autosaved, it’s always a good idea to save your work frequently, using the Save button at the top right of the screen.  


Once you’re happy with your Narrative, you will probably want to share it with others. The [next section](https://kbase.us/narrative-guide/share-narratives/) describes how to do that.
{% endtab %}

{% tab title="12" %}
### Share Narratives

Narratives are _collaborative_ \(multiple people on your project can work on a Narrative together\), _shareable_ \(you can share your Narrative with specific people or with everyone\), _publishable_ \(a finished Narrative is similar to a research paper, and can be cited as a URL\), and _reproducible_ \(you can repeat or even change another scientist’s computational experiment if they publish it as a Narrative\). We believe that you will ultimately help both yourself and other researchers by sharing your Narratives so that others can see what you were thinking, what you did, and what you concluded from your analyses. However, rest assured that **all of your Narratives are private \(viewable only by you\) until you decide to share them.**

You can share a Narrative that you own with any set of people you choose, or with all KBase users. To share a Narrative, click the “share” button near the top right of the page. You will see the people you have already shared with \(right now, only you\).

![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-06-27-at-11.20.29-AM.png)

If you want to share your Narrative with everyone, you can click the “make public” link near the top of the sharing panel. If you only want to share it with a few people, you can type their name or username into the “share with” box. Once you have typed something that matches a name in the KBase user database, the person’s full name will appear. Click the down arrow to the right of the “share with” box to assign permissions to that user–you can allow them only to view your Narrative, to edit it, or to edit and share it.

For example, suppose you want to share your Narrative with kbasehelp so that KBase staff can help you troubleshoot it. You can start typing any part of the username or real name and a list of users that match will appear:

![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-06-27-at-11.23.17-AM.png)

The default permission level for sharing is “View only”, which lets the user you’re sharing with see the Narrative but not let them edit it or share it with others. If you want to share your Narrative with a collaborator and give them more privileges, click the down-arrow to see the permission levels and possibly choose a different one.

![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-06-27-at-11.21.20-AM.png)

You can add multiple users to share with:

![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-06-27-at-11.26.46-AM.png)

Click the “Apply” button to add the chosen user\(s\) to the sharing list for your Narrative. The usernames and permission levels for the users you shared with will appear at the bottom of the Share panel.

![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-06-27-at-11.26.54-AM.png)

You can also choose to share your Narrative with all KBase users by clicking the “make public?” link.

When you’re done sharing, click the x  to close the Share panel.

You can change the access permissions at any time by clicking the Share button again. The up/down arrows next to each user’s permissions let you change the permissions.

Note that unless you alert another user that you have shared a Narrative with them, they will not notice until they happen to see your shared Narrative in their “Narratives that have been shared with you” tab or click on your name in her collaborator list. In the future, the Narrative Interface will alert you to new Narratives that have been shared with you.

If you are working on a shared Narrative, and a collaborator is working on it at the same time, watch for a red box at the top of the screen that says “Narrative updated in another session.” You can update to the latest version by refreshing the page, but note that any changes that you made to the Narrative will be lost, and if you try to save your changes, you might overwrite your collaborator’s changes. We are working on better ways to allow simultaneous editing.

#### Create or modify your user profile

Every KBase user has a user profile. Filling in your KBase user profile helps you become part of the social web that KBase is building, making it easier to find and collaborate with other scientists and share data and Narratives. You are not required to complete your user profile in order to use KBase, but we encourage you to.

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-12-05-at-3.35.26-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-12-05-at-3.35.26-PM.png)

To see and edit your user profile, go to your Dashboard and click the “Account” button on the left side. Your profile page will open, looking something like the screenshot below. You will be able to enter or change information including your organization, department, job title, research interests, avatar, and more. Required fields are marked with a red \*. You must fill in all required fields in order to save your profile \(using the Save button on the upper right of the page\).

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-12-05-at-3.35.55-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-12-05-at-3.35.55-PM.png)

[![](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-12-05-at-3.50.59-PM.png)](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-12-05-at-3.50.59-PM.png)

Below the Save button is a small preview showing what your profile page looks like to others. You can click the “Open Your Profile Page” link to see a bigger version, along with a list of your Narratives and collaborators \(other users with whom you have shared Narratives, or who have shared Narratives with you\) and a search box for searching for other users by name or username. As you start typing in the box, you will see a list of users who have that text in their first or last name or their username. Click one of the matches to see that user’s profile.

The Account tab lets you see basic information about your KBase account. The only field that can be edited there is your preferred email address. Note that other users cannot see your email address; it will be used only by KBase staff to contact you occasionally with important information.

The Linked Sign-In Accounts tab lets you see and manage which external \(Globus or Google\) accounts are linked to your KBase account.

The user profile editor, and KBase’s social networking layer, are in development. Soon you will be able to search for other researchers whose interests overlap with yours, perhaps inviting them to collaborate. You will also be able to see how many times your Narratives were run, copied, extended or cited. Ultimately, we hope that KBase’s expanding social web will help to make systems biology research more effective, collaborative, and reproducible.
{% endtab %}

{% tab title="13" %}
### Access and Copy Narratives

#### View Narratives created by or shared with you

The Narratives tab has two sections that list Narratives that you have created \(“My Narratives”\) and, below that list, those that have been shared with you by other users. The “Shared With Me” list includes only those Narratives that were explicitly shared with you, not those that are viewable by everyone \(public Narratives\). The public Narratives can be accessed from your Dashboard.

![Screen Shot 2017-02-02 at 11.14.14 AM](https://kbase.us/wp-content/uploads/2014/12/Screen-Shot-2017-02-02-at-11.14.14-AM.png)

If you click on one of the Narratives in your Narratives panel, it will open in a new web browser window. If it’s a Narrative that you own, you will be able to run it or edit it. However, if it’s one that someone else owns and shared with you without write permission, you won’t be able to edit or run it–it will open in _View-only mode_.

**View-only mode**

The key difference you will notice when a Narrative opens in View-only mode is that there is no Analyze panel on the left side–you won’t see any data objects or apps. This is because you can’t modify or run a Narrative that was shared with you with only View permission.

![](https://kbase.us/wp-content/uploads/2015/01/Screen-Shot-2017-02-02-at-12.24.50-PM.png)

Why can’t you run a Narrative owned by someone else? Because, as we’ve seen, running an app usually creates new data objects in your Narrative, which requires write permission. If you want to run a Narrative owned by someone else who has not given you write permission, you will need to copy it to your account.

The blue box with a small white arrow on the top left of a View-only Narrative opens the Data Panel \(so you can see the data objects in this Narrative\) and the Narratives list \(so that you can go to another Narrative\).

TIP: You can switch a Narrative that you own to view-only mode by clicking the pencil icon under the title of the Narrative.  
 If you ever want to print out a Narrative, switch it to view-only mode first, so it doesn’t waste the left side of the page with empty space.

#### Copy a Narrative

To copy a Narrative that has been shared with you, so that you can run or change it, you can use the blue “Copy This Narrative” button at the top of the Narratives panel \(or, in View-only mode, at the top right of the screen\). This will copy the Narrative that you are currently viewing \(which is marked with a green dot in the list of Narratives\). You can choose a name for the copy \(or leave the default name, which is the original name with “Copy” at the end\).

![](https://kbase.us/wp-content/uploads/2015/01/image16.png)

When you click Copy, the Narrative and its associated data objects are copied to your account, and you should see the new copy appear at the top of “My Narratives”.

**Copy of a copy warning**

 Please be aware that if you copy a copy of a Narrative, some things may not work right in the copy of a copy. We are working on resolving this problem. See [this page](https://kbase.us/copying-narratives-issues-and-workarounds/) for more information.

You can also copy any Narrative by hovering your cursor over its name in your Narratives panel to reveal the icons and clicking the Copy icon \(the one that looks like two pieces of paper\).

![](https://kbase.us/wp-content/uploads/2015/01/Screen-Shot-2015-02-10-at-10.18.49-PM.png)

The copy is now yours–you can open it, run it, edit it, or even share it with others \(if the owner of the original Narrative gave you sharing privileges\). After you’ve copied a Narrative, you can run all the steps to reproduce the computational experiment, or try changing the parameters or input data to alter or perhaps even improve the results.

Copying Narratives is the key to leveraging KBase’s commitment to reproducibility and reusability. By making it easy to build on previous work and go through rapid cycles of analysis, KBase aims to accelerate the pace of systems biology research.
{% endtab %}
{% endtabs %}






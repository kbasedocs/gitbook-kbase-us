# Analyze Data Using KBase Apps

Once exploring available [KBase Apps ](https://kbase.us/applist/)and determining which ones work with the data objects in your Narrative, you can start analyzing your data.

## Add an App to your Narrative

To add a KBase analysis app, find the app of interest and click its name or the icon to the left of the app name. A box (called a _cell_) containing the chosen app will appear in the main Narrative panel.

<div align="center">

<img src="../../.gitbook/assets/app_addtonarrative.gif" alt="">

</div>

A few things to notice about the app cell:

#### **App Cells** have three tabs&#x20;

1. Configure (where you set the parameters; it’s what you see when you add a new app cell)
2. Info
3. Job Status&#x20;
4. Result

The last two tabs are filled in once you run the app; these are discussed later.

![](../../.gitbook/assets/appcell\_tabs.png)

* The up and down arrows let you move the cell up or down in your Narrative.

![](<../../.gitbook/assets/appcell\_arrows (1).gif>)

* The App “…” dropdown menu offers several options for showing the code that will execute the app; getting more info (in a separate browser window) about the app; and deleting the cell. These are discussed more in the section called “[Revise Your Narrative](revise.md)“.

![](../../.gitbook/assets/ellipsesdropdownmenu.gif)

* The "-/+" in the App Cell menu is the collapse/expand cell option. When the App Cell is expanded, the farthest right option will be a "-" to collapse the cell. When the App Cell is collapsed, the farthest right option will be a "+" to expand the cell.  You can also double click on an App Cell to expand/collapse the app.&#x20;

![](<../../.gitbook/assets/collapsecell (1).gif>)

![](../../.gitbook/assets/appexpandcell.gif)

* Every app has some parameters (fields) that must be filled in before you can run the app.

## Fill in parameters

After you add an app to your Narrative, the required parameters must be filled in before you can run it. For most apps, you will need to select the input data object(s). Other parameters may also need to be set. A red bar to the right of a field indicates that it is a required field and you have not yet entered a valid value in it. Other indicators, such as banners for errors and warnings, may appear. Read the message and hover over any icons to reveal hints. Once you have filled or corrected the field, the indicator should disappear.

Some app fields are “smart” and know which data in your Narrative is valid for that field. These “smart” fields have a pulldown list of data objects that you can choose from. (Remember, only data (of the appropriate type) that you have already added to this particular Narrative will be shown in that list. You can access your data from other Narratives via the My Data and Shared with me tabs in the [Data Panel](add-data.md).)

Some fields are also required, but they will be pre-filled with default values. You can change their values if you chose, or leave them. Additionally, some apps have optional “advanced options” that you can reveal by clicking on the “advanced options” link at the bottom of the cell.

The green "Run" button is enabled when all required fields are filled in.

**Save Your Work**

![](<../../.gitbook/assets/savenarrative (4).gif>)

As you add to your Narrative, be sure to save your work frequently, using the Save button at the top right of the screen.

## Run the App

When you have filled in all the required fields, the _Run_ button on the left side of the app will be enabled; click it to start running the app. Once clicked, the green _Run_ button will turn to a red _Cancel_ button. When the analysis starts running, you will see information in the _Job Status_ tab_**.**_

![](../../.gitbook/assets/screen-shot-2017-03-18-at-2.23.25-pm.png)

Depending on the analysis, the analysis might finish within a few seconds or could take hours to run. You can save your Narrative and come back to it later–the analysis will continue running even if you don’t have the Narrative open.

**Examine and download results**

When an app finishes running, you will see a summary in the _Results_ tab, as well as an output cell below your app cell. Also, if the analysis generates a new data object, that object will be added to your Data Panel.

![](../../.gitbook/assets/screen-shot-2017-02-01-at-1.39.36-pm.png)

In the example, the “Annotate Microbial Contigs” app, once run, produced an output cell that provides information about the newly annotated _Shewanella_ genome object.

This output cell has three tabs: Overview (displayed above), _Browse_ Contigs, which lists the large assembled pieces of a genome, and _Browse Features_, which allows browsing of all the annotated genes.

Different apps create different types of output cells when they run, depending on which type of data object is output by the app. The genome output cell shown above is an example of a _Data Viewer._ Data Viewers are described in the [Explore Data](explore-data.md) section of this guide.

![](../../.gitbook/assets/screen-shot-2017-02-01-at-1.42.23-pm.png)

In addition to creating a new output cell, the app we ran created a new data object and added it to our Narrative. The newly annotated genome object now appears at the top of the Data Panel.

![](../../.gitbook/assets/screen-shot-2017-02-01-at-1.44.53-pm.png)

Remember that you can hover over an object in the Data Panel and click the “..." that will appear to see more information and options, including an option (see image) for downloading the object in GenBank or JSON format (see the [Download Guide](../../data/upload-download-guide/) for more information). In the future, you will be able to choose from a wider variety of common formats, allowing you to download results to use with other tools and send to colleagues.

## **Conduct further analyses**

Once you have reviewed your results, you can use your newly generated data in additional analysis steps. Remember, you can click on the data object in the Data Panel to see which KBase Apps work with that data type.

For example, our annotated genome can be used in a number of analyses because it now includes the standard KBase annotations. If you click on the genome in the Data Panel, you see several apps that apply. Among them are the [_Insert Genomes into Species Tree_ App](https://kbase.us/applist/apps/SpeciesTreeBuilder/insert\_set\_of\_genomes\_into\_species\_tree/release) that constructs a phylogenetic tree allowing you to see species closely related to your genome. You also can use the [_Build Metabolic Model_ App](https://kbase.us/applist/apps/fba\_tools/build\_metabolic\_model/release) to draft a metabolic model from the annotated genome.

## **Re-run Apps with the same or different parameters**

App input cells that have already been run have a “Reset” button that allows you to redo the analysis, with the option to change any of the parameter settings (including, perhaps, the input data) before rerunning. Rerunning an App will overwrite the information in the App cells, but will not overwrite any data objects in your Narrative _unless_ you use the same output object name again.

## **Report errors**

If a job fails, you will see an error message in the output cell and/or in the _Result_ tab. If you need help figuring out what went wrong, please [contact us](../../troubleshooting/report.md) with details about what you were doing when the error occurred and what the error message said. Including the contents of the _Job Status_ tab and the URL of your Narrative will help us debug the problem. We are here to help and appreciate your feedback and error reports!

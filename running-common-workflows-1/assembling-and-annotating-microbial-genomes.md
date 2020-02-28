# Assembling and Annotating Microbial Genomes

#### **Description of tutorial**

This tutorial describes how to use the Assemble Contigs from Reads and Annotate Microbial Contigs appsto assemble and annotate a bacterial or archaeal genome in the KBase Narrative Interface and then browse the results.

In this tutorial, we will:

* Find a set of reads to assemble using the Narrative Interface Data Browser.
* Add the reads to our Narrative.
* Find and insert the Assemble Contigs from Reads app into our Narrative.
* Use this app to assemble an example set of reads into a set of contigs \(an Assembly object\).
* Find and insert the Annotate Microbial Contigs app into our Narrative.
* Use this app to annotate our Assembly.
* Examine assembly job statistics and genome annotation.

### Narrative Tutorial

The tutorial you’re currently reading is just text and images. If you’d like to try a tutorial in the form of a Narrative that shows you the assembly and annotation apps in action, click the button below. You can copy Narrative tutorials to your account and rerun the steps or try them on your own data. You will need a free [KBase account](http://kbase.us/sign-up-for-a-kbase-account/) in order to see and use Narrative tutorials.

[Launch Assemble & Annotate Narrative Tutorial](https://narrative.kbase.us/narrative/ws.18188.obj.6)  


#### **Description of the apps**

The Assemble Contigs from Reads app assembles a set of Next-Generation Sequencing \(NGS\) short reads into contigs. The Annotate Microbial Contigs app annotates the assembled contigs, calling genes and other genomic features and assigning biological functions. The user supplies a set of FASTA or FASTQ files of short reads and chooses from one of a variety of assembly algorithms. The annotation includes assignment of biological functions derived from RAST \(Rapid Annotations using Subsystems Technology\). The resulting annotated genome can be exported in GenBank or FASTA formats.

* Step 1. [Assemble Contigs from Reads](https://narrative.kbase.us/#/narrativestore/method/assemble_contigset_from_reads) \(click the link for the App Details Page\)
  * Assemble a set of short DNA reads into a set of genome contigs
* Step 2. [Annotate Microbial Contigs](https://narrative.kbase.us/#/narrativestore/method/annotate_contigset) \(click the link for the App Details Page\)
  * Annotate bacterial or archaeal contigs using components from the RAST toolkit \(RASTtk\)

#### **Description of the input for Assemble Contigs from Reads**

The input for this app is a set of single- or paired-end reads in FASTA or FASTQ format.  In a more advanced use case, users can upload a reference assembly to determine if the current assembly is better or worse than a previous assembly. In this tutorial, we will demonstrate the app twice, once using example paired-end reads from KBase’s reference data and again using a reference assembly available from the same collection. When you are ready to assemble your own reads or load a reference assembly of your choice, see the instructions in the [Short Reads section of the Data Upload and Download Guide](../working-with-data-1/data-upload-download-guide.md#fastq-sra-reads).

You also can transfer microbial reads and assembly data from the DOE Joint Genome Institute’s website to KBase’s Narrative Interface with the push of a button. To get started, check out our [instructional guide for using the Push to KBase feature](../working-with-data-1/transferring-data-from-jgi.md).

#### **Description of the output**

Running the Assemble Contigs from Reads app will result in two output data objects in your Narrative. The first is an assembled Contig Set object representing the best assembly from a given workflow. The second object is the Assembly Report containing statistics from the assembly pipeline that was run.

#### **Understanding the default behavior and advanced options**

Assembly in KBase offers a set of workflows that have been designed to either optimize the quality of the output or mirror assembly recipes commonly used by the academic community. To understand each workflow, please refer to the [details page](https://narrative.kbase.us/#/narrativestore/method/assemble_contigset_from_reads) for the _Assemble Contigs from Reads_ app. Likewise, the annotation app provides a set of feature calling and annotation algorithms that users can modify to suit their needs. The app details page on annotating a contig set can be found [here](http://kbase.us/annotate-microbial-contigs-method/).

#### **Point and click instructions for using this app**

**Note:** This tutorial assumes that you have already created and opened a new Narrative. For instructions on how to accomplish this and other tasks such as finding or uploading data to your Narrative, please refer to the [Narrative Interface User Guide](http://kbase.us/narrative-guide/).

**Step 1. Add data that you want to analyze**

The first step in running this app is to copy or upload the needed input data. We will demonstrate the Assemble Contigs from Reads app using a set of example reads.  
To add the example data, click the Add Data \(or red  square\) button in the Data Panel on the left of your screen. \(If you don’t see this button, make sure you have the Analyze tab selected.\) The Data Browser will slide out, with tabs that show several data sources. Select the Example tab and look at the Example Sequence Assembly Inputs heading.

Find “rhodo.art.q20.int.PE.reads” and add this set of paired-end reads to your Narrative by mousing over it and clicking the Add button that appears at its left.

![Add data shot](http://kbase.us/wp-content/uploads/2016/12/Add-data-shot.png)

Exit the Data Browser by clicking either the Close button at the bottom right of the browser window or the arrow at the top of the Data Panel. \(Note that you also can close the Data Browser by clicking anywhere in the main Narrative panel in the center.\)

After a moment your Data Panel will update to show the dataset that you just added.

Don’t be concerned that there is only one data object for the paired-end reads. In KBase, the two original paired-end read files get combined into a single data object.

![one item in data panel](http://kbase.us/wp-content/uploads/2016/12/one-item-in-data-panel-.png)

You can find out more about this data object by mousing over the record in the Data Panel and clicking the “…” that appears. An expanded view of the data will open, as shown. Please see the [_Explore Data_](http://kbase.us/narrative-guide/explore-data/) section of the Narrative User Interface Guide for more information.

![explore data shot](http://kbase.us/wp-content/uploads/2016/12/explore-data-shot.png)

**Step 2. Add and run the apps**

Now that you have your input data, you can add the Assemble Contigs from Reads app to your Narrative. Take a closer look at the Apps Panel directly below your data.

You can search for apps using the search box at the top of the Apps Panel or just scroll until you find the one you want. Find the Assemble Contigs from Reads app and click on its name \(or icon\) to add it as a new cell in the main Narrative panel.

To run the app on the example dataset, you must first fill out the fields in each step in the app cell. The detailed parameters for each app are described on the app detail page: [_Assemble Contigs from Reads_](https://narrative.kbase.us/#/narrativestore/method/assemble_contigset_from_reads)_._

In the first field, Read Library, select from the dropdown menu “rhodo.art.q20.int.PE.reads” \(the example dataset you added to your Narrative\). The assembly app also lets you add additional read libraries, but we will not need this option in this case.  Note: data objects called “AssemblyInput,” while present in KBase are not valid input to the Assemble Contigs from Reads app.

The Automatic Assembly option is showing by default in the Assembly Recipe dropdown menu section. \(The assembly recipes are described in the app [details page](https://narrative.kbase.us/#/narrativestore/method/assemble_contigset_from_reads).\)

Next, choose a name for the output assembly \(Contig Set\). In this example, we will use “Rhodo\_auto\_contigs.”

![AssembleAnnotate08](http://kbase.us/wp-content/uploads/2015/02/AssembleAnnotate08.png)

**Be sure to save your Narrative frequently, using the Save button at the top right of the screen.**

![assemble, hit run](http://kbase.us/wp-content/uploads/2016/12/assemble-hit-run.png)

You’re now ready to run the app. Click the green “RUN” button on the right of the cell. The app cell will then show your job as queued, then running.  You can return to this app cell to get a status update on how your job is doing.

![assemble, running](http://kbase.us/wp-content/uploads/2016/12/assemble-running.png)

![assemble, completed](http://kbase.us/wp-content/uploads/2016/12/assemble-completed.png)

This example data is a very small set of reads, so it should run quickly \(by typical assembly standards\) and finish in about 15 to 20 minutes or perhaps longer, depending on the queue. Note that most assembly jobs will be slower because they will contain more reads. Some assembly jobs can take days or even weeks depending on the genome size and repeat structure. You can check your job status by referring back to the app cell, where time running, and status will be displayed.

Following assembly by this app, an Assembly with the file name that you entered, “Rhodo\_auto\_contigs,” will be created and added to your data panel.

An Output cell summarizing the outcome of the assembly process has also been added to your Narrative. Make sure to click on that cell before you add the next app to your Narrative so they appear in the correct order.

The next step is annotation.  Search for [_Annotate Microbial Contigs_](http://kbase.us/annotate-microbial-contigs-method/) in the Apps Panel, and click on its name or icon to add it to a new cell in the main Narrative panel. Use the drop-down list to populate your Assembly name into the app–in this case “Rhodo\_auto\_contigs.”

Next, specify the Scientific Name of the organism you are working on. This field has no restrictions, but we strongly suggest that you enter a meaningful genus, species, and strain name when possible because the name can affect which programs are run. We will use “Rhodobacter sp.” in this example.

Since Rhodobacter is a bacterium, we will leave the _Domain_ field set to B \(Bacteria\).  Note that this app should be used to annotate only bacterial and archaeal genomes. For plant genomes, use the app called [Annotate Plant Coding Sequences with Metabolic Functions](http://kbase.us/annotate-plant-transcripts-with-metabolic-functions-method/) app. More apps to support annotation of eukaryotic and viral genomes are coming soon.

Next, you need to specify a numeric value representing the genetic code. The default is 11, which is the appropriate value for all but a handful of bacterial genomes \(e.g., for Mycoplasmas, use code 4\). The genetic code is a required field because the gene calling algorithms need to be able to find the appropriate stop codons. If you have any questions as to what value to use, we suggest visiting the[ NCBI Taxonomy Browser](http://www.ncbi.nlm.nih.gov/Taxonomy/Browser/wwwtax.cgi).

Finally, for this example, enter “Rhodo\_auto\_anno” to specify the name that will be given to the output annotated genome object.

Notice that as you fill in the required parameter fields, the red arrows next to those fields disappear.

![annotate\_ready to run](http://kbase.us/wp-content/uploads/2016/12/annotate_ready-to-run.png)

Once all red arrows are gone, the app is ready to run.

Click the green arrow at the top right of the app cell to run the annotation app. When the annotation job begins, a message at the top of the app cell will indicate that the job was queued, then running.

The annotation step should be faster than the assembly; it typically takes just a few minutes.

**Step 3. Look at the output**

When the annotation job is complete, return to your Data Panel and make sure you are on the Analyze tab. Notice that two new objects have appeared in your panel: the Genome \(Rhodo\_auto\_anno\), and the Annotation Report \(Rhodo\_auto\_anno.report\).

![output objects in data panel](http://kbase.us/wp-content/uploads/2016/12/output-objects-in-data-panel.png)

In the main Narrative panel, look at the output cells under the two app steps. The output of the assembly app is a table describing the statistics from the assembly job. The Automatic _Assembly_ option that we chose actually performed an assembly using three different programs: Velvet, SPAdes, and IDBA. There are three columns in the output corresponding to the results from each.

The output contains important data for choosing the best alignment, such as the total number of contigs, number of genes, and the N50 values of the contigs.  The comparatively “best” run would have the fewest number of contigs, the highest N50 value, and the largest number of genes.  However, one should proceed with caution and consider whether the assembly also has the highest number of ambiguous positions \(685 N characters/100kb\).

Note that the _Automatic_ _Assembly_ option runs a workflow that infers the “best” assembly by using post-analysis metrics called an “AR score.”  The output is sorted by this score, with the best alignment appearing first in the table . Currently, only the contig set generated by the best assembly is made available in the Data Panel.

![assembly output window](http://kbase.us/wp-content/uploads/2016/12/assembly-output-window.png)

The output of the second step is the genome annotation. This output contains data about the genome as well as a list of contigs and the genes that were called on each contig. The data presented currently is based on the assembly with the highest N50 value; however, we are in the process of implementing better algorithms for making this choice. Notice that this output table has three tabs for reviewing the data: Overview, Browse Features, and Browse Contigs. You can sort table entries under these tabs by clicking on a column header to sort by that field \(e.g., Length\). Clicking the same column header again will reverse the sort order. You can even sort by more than one column simultaneously by clicking one column header and then Shift-clicking on others. To see more details about an entry under the Contigs and Genes tabs, click on the entry to open an expanded view of it:

![](http://kbase.us/wp-content/uploads/2015/02/ViewContig2.png)

**Step 4. Download the results**

To download your annotated genome or Assembly, locate the data in your Data Panel. Open an expanded view of the object by clicking on the “. . .” or white space surrounding the object name \(but not on the name itself\).

![AssembleAnnotate16](http://kbase.us/wp-content/uploads/2015/02/AssembleAnnotate16-e1424366562914.png)

Use the Export/Download data icon to download the data in a format of your choice. For genomes, the options are GenBank or JSON formats; for Assemblies \(Contig Sets\), they are FASTA or JSON. \(Be aware that the assembly report can only be downloaded in JSON format at this time because the download functionality is still in development.\)

![AssembleAnnotate17](http://kbase.us/wp-content/uploads/2015/02/AssembleAnnotate17.png)

### **Further analysis / next steps**

The annotated genome object generated by this app is the starting input object for many other KBase analyses. For example, now that you have a genome with KBase annotations, you may be interested in proceeding to metabolic modeling. If so, we recommend reading the tutorial for the [Reconstruct Genome-scale Metabolic Model](http://kbase.us/reconstruct-genome-scale-metabolic-model-app/) app. If you would like to use your genome to begin evolutionary studies, check out tutorials on the apps for [Insert Genome into Species Tree](http://kbase.us/insert-genomes-into-species-tree-app/) and [Compare Genomes from Pangenome](http://kbase.us/compare-genomes-from-pangenome-app/).


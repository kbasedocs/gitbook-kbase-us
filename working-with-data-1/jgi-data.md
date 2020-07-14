---
description: >-
  DOE’s Joint Genome Institute (JGI) users can transfer genome reads,
  assemblies, and annotated genomes to KBase’s Narrative Interface for assembly,
  annotation, metabolic modeling, and more.
---

# Transferring Data from JGI

### **Before transferring data from JGI to KBase, you must:**

* [Get a JGI account](http://contacts.jgi-psf.org/registration/new)
* [Get a Globus account](https://www.globusid.org/create)
* [Get a KBase account](http://kbase.us/sign-up-for-a-kbase-account/) and link it to Globus \(see the section “Create or modify user profile” [here](../getting-started/narrative-user-guide/share-narratives.md) for help\)
* [Use either Chrome, Firefox, or Safari browser](../getting-started/supported-browsers.md)

The Search tool on the KBase Dashboard is a quick and easy way to copy public genome reads and assemblies from JGI to your [KBase Staging Area](../getting-started/narrative-user-guide/add-data-to-your-narrative.md) \(this page describes the process for transferring those and also private data and annotated genomes\).

![](../.gitbook/assets/search_dashboardmenu%20%281%29.png)

JGI’s Globus service lets users select data from the JGI Genome Portal’s sequencing projects and make them transferable to KBase, all in a few simple steps. There are some similarities to the KBase-initiated [Globus service](globus.md), but also some differences.

### Transferring Data from JGI to KBase

Starting at the [JGI Genome Portal](https://genome.jgi.doe.gov/portal/), search for the genome or project of interest and click on the download link. Click on the green "Agree" button on the next page to accept the data usage policy.

![](http://kbase.us/wp-content/uploads/2015/02/image1.png)

![](http://kbase.us/wp-content/uploads/2019/07/JGI-Globus.png)

Near the top of the download page is a link to JGI’s Globus v.2 service. This version works by 1\) transferring the entire project to a JGI/Globus staging area and 2\) sending you an email when it is ready.

Click on the blue "Download" button and one of two windows will pop up:  
1. A window to enter a Globus ID or register for a Globus ID

![](http://kbase.us/wp-content/uploads/2019/07/globusv2.png)

**OR**

2. Or a window saying “There is not enough disk space in the staging area for this data.”

If you do get the message about disk space, this is an issue between JGI and Globus \(it has nothing to do with KBase\), and it is dependent on other users staging data for transfer. The issue should eventually resolve itself if you try again later.

Once you successfully enter your Globus account name and hit the blue "Submit" button, your data will be transferred to the JGI staging area. A successful transfer request will look like this:

![](http://kbase.us/wp-content/uploads/2019/07/globus3.png)

You will receive an email from no-reply@genome.jgi.doe.gov with a link for transferring data with Globus. The email also states that **JGI only keeps this link active for 14 days**. After that time, they will remove the data from their staging area to make room for other users.

Clicking on the link in the email will take you to a Globus file transfer window:

![](http://kbase.us/wp-content/uploads/2019/07/globus4.png)

Double click on the directories until you get o the file you want. Click on the file name to highlight it and then click on the "Transfer or Sync to..." link on the right.

 [![](http://kbase.us/wp-content/uploads/2019/07/globus-5.png)](http://kbase.us/wp-content/uploads/2019/07/globus-5.png) 

The newly created JGI endpoint is filled in on the left.

Set the “To” endpoint \(right\) to “KBase Bulk Share”, which is the KBase Staging Area. If you do not see a directory with your name, add /username \(i.e. /landml for the user below\) to the Path for the KBase endpoint.

![](http://kbase.us/wp-content/uploads/2019/07/globus-6.png)

You should then be able to drag data files or folders from the left endpoint to the right one, inside the Globus interface, and the files will be copied to your KBase Staging Area.

If the connection to the server is broken during transfer, Globus will start up again where it left off once the connection is reestablished. The link in the JGI email may be used to reestablish the connection.

While it may be possible to drag ALL the project data from the JGI endpoint to the KBase endpoint, not all files can be imported into KBase. Reads files \(.fastq or .fastq.gz\), assemblies \(.fna or .fasta\), and annotated genomes \(.gbk or .gff\) have a corresponding KBase object.

You can import data from your **Data Browser** Staging Area to any of your KBase Narratives \(see [this page](../getting-started/narrative-user-guide/add-data-to-your-narrative.md) for more information\). The imported objects are permanent in your KBase account, but the files in the Staging Area will be removed after 90 days.

Important differences between JGI and KBase data staging:  
1. The JGI staging area keeps file links for 14 days. The KBase staging area keeps files for 90 days.  
2. The JGI staging area has a limited amount of space that is shared with other users. The KBase staging area has 2.8 terabytes available to the user.  
3. The JGI notifies users by email when files have been added to the staging area. The KBase _Import_ tab shows files in your Staging Area and has an update button to refresh the list.  
4. JGI stages an entire project at one time. KBase stages specific files selected by the user.  



---
description: >-
  The Job Log contains run information from apps and other jobs, including
  important error information.
---

# The Job Log

The Job Log can be found in two places: an app's _Job Status_ tab and the **Job Browser** \(in the Dashboard Menu\).

### **Job Status tab**

The Job Log starts at the bottom with the error highlighted in pink. ****There may be useful information located just above the pink section. 

![](http://kbase.us/wp-content/uploads/2014/10/AppErrorStatus-1.png)

### **Job Browser**

Find the line with the job of interest and click on the icon for the piece of paper. This will open up the log, starting at the top. 

![](../.gitbook/assets/jobsfeed_dashboardmenu.png)

In the Job Browser, jobs not associated to an app i.e., export, are included within the job list. The Job ID and worker node are easily located and the log can be scrolled through within the pop-out. Job Logs can be downloaded in CSV, TSV, JSON, and TEXT formats using the download \(downward-facing arrow into tray\) icon. 

![](../.gitbook/assets/joblog_jobbrowser.gif)

{% hint style="info" %}
Even if you find an explanation for your error on this page, it is okay to [submit a Help Board ticket](support.md) with follow-up questions.
{% endhint %}

### Helpful Points

* If the output object is created but the job ends in an error, assume that the error didn’t affect the data. Errors sometimes occur in the cleanup and reporting at the end while not affecting the output data.
* Jobs _do not run more than 7 days_. If the narrative and/or the Job Browser say that a job is still running after 7 days, assume that it is dead. Resubmitting may solve the problem, but it is possible the job might be too big for KBase. 
* Assemblers currently have an upper limit of between 180,263,840 paired reads and 240,351,788 reads depending on complexity. If the job has been run twice, exceeded the 7 day limit, and your data is in this size range, it may be too big for KBase at this time.
* Bowtie appears to have an upper limit between 3.5E+10 and 4.0E+10 bases due to space limitations.
* If asked for a job ID, it is a 24-digit hexadecimal number that looks similar to this: 5e1e3234e4b0fb2e6517240a. It is in the first line of the job log.
* If asked for the node where the job ran, it is on the first line of the job log and looks similar to `Running on chicagoawe163` or `Running on uploadworker` or `Running on uploadworker-prod-dtn2`
* Any file uploaded from a Windows machine might have  DOS-style carriage-return line files along with new-lines. This has been known to cause problems with importing FASTQ files  and may affect other files as well.


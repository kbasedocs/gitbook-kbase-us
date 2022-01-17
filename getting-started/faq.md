---
description: Frequently Asked Questions about KBase.
---

# FAQs

## Is KBase free to use?&#x20;

Yes! KBase is completely free to use and is supported by the Department of Energy.

## I'm getting an error. What do I do?

You can check [the job log](../troubleshooting/job-errors/common/job-log.md) and refer to our [troubleshooting guide](../troubleshooting/). If you do not see a reason for the error there, please make a ticket on our [Help Board](https://kbase-jira.atlassian.net).

## Is it possible to obtain publication-quality figures by using these tools?

Some of the Apps can produce publication-quality images that can be views by opening in a separate window. We hope to add more in the future.

## I have too much data to move.&#x20;

Is there a better way for handling large datasets? For large files or collections of files, we recommend using Globus. We also have a [guide for importing using Globus](../data/globus.md).

## Can I import more than one file into a Narrative at the same time?

Yes, bulk import allows you to check multiple files in the staging area and import them all by clicking "Import Selected." More instructions on this feature are [described in the Narrative Guide](narrative/add-data.md#using-bulk-import).&#x20;

## How many users can view a Narrative?&#x20;

There is no limit to the number of users that can be invited to view or edit Narratives. However, it is possible for users who are accessing the Narrative simultaneously to overwrite each other's changes. For that reason, we recommend only one person edit the Narrative at a time.

## I work with datasets with many samples, outputs from each step often mixed together and often hard for me to select the ones for the next step. How do I keep them organized?&#x20;

The best way to organize many inputs is to create sets. There are Apps for building these sets, such as [Build AssemblySet](https://narrative.kbase.us/#catalog/apps/kb\_SetUtilities/KButil\_Build\_AssemblySet/release) that allow you to group those outputs.

## What languages are supported in code cells?

Currently we only support code cells in Python.

## How does KBase compare with the standalone tools available with command line interface? Does KBase always use the most recent version?

Provided the same data, parameters, and tool version are consistent, the results are the same. We make every attempt to use the latest versions of Apps and databases, but they do not always correspond to the most recent version.

## How do I access advanced parameters?&#x20;

You can view some advanced parameters depending on the app by clicking the Advanced Parameters button. For some apps there are few or no advanced parameters. In creating these Apps we aim to balance configurability and usability. As a result, for some Apps we do not make certain rarely changed parameters visible.

## How do I get a tool I like added?&#x20;

There are a couple venues:&#x20;

1\. Submit a Help Desk New Feature Request. We can't promise if or when new feature requests are added, but user input helps us plan our future development.&#x20;

2\. Add as a 3rd-party developer: If you are a developer of an app, you can find more information on [the developer's page](../development/) and you can read the documentation for our [Software Development Kit](https://kbase.github.io/kb\_sdk\_docs/) . If you are not the developer, you can reach out to the developer and ask them about wrapping it for KBase.&#x20;

Alternatively, a beta version of the App might already be in KBase. In the Apps panel, click on the "R" button to switch from release to beta. When a "B" appears in place of the "R", you are viewing beta Apps.

## What pipelines does KBase provide?&#x20;

&#x20;KBase does not provide _pipelines_ per se; we try to be as flexible as possible. We do have [example Narratives](../workflows/) that replicate the paths many users follow, but we encourage everyone to plot their own course.

## Will my data be made public?

All user data in KBase is [private by default until you share it](https://www.kbase.us/data-policy-and-sources/). You can keep all your data private if you wish. We do encourage users to make data public in the interest of FAIR - Findable, Accessible, Interoperable, and Reusable - data practices.

## What organisms are available in KBase?&#x20;

In KBase as a whole, anything can be uploaded, the only exception being that human data is not permitted. There are connections to some bacterial, plant, and fungal species in the Public Data tab, but any user data or data found from public sources other than those integrated into KBase can be uploaded. On an app-by-app basis, some tools may work sub-optimally or not at all with certain species.

## Is there an API to allow access to the methods from the command line?&#x20;

Command line is not supported for the narratives. However, you may find more flexibility with the KBase Software Development Kit (SDK).

## Can I get an in-person KBase workshop at my institution?&#x20;

If you would like an in-person workshop, contact us by email at [engage@kbase.us](mailto:engage@kbase.us).

## Can I see the background code for KBase?&#x20;

Yes, the relevant Github repo for each App can be found by following the links in the App Catalog. You can access the version and parameters that were used during an App run by clicking on the ellipsis button and clicking "Show code."

## **What is the difference between Public and Private organizations?**

* The existence and contents of Private organizations are only visible to members of the organization. The organization will not be findable by non-members.
* Any KBase user can see a list of all Public organizations plus a description of the organization. Non-members are given the option to request membership. Members of the organization can access more information than non-members.

## **Why can't I open a Narrative in an Org?**

Click on ‘Click for Access’ and you are automatically granted View access to the Narrative. You can then click on the linked Narrative to open.&#x20;

## What if I lose access to my account?&#x20;

You can log into KBase through Google, Globus, and ORCiD. It is recommended to always have at least one personal account linked to your KBase account, so that in the event you lose access to an identity supplier i.e., Google, Globus, or ORCiD because of an email provider change, then you will still have another method to login.&#x20;

If you do lose access completely, please submit a ticket through the [Help Board](../troubleshooting/support.md#contact-us).&#x20;

\

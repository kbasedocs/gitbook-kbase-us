---
description: Frequently asked questions about KBase.
---

# FAQ

## Is KBase free to use? 

Yes! KBase is completely free to use and is supported by the Department of Energy.

## I'm getting an error. What do I do?

You can check the job log and refer to the troubleshooting page \([http://kbase.us/troubleshooting/](http://kbase.us/troubleshooting/)\). If you do not see a reason for the error there, please make a ticket on our Help Board.

## Is it possible to obtain publication-quality figures by using these tools?

Some of the Apps can produce publication-quality images that can be views by opening in a separate window. We hope to add more in the future.

## I have too much data to move. 

Is there a better way for handling large datasets? For large files or collections of files, we recommend using Globus. You can find a guide to using Globus [here](https://kbase-us.gitbook.io/kbase-documentation-1/working-with-data-1/transferring-data-with-globus).

## How many users can view a narrative? 

There is no limit to the number of users that can be invited to view or edit Narratives. However, it is possible for users who are accessing the Narrative simultaneously to overwrite each other's changes. For that reason, we recommend only one person edit the Narrative at a time.

## I work with datasets with many samples, outputs from each step often mixed together and often hard for me to select the ones for the next step. How do I keep them organized? 

The best way to organize many inputs is to create sets. There are Apps for building these sets, such as [Build AssemblySet](https://narrative.kbase.us/#catalog/apps/kb_SetUtilities/KButil_Build_AssemblySet/release) that allow you to group those outputs.

## What languages are supported in code cells?

Currently we only support code cells in Python.

## How does Kbase compare with the standalone tools available with command line interface? Does KBase always use the most recent version?

Provided the same data, parameters, and tool version are consistent, the results are the same. We make every attempt to use the latest versions of Apps and databases, but they do not always correspond to the most recent version.

## How do I access advanced parameters? 

You can view some advanced parameters depending on the app by clicking the Advanced Parameters button. For some apps there are few or no advanced parameters. In creating these Apps we aim to balance configurability and usability. As a result, for some Apps we do not make certain rarely changed parameters visible.

## How do I get an app I like added? 

There are a couple venues: 

1. Submit a Help Desk New Feature Request. We can't promise if or when new feature requests are added, but user input helps us plan our future development. 

2. Add as a 3rd-party developer: If you are a developer of an app, you can find more information at our developer"s page \([http://kbase.us/developer](http://kbase.us/developer)\) and you can read the documentation for our Software Development Kit at \([https://kbase.github.io/kb\_sdk\_docs/](https://kbase.github.io/kb_sdk_docs/)\). If you are not the developer, you can reach out to the developer and ask them about wrapping it for KBase. Alternatively, a beta version of the App might already be in KBase. In the Apps panel, click on the "R" button to switch from release to beta. When a "B" appears in place of the "R", you are viewing beta Apps.

## What pipelines does KBase provide? 

 KBase does not provide _pipelines_ per se; we try to be as flexible as possible. We do have example Narratives that replicate the paths many users follow, but we encourage everyone to plot their own course.

## Will my data be made public?

All user data in KBase is private by default until you share it. You can keep all your data private if you wish. We do encourage users to make data public in the interest of FAIR \(Findable, Accessible, Interoperable, and Reusable\) data practices.

## What organisms are available in KBase? 

In KBase as a whole, anything can be uploaded, the only exception being that human data is not permitted. There are connections to some bacterial, plant, and fungal species in the Public Data tab, but any user data or data found from public sources other than those integrated into KBase can be uploaded. On an app-by-app basis, some tools may work sub-optimally or not at all with certain species.

## Is there an API to allow access to the methods from the command line? 

Command line is not supported for the narratives. However, you may find more flexibility with the SDK.

## Can I get an in-person KBase workshop at my institution? 

If you would like an in-person workshop, contact us by email \([engage@kbase.us](mailto:engage@kbase.us)\) and we will explore the possibilities.

## Can I see the background code for KBase? 

Yes, the relevant Github repo for each App can be found by following the links in the App Catalog. You can access the version and parameters that were used during an App run by clicking on the ellipsis button and clicking "Show code."




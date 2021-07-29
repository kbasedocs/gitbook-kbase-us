---
description: >-
  Interested in developing an App for KBase? Here you can find information for
  developers.
---

# Developing Apps

## **The Principles**

### **Reproducibility**

KBase is a scientific platform. A cornerstone of science is that scientific experiments and analyses are reproducible - that is a scientist must be able to take a description of an experiment and/or analysis, perform said experiment / analysis independently, and get the same results. Science that is not reproducible is not science, and knowledge that cannot be verified independently is not knowledge.

### **Provenance**

Provenance in the context of KBase explains how data comes to exist - the sequence of operations that transformed a set of units of data into a different set of units of data along with who caused those transformations to occur and when. Information on job performance and the error log should be considered part of the data produced. Accurate provenance enables many of the other KBase principles, including reproducibility and Credit where credit is due. Data without provenance is not useful, as there is no way to determine how the data was created and therefore assess the data’s reliability.

### **Sharing and data privacy**

Users loading data into and creating data within KBase are guaranteed that their data and activities are private unless they explicitly share their data or make it public. KBase will not mine, collate, or otherwise use their private data or activities/jobs \(other than for internal tasks required to administer the platform\), and their data/activities/jobs will not be visible in any data view to users that are not granted access.

When data or analyses are shared, they are expected to be viewable and runnable by the users they are shared with. If a user makes a copy of data or analyses, those data and analyses are expected to be viewable and runnable just as the sources are viewable and runnable. Information about the original generators of the data are expected to propagated along with the data to ensure proper credit. 

### **Credit where credit is due**

Users that add data, apps, or analyses to the system and make them available for other users to rerun, reuse, or copy and modify must receive credit for their work.

### **Support of cross-references**

Data in KBase should reference appropriate and relevant related data e.g., a Genome object referencing the Taxon object to which it belongs. Data should be richly connected to other data types when feasible. Additionally, data imported into the system should reference the data source.

### **FAIR data management**

[**Findable, Accessible, Interoperable, Reusable**](https://www.nature.com/articles/sdata201618) ****data meets the criteria set out in the linked paper. FAIR overlaps with many of the other principles set out here but is an emerging standard for data management. Further, we wish to ensure data of the same type are comparable i.e., data are in comparable units derived from similar “workflows” so for example, numbers from two different data sets can be fairly combined. 

### **Open source software and data**

KBase software is publicly available through [GitHub](https://github.com/kbase). You may reuse KBase code under the terms of our [open source license](https://github.com/kbase/sdkbase2/blob/master/LICENSE.md). All software and data used in KBase must be open source and restriction free. This, along with reproducibility and provenance allows users to examine and understand each step in analyses workflows.

### **Extensible by 3rd parties**

3rd parties can extend the functionality of KBase by contributing application modules that run in the KBase execution environment. These modules are expected to also follow the principles outlined here.

### [Develop and release your own App](https://www.kbase.us/develop/)

If you want to develop Apps using the SDK, please apply for a KBase developer account by going to the Requesting a [New KBase Developer Account](https://accounts.kbase.us/index.php?tpl=request_identity.tpl). If you are a US citizen, your account can be created within a few days. For foreign nationals, it may take several weeks \(and, in a few cases, you may not be able to get a developer account\). Non-US citizens will be asked for additional information in order to process their application.Once your account is approved, [contact us](https://www.kbase.us/support/) with your username and ask to be added to the developer list.

### KBase System Architecture

KBase is based loosely on a service-oriented architecture that bundles related functionality into a set of independently scalable services that are managed to provide responsive interaction via the Narrative Interface.

For more details, please see the KBase [architecture overview](https://github.com/kbase/KBaseDeveloperBootstrap/blob/master/README.md), which ****outlines the components and relationships between KBase’s user interfaces, services and databases.


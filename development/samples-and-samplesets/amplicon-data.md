---
description: Analyzing amplicons in KBase
---

# Amplicon Data

## Uploading Amplicons to KBase

### Step 0: Generating Amplicon Matrix

There are many outside approaches to creating amplicon matrices, including QIIME and mothur. These should be usable in KBase, but may require additional curation. When uploading, ensure that rows are taxa and columns are samples. A column for taxonomy is optional.

The consensus sequences must also be included as a .fa file. Sequence names must match exactly with the taxa names in the amplicon matrix. 

### Upload

Amplicon matrices can be imported using the "Import Amplicon Matrix from TSV/FASTA File in Staging Area" app. This app has numerous parameters, many of which are optional. We recommend uploading raw counts as analysis will be tracked and provenance maintained on system. Rarefaction, standardization, and normalization will be described in the Analysis section. 

First, the amplicon can be applied to an existing SampleSet and AttributeMapping on-system. This is not required, but facilitates the interoperability of objects in KBase. 

The two primary inputs are the amplicon matrix in the "Taxonomic Abundance TSV File Path" and the sequence file in the "FASTA File Path" field. Other required fields that required user input are forward and reverse primer sequences, quality filtering and clustering cutoffs, and finally output object name. Additionally, the Target Gene/Region, sequencing platform, and clustering method default to full length, Illumina, and reference, respectively, but should be changed if the default values do not apply to your data.

Additional parameters are available and optional, but not required. These parameters include a description of the amplicon data, the extraction kit used, the sequencing run, and the sequencing kit used. While these parameters are not required, it is recommended you fill them out to enhance workflow documentation and reproducibility. 

Once your amplicon matrix is uploaded, you can use the "View Matrix as Table" app for viewing your new object. 

## Analysis

### Data Cleaning

As mentioned above, rarefaction and standardization can be performed in KBase to track data provenance. There are two main apps that can be used in any order and/or repeatedly if, for instance, you want to remove singletons, then rarefy samples, then calculate relative abundance of rarefied samples. 

The "Transform Matrix" app takes an AmpliconMatrix object as input. It allows abundance filtering, which can remove rows or columns if all values fall below a user-specified threshold and/or if the sum of all values falls below a user-specified threshold. It can also perform standardization, with options for centering the data before scaling, scaling the data to unit variance, and whether to perform the standardization on columns or rows. Finally, the app can perform ratio transformation, by either Centre or Isometric Log Ratio Transformation methods, and can likewise be applied to columns or rows. 

The "Rarefy Matrix" app can be performed on columns or rows, and allows manual selection of a seed value to aid reproducibility.

The "View Matrix as Table" app can again be used to view the matrix.

### Taxonomic Classification

If taxonomies were not included in the original amplicon matrix upload, they can be assigned using the "RDP Classifier" app. This app can assign taxonomy based on several gene databases including RDP Classifier 2.13 - 16srrna, RDP Classifier - fungallsu, and SILVA 138 - SSU, Full Length. Silva databases are currently under development. 

Once taxonomy is assigned, the AmpliconMatrix can be used in the "Taxonomy Abundance Barplot" app to visualize the taxonomic abundance. 

### Functional Prediction

There are currently two apps to predict function from AmpliconMatrix objects - "Map Tax to Functions using FAPROTAX - v1.2.1" and "Predict prokaryote EC, KO, & MetaCyc function abundances with PICRUSt2 v2.3.0\_B."

The FAPROTAX app allows you to identify functions and then assign them to a new AmpliconMatrix. FAPROTAX is a manually curated database  with particular focus on marine and lake biochemistry, such as sulfur, nitrogen, hydrogen, and carbon cycling. For more details, please refer to the main FAPROTAX website at [http://www.loucalab.com/archive/FAPROTAX/](http://www.loucalab.com/archive/FAPROTAX/). 

PICRUSt fucntions similarly to FAPROTAX, but with some differences. It allows you to identify functions from many different ontologies, including COG, EC, and KO, any combination of which can be chose with the relevant checkboxes in the parameters. It can create new FunctionalProfile objects for the SampleSet, AmpliconMatrix, or both, and outputs a new AmpliconMatrix Object. More information about PICRUSt2 can be found in the original publication: [https://www.biorxiv.org/content/10.1101/672295v1.full.pdf](https://www.biorxiv.org/content/10.1101/672295v1.full.pdf)

### Statistical Analysis

Further statistical analysis of the AmpliconMatrix objects can be performed with a variety of apps. These apps include "Perform NMDS Analysis," "Perform Categorical Variable Statistics Analysis," "Perform Similarity Percentage \(SIMPER\) Statistics Analysis," and more. Most relevant apps can be found in the Utilities section of the apps panel and filtered by searching for "GenericsAPI."


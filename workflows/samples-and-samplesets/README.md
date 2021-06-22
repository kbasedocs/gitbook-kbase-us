# Samples in KBase

SampleSets are still a work in progress, and much of the documentation here is not currently applicable in production. Watch your inbox for notifications from KBase Outreach when these workflows go live. 

If you are interested in beta testing these Apps, please contact us at engage@kbase.us.

## Overview

In KBase, a Sample is an entity that represents some measure material from an experiment. It has a unique ID internal to KBase, aliases, related samples, and structured metadata. Samples only occur within a Narrative as a SampleSet, but the same Sample may be shared by multiple SampleSets. 

One key feature of KBase if the ability to link the same data across many users and analyses. To do this, sample aliases allow the same data uploaded by multiple people to be linked and connect different analyses of the same data. These aliases can also be used to link Samples in KBase with other methods of sample registration, such as ESS-DIVE or SESAR. 

Because the metadata about a sample is critically important for, KBase provides the option to upload metadata spreadsheets to link to Samples. This allows for more detailed analysis across Samples, as shown below.

### Uploading samples, amplicons, and chemical abundances

#### Samples and SampleSets

When uploading Samples, the new Samples can either be added to an existing SampleSet or used to create a new SampleSet. To add to an existing set, choose the appropriate SampleSet from the drop-down in the importer. To create a new set, simply leave it blank and a new SampleSet will be created from the new Samples being uploaded.

_Direct Import from IGSN_

Samples can be directly imported from IGSN using the app "Import Samples from IGSN." This app can imports public SESAR samples with the IGSN number. Samples can be found through the IGSN catalog search at [https://www.geosamples.org/catalogsearch](https://www.geosamples.org/catalogsearch). Samples imported using this method can be added to an existing SampleSet by selecting it from the SampleSet drop-down or can be used to create a new SampleSet. The additional parameters are the same as those for importing Samples manually, as described below.

_Upload from local_

As with all data in KBase, Samples data must be uploaded to the staging area and then imported into a Narrative. When importing new Samples, the default action is to create a new SampleSet. Every Sample must belong to a SampleSet, even if that SampleSet contains only one Sample. Currently, all samples must be formatted to fit SESAR or Enigma formats. See the section for Samples Formats to view or download templates for those types. If your data does not correspond to those standards, you may still upload it, but your analysis will be limited as those standards are required to validate most of the data. Any non-validated data can be uploaded as user terms, but these do not allow comparisons across samples. We recommend you to change the column headers to correspond with the relevant SESAR or Enigma headers, and ensure the data matches, for instance, ensuring the values and units of an elevation are in separate columns in a SESAR template.

_Data Validation_

SampleSets that are uploaded to KBase are validated to ensure the data is formatted appropriately. Critical errors, such as unrecognized units for a measurement, will prevent upload entirely. Minor errors, such as an unrecognized controlled vocabulary term, can be ignored by selecting the "Ignore Warnings" checkbox in the importer. 



#### Amplicon Matrices

When analyzing amplicon data, the consensus sequence for each OTU must be included for some steps of analysis. This data should be added as a separate FASTA file where each sequence ID exactly matches the OTU ID in the amplicon matrix. 

{% file src="../../.gitbook/assets/amplicon\_example.zip" caption="Example of test amplicon matrix with consensus FASTA" %}

#### Metabolomics Data

Like other data in the Samples workflows, chemical abundance data must be formatted to ensure samples are correctly linked. To this end, the [Create Chemical Abundance Matrix Template](https://ci.kbase.us/#appcatalog/app/GenericsAPI/build_chemical_abundance_template/dev) creates an Excel spreadsheet for direct download that can be populated with chemical abundance data.

### Viewing samples, amplicons, and chemical abundances

#### Viewing in the Narrative

Once imported, the SampleSet viewer widget allows you to see the samples data that has been imported. This includes all the metadata such as collection information that was uploaded, and can be selectively viewed using the search bar. 

#### Viewing the Landing Page

More details for the SampleSets can be found on the landing page. Click on the SampleSet name in the viewer widget or the binoculars button in the data pane to view the landing page. This lists 

### Running workflows

#### SampleSets

Samples can be used as a basis to generate OTU sheet or chemical abundance templates that can be used for amplicon or chemical abundance analysis, respectively, in KBase. This allows the amplicon and chemical abundance analysis to remain linked to the sample metadata and enrich analysis. 

SampleSets currently must be uploaded in SESAR or ENIGMA formats, but more formats may become available in the future. For more information on the SESAR format, please see [their website.](https://www.geosamples.org/)

To preserve SampleSet content, the default setting is for the SampleSets to only be modifiable by the original uploader. The Update SampleSet Access Controls App allows other users to be added, after which they can add Samples to the set using the Import Samples App.

#### Amplicons

As previously stated, amplicons must include consensus sequences and an amplicon matrix. There are a number of options for generating these matrices, such as QIIME and mothur. We recommend uploading the raw count matrices rather than rarefied or nomalized. KBase can perform these steps on-system, and doing so maintains data provenance for enhanced reproducibility. The Transform Matrix and Rarefy Matrix Apps allow you to perform these steps while maintaining the original matrices as a KBase object and creating a provenance graph to show how the data was transformed. 

Taxonomies can be assigned using the RDP Classifier App based on the consensus sequences that are supplied. Then, function can be assigned with either [FAPROTAX](https://pages.uoregon.edu/slouca/LoucaLab/archive/FAPROTAX/lib/php/index.php?section=Instructions) or [PICRUSt2](https://www.biorxiv.org/content/10.1101/672295v1.full.pdf). From there, additional statistical comparisons can be calculated, such as clustering \(hierarchical or k-means\), PCA analysis, and more. For a full catalog of Apps, see the utilities section of the App Catalog or filter Apps by input within the Narrative. 

#### Metabolomics

Once metabolomics data are uploaded, they can be can be mapped using Escher. Additional statistical analysis of the chemical abundance attribute maps, such as PCA and clustering, can be performed. Apps can be filtered as with the amplicon analysis above. 

PickAxe can be used if you have a metabolic model in the Narrative. PickAxe applies SMARTS reaction rules  to generated novel compounds. The result is a directed graph that branches from a small number of source compounds to a large number of daughter compounds


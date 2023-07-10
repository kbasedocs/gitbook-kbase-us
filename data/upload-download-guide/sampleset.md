---
description: >-
  A guide to importing and formatting sampling data and metadata to comply with
  standard templates.
---

# SampleSet

{% hint style="info" %}
SampleSets are still a work in progress, and much of the documentation here is not currently applicable in production. Watch your inbox for notifications from KBase Outreach when these workflows go live.&#x20;

If you are interested in beta testing these Apps, please contact us at engage@kbase.us.
{% endhint %}

A Sample in KBase represents physical material from an experiment with attributes or metadata (environment, location, temperature, etc). It has a unique ID internal to KBase, aliases, related Samples, and structured metadata. Samples occur within the Narrative as a SampleSet, and multiple SampleSets may share the same Sample.&#x20;

## Formatting SampleSets

### IGSN SESAR

The [SESAR](https://www.geosamples.org/) (System for Earth SAmple Registration) format is one format that can be used in KBase for uploading Samples. Their samples use a [controlled vocabulary for fields of data and metadata](https://www.geosamples.org/vocabularies) that can be used in KBase.

Download a template of the SESAR format below and fill in your own data, or generate a new dataset file [based on their documentation](https://www.geosamples.org/resources/help). The .xlsx file has pre-filled options for the columns with [controlled vocabulary](../samples/ontology.md), whereas the CSV file is a much smaller file that only contains a heading with the possible fields.

{% file src="../../.gitbook/assets/sesar_sample_template (1).xlsx" %}
Downloadable SESAR Template File
{% endfile %}

{% file src="../../.gitbook/assets/sesar_sample_template.csv" %}
Downloadable SESAR CSV Template
{% endfile %}

Samples can be directly imported from IGSN SESAR using the "Import Samples from IGSN" App, which takes SESAR number(s) separated by commas as input and imports the sample information directly from SESAR.&#x20;

### NCBI BioSamples

NCBI BioSamples can be directly imported using the "Import Samples from NCBI" App, which takes the NCBI BioSample accession number(s), again separated by commas when importing multiple samples into the same SampleSet.

### ENIGMA

The Ecosystems & Networks Integrated with Genes & Molecular Assemblies (ENIGMA) Science Focus Area (SFA) partners with KBase for new functionality development. The ENIGMA metadata template is available as a template for the "Import Samples" App.&#x20;

{% file src="../../.gitbook/assets/enigma_format.xlsx" %}
Downloadable ENIGMA XLSX Template
{% endfile %}

{% file src="../../.gitbook/assets/enigma_format.csv" %}
Downloadable ENIGMA CSV Template
{% endfile %}

## Uploading and Importing

When uploading and importing Samples, new Samples can either be added to an existing SampleSet or used to create a new SampleSet. To add Samples to an existing SampleSet, choose the appropriate SampleSet from the drop-down in the importer. To create a new set, leave it blank and a new SampleSet will be created from the newly imported Samples.

#### _from IGSN or NCBI_

Samples can be directly imported from IGSN or NCBI using the "Import Samples from IGSN" or "Import from NCBI" Apps, respectively, searchable in the Upload section of the Apps panel. Samples imported using this method can be added to an existing SampleSet through selecting it from the SampleSet drop-down or can be used to create a new SampleSet. Additional parameters are the same as those for importing Samples manually (from local computer).

#### _from local_

Samples data is uploaded to the Staging Area and then imported into a Narrative. When importing new Samples, the default action is to create a new SampleSet. Individual samples must belong to a SampleSet, even if that SampleSet contains only one Sample.&#x20;

Samples must be in [SESAR or ENIGMA formats](sampleset.md#formatting-samplesets) to not limit analysis as these standards are required to validate most of the data. Non-validated data can be uploaded as user terms, but this will not allow comparisons across Samples. We recommend to change the column headers to correspond with the relevant SESAR or ENIGMA headers, and ensure the data matches.

### [_Data Validation_](../samples/ontology.md)

SampleSets that are uploaded to KBase are validated to ensure the data format is correct. If data does not match format requirements, the upload may result in an [error](sampleset.md#error-report-display).&#x20;

{% hint style="warning" %}
Critical errors, such as unrecognized units for a measurement, will prevent upload entirely. Minor errors, such as an unrecognized controlled vocabulary term, can be ignored by selecting the "Ignore Warnings" checkbox in the importer.
{% endhint %}

### Viewing

#### in the Narrative

Once imported, the SampleSet viewer widget allows you to see the Samples data that has been imported. This includes all metadata, such as collection information, and can be selectively viewed using the search bar.&#x20;

#### the Landing Page

More details for the SampleSets can be found on the landing page. Click on the SampleSet name in the viewer widget or the binoculars button in the data pane to view the landing page.

{% embed url="https://youtu.be/PFWNWji8p0U?t=461" %}
Uploading and Importing SampleSets
{% endembed %}

## Permissions

Permissions are managed separately from the Narrative workspace with some exceptions. The permissions for a Sample can be viewed in the **Sample landing page** under the **Access tab.** When a SampleSet is shared with a user, that user automatically has read access to  all Samples included in the SampleSet. Read access will automatically be given with the first access to the SampleSet by visiting its landing page or viewing it in the Narrative.

![Viewing Samples Access Permissions](../../.gitbook/assets/sample\_access.gif)

To grant a user increased permissions (e.g. to modify Samples), you should use the **Update SampleSet Access Controls App** in the Narrative.&#x20;

![Update SampleSet Access Controls App to change user permissions for specific SampleSets. ](../../.gitbook/assets/UpdateSampleSetAccess\_App.png)

{% hint style="warning" %}
Permissions will be granted for all Samples in the SampleSet. There is not currently a mechanism to change the permissions on a single app and there is not a method to easily revoke permissions.
{% endhint %}

## Updating Attributes

You will need to export a CSV file of the Samples from a SampleSet, modify the columns and/or their values, then re-import the Samples CSV using the Samples Importer App to edit Sample attributes (for example adding, modifying or removing columns or updating values).&#x20;

This will not modify existing data or analysis that has already been run. To update the analysis results, you will need to re-run the analysis apps using the new SampleSet with your recently updated Samples.

### Subsets and Supersets

Creating subsets and supersets in the Narrative is under development. The most efficient way manage subsets of Samples is to upload separate SampleSets for each subset, and a complete SampleSet to represent the parent set. In the same way, a superset can be created by downloading SampleSets, combining them, and then uploading the combined superset.

## Errors

The Samples Importer Apps are designed to encourage the use of validated data, but we are aware that not all information is accounted for in our validator, and sometimes wrangling the data to fit validation formats is not worth the effort. While we do encourage validation as much as possible, our importers use a two-tiered system of error reporting.

There are two, color-coded error types: red and yellow. &#x20;

1. Red errors indicate the validation failed to recognize a value as a validated field, such as the type "playdoh" for material. This prevents the importer from creating a SampleSet for any cell with values that do not comply with controlled vocabulary.&#x20;
2. Yellow errors indicate a column (in this case, "color") could not be validated as a controlled field. These result in warnings, but the SampleSet can still be created.

![Two kinds of errors - red errors are critical, while yellow are warnings](../../.gitbook/assets/sampleset\_upload\_errors.png)

### Handling Errors

Sample imports can return a "successful" job that does not create an object in the Data panel. In this case, you can interpret a successful job run to indicate that the sample file was read, but the contents may or may not be valid.

* A cell in a validated column that does not comply with the [controlled vocabulary](../samples/ontology.md) will fail to upload. Consult the [format guide](sampleset.md#formatting-samples-and-samplesets) or source of the template to determine if the value is accepted and if the vocabulary contains a valid term for your value. If your value is not part of the controlled vocabulary and there is not a suitable alternative, you can change the column header to a user defined field.

{% hint style="info" %}
&#x20;If you would like your term added to the controlled vocabulary, [please contact us](../../troubleshooting/support.md).&#x20;
{% endhint %}

* If there is a warning due to an unvalidated field, you can choose to accept the warning or decline it and fix the spreadsheet. If you accept an unvalidated field, it will be stored as a user-defined field. This allows you to include the information, but does not allow comparisons across Samples. For additional descriptive information, accepting the warning may be beneficial. But if the information is critical to Samples which you plan to use in analysis, we recommend manually fixing the values to comply with controlled vocabulary terms.&#x20;
* No mechanism exists to accept warnings _after_ the import has run. You can run the Importer App with the "Ignore Warnings" option unchecked. This allows you to see the errors and warnings and run does not create a data object. Then proceed to edit your spreadsheet and re-run the App with the warnings fixed, or run the App with the option checked and delete the resulting object if you find warnings you want to fix.

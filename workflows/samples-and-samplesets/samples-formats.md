---
description: A guide to formatting Samples data to comply with standard templates.
---

# Samples Formats

### IGSN SESAR

#### Samples based on SESAR

The SESAR \(System for Earth SAmple Registration\) format is one format that can be used in KBase for uploading Samples. Their samples have a controlled vocabulary for the various fields of data and metadata that can be included in SESAR samples. See their [vocabularies documentation page](https://www.geosamples.org/help/vocabularies) for a description of each of the fields. 

You can download a template of the SESAR format below and fill with your own data, or generate a new one from scratch based on their documentation linked above. The .xlsx file has pre-filled options for the columns with controlled vocabulary, whereas the CSV file is a much smaller file that only contains a heading with the possible fields.

{% file src="../../.gitbook/assets/sesar\_sample\_template \(1\).xlsx" caption="Downloadable SESAR Template File" %}

{% file src="../../.gitbook/assets/sesar\_sample\_template.csv" caption="Downloadable SESAR CSV Template" %}

#### Direct Import

Samples can be directly imported from IGSN SESAR using the "Import Samples from IGSN" app. This app takes SESAR number\(s\) separated by commas as input and imports the sample information directly from SESAR. 

### NCBI BioSamples

NCBI BioSamples can also be directly imported using the app "Import Samples from NCBI." This app takes the NCBI BioSample accession number\(s\), again separated by commas when importing multiple samples into the same SampleSet.

### ENIGMA Format

The Ecosystems & Networks Integrated with Genes & Molecular Assemblies \(ENIGMA\) Science Focus Area \(SFA\) partners with KBase for new functionality development. Their metadata template has been added as a usable template in the "Import Samples" app. 

{% file src="../../.gitbook/assets/enigma\_format.xlsx" caption="Downloadable ENIGMA XLSX Template" %}

{% file src="../../.gitbook/assets/enigma\_format.csv" caption="Downloadable ENIGMA CSV Template" %}




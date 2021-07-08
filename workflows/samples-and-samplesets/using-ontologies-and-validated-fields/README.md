---
description: Make the most out of your metadata by using KBase validation
---

# Using Ontologies and Validated Fields

### Introduction

The concept of "samples" can be often be ill-defined, without universal definitions for what information is included and how that information is presented. There are many standards, such as NCBI BioSamples and IGSN SESAR, that aim to describe sample metadata. These standards often overlap, but also often differ significantly depending on the focus of the entity that manages the samples. At the same time, many labs and smaller institutions often keep their own templates and organize their data in a specific way. Because of this, there must be a mechanism to integrate similar metadata from different sources as well as account for the differences between the sources. 

The development of Samples in KBase relies heavily on a common vocabulary within KBase. As such, KBase is implementing uploaders to ingest data from multiple sources, but this development takes time and not all sources will always be available. 

When uploading Samples to KBase, there are many metadata terms that are built in and can be validated. Doing so allows your data to be more easily compared with other data and allows us to integrate data when different sources may use different conventions. 

### Validated Metadata

When samples are uploaded into KBase via a spreadsheet, they are transformed into an internal representation.  The columns in the spreadsheet get mapped and transformed based on the template being used.  Columns that correspond to recognized terms are validated to ensure they are of the proper format.  This can include checking that the value is the proper type \(e.g. string versus a number\), in the correct range, match an enumerated list, or appear in an ontology.  These controlled terms are useful both because they undergo this validation but also they provide a more precise meaning for the value and comparisons accounting for units, such as one dataset measuring depth in centimeters and one in millimeters.  When the uploader encounters terms it doesn’t recognize, those terms and values will be stored in a user section of the samples.  These values still serve a purpose.  They can be used in analysis within that data set and they can provide contextual information that the original uploader understands.  However, they can not reliably be compared across sample sets and other samples in the system. For example, two projects may use the same term to represent different concepts \(e.g. depth below sea-level or depth below surface\).  Using templates and controlled terms clarifies the exact meaning of a term and enforces additional validation. For a full list of terms KBase recognizes, see this table \[link\].  If there are terms you would like added, please consult the instruction here \[link\] on how to request additions.

The file TSV file below contains a list of the metadata fields that are currently supported for validation along with a description that provides general formatting direction, such as units of measure. You can view the[ most up-to-date version of this list](https://github.com/kbase/sample_service_validator_config/blob/master/metadata_validation.tsv) on the project GitHub. 

{% file src="../../../.gitbook/assets/metadata\_validation.tsv" caption="Validated Metadata TSV" %}

If you have Sample Attribute columns that are represented as validated terms in SESAR, ENIGMA, or KBase formats, you may request the terms to be added to KBase's vocabulary. Expert KBase staff will review newly proposed attributes to assess: 1\) overlap with current supported attributes, 2\) existing or relevant ontological frameworks, and 3\) in the case of measured data, the presence of and interoperability of units.  


### Ontology Landing Pages

The Ontology API supports multiple ontology systems. Currently supported systems are Gene Ontology \(GO\) and Environmental Ontology \(ENVO\). You can see more information on both ontologies from their own home pages, or view the KBase landing page for a given ontology page with the links and URL format below \(respectively\).

* Gene Ontology \(GO\) - [http://geneontology.org](http://geneontology.org) 
  * https://ci.kbase.us/\#ontology/term/go\_ontology/GO:\#\#\#\#\#\#\#
* The Environmental Ontology \(ENVO\) - [https://sites.google.com/site/environmentontology/home](https://sites.google.com/site/environmentontology/home)
  * https://ci.kbase.us/\#ontology/term/envo\_ontology/ENVO:\#\#\#\#\#\#\#\#






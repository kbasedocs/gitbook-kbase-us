---
description: Make the most out of your metadata by using KBase validation
---

# Using Ontologies and Validated Fields

### Introduction

The concept of "samples" can be often be ill-defined, without universal definitions for what information is included and how that information is presented. There are many standards, such as NCBI BioSamples and IGSN SESAR, that aim to describe sample metadata. These standards often overlap, but also often differ significantly depending on the focus of the entity that manages the samples. At the same time, many labs and smaller institutions often keep their own templates and organize their data in a specific way. Because of this, there must be a mechanism to integrate similar metadata from different sources as well as account for the differences between the sources. 

The development of Samples in KBase relies heavily on a common vocabulary within KBase. As such, KBase is implementing uploaders to ingest data from multiple sources, but this development takes time and not all sources will always be available. 

When uploading Samples to KBase, there are many metadata terms that are built in and can be validated. Doing so allows your data to be more easily compared with other data and allows us to integrate data when different sources may use different conventions. 

### Validated Metadata

The file TSV file below contains a list of the metadata fields that are currently supported for validation along with a description that provides general formatting direction, such as units of measure. You can view the[ most up-to-date version of this list](https://github.com/kbase/sample_service_validator_config/blob/master/metadata_validation.tsv) on the project GitHub. 

{% file src="../../.gitbook/assets/metadata\_validation.tsv" caption="Validated Metadata TSV" %}

### Ontology Landing Pages

The Ontology API supports multiple ontology systems. Currently supported systems are Gene Ontology \(GO\) and Environmental Ontology \(ENVO\). You can see more information on both ontologies from their own home pages, or view the KBase landing page for a given ontology page with the links and URL format below \(respectively\).

* Gene Ontology \(GO\) - [http://geneontology.org](http://geneontology.org) 
  * https://ci.kbase.us/\#ontology/term/go\_ontology/GO:\#\#\#\#\#\#\#
* The Environmental Ontology \(ENVO\) - [https://sites.google.com/site/environmentontology/home](https://sites.google.com/site/environmentontology/home)
  * https://ci.kbase.us/\#ontology/term/envo\_ontology/ENVO:\#\#\#\#\#\#\#\#






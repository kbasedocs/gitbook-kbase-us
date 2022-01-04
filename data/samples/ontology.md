---
description: Make the most out of your metadata by using controlled vocabulary
---

# Ontologies and Validated Terms

**TL;DR: Use vocabulary that can be identified in KBase so your metadata is functional.**&#x20;

When uploading Samples to KBase, there are many metadata terms that are built in and can be validated. Doing so allows your data to be more easily compared with other data and allows us to integrate data when different sources may use different conventions.&#x20;

{% hint style="info" %}
Many standard terms, such as NCBI BioSamples and IGSN SESAR, aim to describe sample metadata. These standards often overlap and may differ significantly depending on the focus of the organization or institution that manages the samples. At the same time, many labs and smaller institutions have their own templates and organization of their data.&#x20;

Thus, there must be a way to integrate similar metadata from different sources and account for the differences between the sources.&#x20;
{% endhint %}

When Samples are uploaded into KBase via a spreadsheet, they are transformed into an internal representation. Columns within the spreadsheet are mapped and transformed based on the template used. Columns that correspond to recognized terms are validated to ensure they properly formatted, such as checking that the value is the proper type (e.g. string versus a number), in the correct range, match an enumerated list, or appear in an ontology.&#x20;

Controlled terms are useful both because they undergo this validation and they provide a more precise meaning for the value and comparisons accounting for units.&#x20;

When the uploader encounters terms it doesn’t recognize, those terms and values will be stored in a user section of the samples. These values still serve a purpose and can be used in analysis within that data set and they can provide contextual information that the original uploader understands.  However, unrecognized terms can not reliably be compared across SampleSets and other samples in the system. For example, two projects may use the same term to represent different concepts (e.g. depth below sea-level or depth below surface).&#x20;

Using templates and controlled terms clarifies the exact meaning of a term and enforces additional validation. For a full list of terms KBase recognizes, see the [validated metadata table](ontology.md#validated-metadata) below. If there are terms you would like added, please contact us at engage@kbase.us to suggest additions.

## Ontology Landing Pages

The Ontology API supports multiple ontology systems. Currently supported systems are Gene Ontology (GO) and Environmental Ontology (ENVO). You can see more information on both ontologies from their own home pages, or view the KBase landing page for a given ontology page with the links and URL format below (respectively).

* [Gene Ontology (GO)](http://geneontology.org)
  * KBase: https://narrative.kbase.us/#ontology/term/go\_ontology/GO:#######
* [The Environmental Ontology (ENVO)](https://sites.google.com/site/environmentontology/home)
  * KBase: https://narrative.kbase.us/#ontology/term/envo\_ontology/ENVO:########

## Validated Metadata Terms

The file TSV file below contains a list of the metadata terms currently supported for validation along with a description that provides general formatting direction. You can view the[ most up-to-date version of this list](https://github.com/kbase/sample\_service\_validator\_config/blob/master/metadata\_validation.tsv) in the KBase Samples GitHub.&#x20;

{% file src="../../.gitbook/assets/metadata_validation.tsv" %}
Validated Metadata TSV
{% endfile %}

{% hint style="info" %}
If you have Sample Attribute columns that are represented as validated terms in SESAR, ENIGMA, or KBase formats, you may request the terms to be added to KBase's vocabulary.&#x20;

KBase will review newly proposed attributes to assess: overlap with current supported attributes; existing or relevant ontological frameworks; and presence of and interoperability of units for measured data.&#x20;
{% endhint %}

### Unit Conversions

You can see a full list of the units and their defined relations to each other in [GitHub](https://github.com/hgrecco/pint/blob/master/pint/default\_en.txt).

### Terms

To determine if your term is valid, the easiest way is to search the[ ENVO Database](https://www.ebi.ac.uk/ols/ontologies/envo).&#x20;

## Commonly used units:

**Length**

* Base: meter, m
* Micron/micrometer: µm or um, 1\*10^-6 m
* Millimeter: mm, 1\*10^-3 m
* Centimeter: cm, 1\*10^-2 m
* Kilometer: km, 1\*10^3 m

**Time**

* Base: second, s
* Minute: min, 60 s
* Hour: hr, 3600 s or 60 min
* Day: d, 24 hr
* Year: yr or a, 365.25 d

**Mass**

* Base: gram, g
* Microgram: µg, 1\*10^-6 g
* Milligram: mg, 1\*10^-3 g
* Kilogram: kg, 1\*10^3 g

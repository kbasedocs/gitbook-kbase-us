---
description: >-
  Some of the tools in KBase available for rarefaction, standardization, and
  analyzing amplicon matrices and OTU tables.
---

# Amplicon / Data Matrices

### Data Cleaning

Rarefaction and standardization can be performed in KBase to track data provenance on how the data was transformed. These Apps can be used in any order and/or repeatedly. For instance to remove singletons, rarefy samples, and then calculate relative abundance of rarefied samples.&#x20;

* [Transform Matrix App](https://kbase.us/applist/apps/GenericsAPI/transform\_matrix/release) – uses an AmpliconMatrix object as input
  * provides abundance filtering, which can remove rows or columns if all values fall below a user-specified threshold and/or if the sum of all values falls below a user-specified threshold
  * perform standardization, with options for centering the data before scaling, scaling the data to unit variance, and whether to perform the standardization on columns or rows
  * perform ratio transformation, by either Centre or Isometric Log Ratio Transformation methods, and be applied to columns or rows&#x20;
* [Rarefy Matrix App](https://kbase.us/applist/apps/GenericsAPI/rarefy\_matrix/release) – allows manual selection of a seed value to aid reproducibility to columns or rows

### Taxonomic Classification

* Classify rRNA with taxonomy using naïve Bayes with RDP Classifier App (in dev/beta) – assigns taxonomies to amplicon matrices based on several gene databases including RDP Classifier 2.13 - 16srna, RDP Classifier - fungallsu, and SILVA 138 - SSU, Full Length. _Silva databases are currently under development_.
* [Taxonomy Abundance Barplot App](https://narrative.kbase.us/#catalog/apps/TaxonomyAbundance/run\_TaxonomyAbundance/beta) (in beta) – visualize the taxonomic abundance

### Statistical Analysis

Statistical comparisons can be calculated, such as clustering (hierarchical or k-means) and PCA analysis.&#x20;

* [Perform NMDS Analysis App](https://narrative.kbase.us/#catalog/apps/kb\_Amplicon/run\_metaMDS/beta) ([in beta](../beta.md)) – performs Non-metric Multidimensional Scaling Analysis on amplicon matrix data to visualize it in two dimensions
* [Perform Categorical Variable Statistics Analysis App](https://kbase.us/applist/apps/GenericsAPI/perform\_variable\_stats/release) – perform Categorical Variable Statistics Analysis on an amplicon matrix object
* [Perform Similarity Percentage (SIMPER) Statistics Analysis App](https://kbase.us/applist/apps/GenericsAPI/perform\_simper/release) – performs similarity percentage or SIMPER (Clarke 1993) analysis based on the decomposition of Bray-Curtis dissimilarity index

### Functional Prediction for Amplicon Matrices

* [Map Tax to Functions using FAPROTAX App](https://narrative.kbase.us/#catalog/apps/kb\_faprotax/faprotax/beta) – identify functions and assign them to a new AmpliconMatrix using a manually-curated database that focuses on marine and lake biochemistry, such as sulfur, nitrogen, hydrogen, and carbon cycling.

{% hint style="info" %}
[Louca Lab FAPROTAX site](http://www.loucalab.com/archive/FAPROTAX/lib/php/index.php?section=Home) ([http://www.loucalab.com/archive/FAPROTAX/](http://www.loucalab.com/archive/FAPROTAX/))

Louca, S., Parfrey, L.W., Doebeli, M. (2016) Decoupling function and taxonomy in the global ocean microbiome. Science **353**: 1272-1277. [https://www.science.org/doi/10.1126/science.aaf4507](https://www.science.org/doi/10.1126/science.aaf4507)
{% endhint %}

* [Predict prokaryote EC, KO, & MetaCyc function abundances with PICRUSt2 App](https://narrative.kbase.us/#catalog/apps/kb\_PICRUSt2/run\_picrust2\_pipeline/beta) – identify functions from many different ontologies, including COG, EC, and KO, or any combination of which can be chosen in the parameters. Create new FunctionalProfile objects for the SampleSet, AmpliconMatrix, or both, and outputs a new AmpliconMatrix Object.&#x20;

{% hint style="info" %}
Douglas, G.M., Maffei, V.J., Zaneveld, J.R. _et al._ (2020). PICRUSt2 for prediction of metagenome functions. _Nat Biotechnol_ **38:** 685–688 (2020). [https://doi.org/10.1038/s41587-020-0548-6](https://doi.org/10.1038/s41587-020-0548-6)

[PICRUSt2: An improved and extensible approach for metagenome inference](https://www.biorxiv.org/content/10.1101/672295v1.full.pdf) (preprint)
{% endhint %}

Most of the relevant KBase Apps can be found in the Utilities section of the Apps panel and filtered through searching with "GenericsAPI" or [GenericsAPI Module Catalog](https://narrative.kbase.us/#catalog/modules/GenericsAPI).&#x20;

---
description: Some of the tools in KBase available for metabolic modeling
---

# Metabolic Modeling

KBase has a suite of [Apps supporting the reconstruction, prediction, and design of metabolic models](https://kbase.us/applist/#Metabolic%20Modeling) in microbes and plants. Genome-scale metabolic models can be used to explore an organism’s growth in specific media conditions, determine which biochemical pathways are present, optimize production of an important metabolite, identify high flux pathways, and more.

### **Flux Balance Analysis**

* [Build Metabolic Model](https://kbase.us/applist/apps/fba\_tools/build\_metabolic\_model/release) – Construct genome-scale metabolic models based on a bacterial genome and media condition&#x20;
  * Red pathways is increased and blue pathways&#x20;
* [Gapfill Metabolic Model](https://kbase.us/applist/apps/fba\_tools/gapfill\_metabolic\_model/release) – Fill in missing reactions based on stoichiometry
* [Run Flux Balance Analysis](https://kbase.us/applist/apps/fba\_tools/run\_flux\_balance\_analysis/release) – Predict metabolic fluxes
* [Compare FBA solutions](https://kbase.us/applist/apps/fba\_tools/compare\_fba\_solutions/release) – __ Determine optimal conditions of flux&#x20;
* [Check Model Mass Balance](https://kbase.us/applist/apps/fba\_tools/check\_model\_mass\_balance/release) – Ensure accuracy&#x20;
* [Compare Models](https://kbase.us/applist/apps/fba\_tools/compare\_models/release) – View multiple models side by side

### Editing Models

* [Edit Metabolic Model](https://kbase.us/applist/apps/fba\_tools/edit\_metabolic\_model/release) – Build unique models suited to specific experiments.&#x20;
* __[Create or Edit Media](https://kbase.us/applist/apps/fba\_tools/edit\_media/release) – Create specialized growth conditions
* [Bulk Download Modeling Objects](https://kbase.us/applist/apps/fba\_tools/bulk\_download\_modeling\_objects/release) – Save modeling data for future analysis&#x20;

### Comparative Genomics

* [Propagate Model to New Genome](https://kbase.us/applist/apps/fba\_tools/propagate\_model\_to\_new\_genome/release) – Translate metabolic models from one organism to another

### Expression

* [Compare Flux with Expression ](https://kbase.us/applist/apps/fba\_tools/compare\_flux\_with\_expression/release)– Compare reaction fluxes with gene expression values to identify metabolic pathways where expression and flux data agree or conflict and compare with chemical abundance data
* [Simulate Growth on Phenotype Data](https://kbase.us/applist/apps/fba\_tools/simulate\_growth\_on\_phenotype\_data/release) – Reconcile models with empirical data

### **Metabolomics**

* [Escher Pathway Viewer App](https://narrative.kbase.us/#catalog/apps/kb\_escher/run\_kb\_pathway\_view/beta) ([in beta](../beta.md)) – Display Escher metabolic pathways and combine pathways with flux balance analysis and metabolomics data to view flux or expression.&#x20;
  * When viewing flux is in green and expression is in brown. The oval size and color intensity reflects metabolite abundance.&#x20;
* [PickAxe App](https://narrative.kbase.us/#catalog/apps/kb\_pickaxe/pickaxe/beta) ([in beta](../beta.md)) – Generate novel compounds from an FBA Model and a Chemical Abundance Matrix&#x20;
  * Pickaxe is part of the MINE Databases, documentation for which can be found here: [https://github.com/tyo-nu/MINE-Database/blob/master/minedatabase/pickaxe.py](https://github.com/tyo-nu/MINE-Database/blob/master/minedatabase/pickaxe.py).&#x20;
* [Fit Model to Exometabolite Data](https://narrative.kbase.us/#catalog/apps/fba\_tools/fit\_exometabolite\_data/beta) ([in beta](../beta.md)) – Identify biochemical reactions to add to a draft metabolic model for production and consumption of exometabolites&#x20;

### **Microbial Communities**

* [Merge Metabolic Models into Community Model](https://kbase.us/applist/apps/fba\_tools/merge\_metabolic\_models\_into\_community\_model/release) – Investigate community metabolism&#x20;
* [Build Metagenome Metabolic Model](https://kbase.us/applist/apps/fba\_tools/build\_metagenome\_model/release) – Build a metagenome metabolic model from an annotated assembly or bins

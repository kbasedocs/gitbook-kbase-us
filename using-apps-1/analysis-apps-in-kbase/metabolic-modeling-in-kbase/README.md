# Metabolic Modeling in KBase

![](../../../.gitbook/assets/model-icon.png) KBase has a suite of [Apps](https://kbase.us/applist/#Metabolic%20Modeling) and data that support the reconstruction, prediction, and design of metabolic models in microbes and plants. Genome-scale metabolic models are primarily reconstructed from protein functional annotations. These genome-scale metabolic models can be used to explore an organism’s growth in specific media conditions, determine which biochemical pathways are present, optimize production of an important metabolite, identify high flux pathways, and more.

Metabolic models can be used to evaluate an organism’s metabolic capability by simulating growth under different conditions to answer important biological questions such as:

* What biochemical pathways are present?
* What are the high flux pathways under a certain growth condition?
* Could the organism grow anaerobically?
* Would it grow under certain minimal media conditions?
* Could the organism be optimized to produce a particular drug molecule or industrially important biofuel?

### **Flux Balance Analysis**

* [Build Metabolic Model](https://narrative.kbase.us/#appcatalog/app/fba_tools/build_metabolic_model/release) – Construct genome-scale metabolic models from a genome and media condition 
* [Gapfill Metabolic Model](https://narrative.kbase.us/#appcatalog/app/fba_tools/gapfill_metabolic_model/release) – Fill in missing reactions based on stoichiometry
* [Run Flux Balance Analysis](https://narrative.kbase.us/#appcatalog/app/fba_tools/run_flux_balance_analysis/release) – Predict metabolic fluxes
* [Compare FBA solutions](https://www.youtube.com/watch?v=AQ2KsrQrq9s&list=PLh7Q4SqpZYTwdK8ekQnqKinFzbqZuzu8f) – __Determine optimal conditions of flux 
* [Check Model Mass Balance](https://narrative.kbase.us/#catalog/apps/fba_tools/check_model_mass_balance/release) – Ensure accuracy 
* [Compare Models](https://narrative.kbase.us/#appcatalog/app/fba_tools/compare_models/release) – View multiple models side by side

### Editing Models

* [Edit Metabolic Model](https://narrative.kbase.us/#catalog/apps/fba_tools/edit_metabolic_model/release) – Build unique models suited to specific experiments. 
* \_\_[Create or Edit Media](https://narrative.kbase.us/#catalog/apps/fba_tools/edit_media/release) – Create specialized growth conditions
* [Bulk Download Modeling Objects](https://narrative.kbase.us/#catalog/apps/fba_tools/bulk_download_modeling_objects/release) – Save modeling data for future analysis with _Bulk Download Modeling Objects_

### Comparative Genomics

* [Propagate Model to New Genome](https://narrative.kbase.us/#catalog/apps/fba_tools/propagate_model_to_new_genome/release) – Translate metabolic models from one organism to another

### Expression

* [Compare Flux with Expression ](https://narrative.kbase.us/#catalog/apps/fba_tools/compare_flux_with_expression/release)– Compare reaction fluxes with gene expression values to identify metabolic pathways where expression and flux data agree or conflict
* [Simulate Growth on Phenotype Data](https://narrative.kbase.us/#catalog/apps/fba_tools/simulate_growth_on_phenotype_data/release) – Reconcile models with empirical data

### **Microbial Communities**

* [Merge Metabolic Models into Community Model](https://narrative.kbase.us/#catalog/apps/fba_tools/merge_metabolic_models_into_community_model/release) – Investigate community metabolism 

Flowchart of apps used in Metabolic Modeling.

![](../../../.gitbook/assets/modeling-flowchart.jpg)

{% hint style="info" %}
**Learn More**

The flowchart above shows KBase’s metabolic modeling tools \(green\) as well as some other analysis tools. Check the [App Catalog](../../app-catalog.md) for the latest set of metabolic modeling analysis tools \(Apps\).
{% endhint %}

### Tutorials and Example Narratives

The [video tutorial](https://www.youtube.com/watch?v=AQ2KsrQrq9s&list=PLh7Q4SqpZYTwdK8ekQnqKinFzbqZuzu8f) below presents an introduction to building metabolic models in KBase. The “Microbial Metabolic Model Reconstruction and Analysis” Narrative tutorial lets you see and try out for yourself some examples of KBase’s metabolic modeling functionality in action. Common questions and answers about KBase’s metabolic modeling tools can be found in the [Metabolic Modeling FAQ](../../../running-common-workflows-1/faq-metabolic-modeling-in-kbase.md).

{% embed url="https://www.youtube.com/watch?v=AQ2KsrQrq9s" %}

* \*\*\*\*[Microbial Metabolic Model Reconstruction and Analysis Tutorial](https://narrative.kbase.us/narrative/ws.18302.obj.61)
* [Run Flux Balance Analysis Tutorial](https://kbase.us/run-flux-balance-analysis-method/)
* [Propagate Model to New Genome Tutorial](https://kbase.us/propagate-genome-scale-model-to-close-genome-app/)
* [Simulate Growth on Phenotype Data Tutorial](https://kbase.us/simulate-growth-on-phenotype-data-method/)
* [Modeling a Plant-Microbe Interaction Narrative](https://kbase.us/simulate-growth-on-phenotype-data-method/)

### **Publications**

* [Constructing and Analyzing Metabolic Flux Models of Microbial Communities](constructing-and-analyzing-metabolic-flux-models-of-microbial-communities.md)
* Modeling Central Metabolism and Energy Biosynthesis across Microbial Life: [Publication](http://bmcgenomics.biomedcentral.com/articles/10.1186/s12864-016-2887-8); [Narrative](https://narrative.kbase.us/narrative/ws.15253.obj.1)
* Microbial Community Metabolic Modeling: A Community Data-Driven Network Reconstruction: [Publication](http://onlinelibrary.wiley.com/doi/10.1002/jcp.25428/full); [Narrative](https://narrative.kbase.us/narrative/ws.13807.obj.1)


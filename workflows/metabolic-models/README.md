---
description: Running metabolic modeling workflows in KBase
---

# Constructing Metabolic Models

KBase has a suite of [Apps](https://kbase.us/applist/#Metabolic%20Modeling) and data that support the reconstruction, prediction, and design of metabolic models in bacteria, fungi, and plants using functionality from [ModelSEED](https://modelseed.org/) and [PlantSEED](https://modelseed.org/genomes/Plants) databases. Genome-scale metabolic models are primarily reconstructed from protein functional annotations. These genome-scale metabolic models can be used to explore an organism’s growth in specific media conditions, determine which biochemical pathways are present, optimize production of an important metabolite, identify high flux pathways, and more.

Metabolic models can be used to evaluate an organism’s metabolic capability by simulating growth under different conditions to answer important biological questions such as:

* What biochemical pathways are present?
* What are the high flux pathways under a certain growth condition?
* Could the organism grow anaerobically?
* Would it grow under certain minimal media conditions?
* Could the organism be optimized to produce a particular drug molecule or industrially important biofuel?

## Workflow

Flowchart of [Apps](https://kbase.us/applist/#Metabolic%20Modeling) used in [Metabolic Modeling](../../apps/analysis/metabolic-modeling.md).

![](../../.gitbook/assets/modeling-flowchart.jpg)

{% hint style="info" %}
**Learn More**

The flowchart above shows KBase’s metabolic modeling tools (green) as well as some other analysis tools. Check the [App Catalog](https://kbase.us/applist/#Metabolic%20Modeling) for the latest set of metabolic modeling analysis tools in KBase.

The [video tutorial](https://www.youtube.com/watch?v=AQ2KsrQrq9s\&list=PLh7Q4SqpZYTwdK8ekQnqKinFzbqZuzu8f) below presents an introduction to building metabolic models in KBase. The [“Microbial Metabolic Model Reconstruction and Analysis” Narrative tutorial](./#narrative-tutorial) lets you see and try out for yourself some examples of KBase’s metabolic modeling functionality in action. Common questions and answers about KBase’s metabolic modeling tools can be found in the [Metabolic Modeling FAQ](faq-metabolic-modeling.md).
{% endhint %}

## **Narrative Tutorials**

* ****[Microbial Metabolic Model Reconstruction and Analysis Tutorial](https://narrative.kbase.us/narrative/ws.18302.obj.61) – Guides through a workflow on how to draft a metabolic model and use KBase Apps to gapfill, run flux balance analysis and simulate growth.&#x20;
* [Constructing and Analyzing Metabolic Flux Models of Microbial Communities](metabolic-flux-models.md) – Provides a case study on current research in modeling the growth and behavior of microbial communities.
* Modeling Central Metabolism and Energy Biosynthesis across Microbial Life: [Publication](http://bmcgenomics.biomedcentral.com/articles/10.1186/s12864-016-2887-8); [Narrative](https://narrative.kbase.us/narrative/ws.15253.obj.1)
* Microbial Community Metabolic Modeling: A Community Data-Driven Network Reconstruction: [Publication](http://onlinelibrary.wiley.com/doi/10.1002/jcp.25428/full); [Narrative](https://narrative.kbase.us/narrative/ws.13807.obj.1)
* Case Study: Genome-wide Transcriptomics and Plant Primary Metabolism in response to Drought Stress in Sorghum – plant-based example of using KBase to integrate full genome RNA-seq analysis and a metabolic model to generate a reaction matrix. [Publication](https://doi.org/10.1016/j.cpb.2021.100229); [Narrative](https://kbase.us/n/101788/79/).&#x20;

### Metabolomics

* [Modeling and Integration of Omics Data in KBase](https://narrative.kbase.us/narrative/55494) – Demonstrates model construction, integration of transcriptomics and metabolomics data, and an example of data representation on metabolic maps based on a Yeast example.
* [Predicting Novel Compounds and Reactions using PickAxe](https://narrative.kbase.us/narrative/55494) – Demonstrates cheminformatics expansion of known metabolites, based on compounds within a metabolic model, and using the PickAxe App to map metabolomics data.

## Video Tutorials

{% embed url="https://www.youtube.com/watch?v=AQ2KsrQrq9s&t=7s" %}
Build Metabolic Model Tutorial&#x20;
{% endembed %}

{% embed url="https://youtu.be/a2WwjbPh3cA" %}
Introduction to Metabolic Modeling in KBase
{% endembed %}

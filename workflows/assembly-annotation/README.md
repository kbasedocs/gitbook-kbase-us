---
description: Running assembly and annotation in KBase
---

# Assembling and Annotating Microbial Genomes

KBase enables _de novo_ assembly of prokaryotic NGS reads from various sequencing platforms. Assemblies can then be annotated with RAST or Prokka, enabling you to explore structural and functional features of a Genome or use it in other analyses.&#x20;

{% hint style="info" %}
Steps for [assembly and annotation](../../apps/analysis/assembly-and-annotation.md) include:

1. Upload reads to assemble.
2. [Add your Reads data object](../../data/upload-download-guide/reads.md) to the Narrative.
3. Search the App Catalog and insert an [Assembly App](https://kbase.us/applist/#Genome%20Assembly)&#x20;
   * Use one of these tools to create an Assembly object.
4. Search the App Catalog and insert an [Annotation App](https://kbase.us/applist/#Genome%20Annotation)
   * Use one of these tools to annotate the Assembly object.
5. Examine assembly job statistics and genome annotation.
{% endhint %}

## Narrative Tutorials

* [Microbial Genome Assembly and Annotation Tutorial](https://narrative.kbase.us/narrative/ws.18188.obj.6) – guides through assembling a set of NGS short reads into contigs and annotate the assembled contigs, assigning biological functions derived from RAST&#x20;
* [Genome Analysis Tools and Features](https://narrative.kbase.us/narrative/48493) – a how-to guide for various tools to analyze genomic sequencing data in KBase from quality control and assessment of NGS reads, de novo assembly, and genome annotation.
* [Genome Analysis 1: Drafting Isolate Genomes](https://narrative.kbase.us/narrative/83666) – demonstrates how to draft isolate genomes from quality assessment to assembly and annotation
* [Genome Analysis 2: Identifying Features of Interest in Genomes](https://narrative.kbase.us/narrative/83681) – shows how to build a workflow for searching and identifying features within your genomes
* Genome Analysis 3: Domain Annotation and Feature Profiling – guides users through annotating protein families and analyzing features across a set of genomes for comparative analysis

## Video Tutorial

{% embed url="https://youtu.be/EGW3rA8tWf4" %}
Introduction to Genome Analysis
{% endembed %}

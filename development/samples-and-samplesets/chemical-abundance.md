---
description: Analyzing chemical abundance and metabolomics data in KBase
---

# Chemical Abundance

## Uploading to KBase

As with amplicon data, chemical abundance data works best with an existing SampleSet. If there is already a SampleSet to apply the chemical abundance data, a template can be generated using the "Create Chemical Abundance Matrix Template" app. This app generates a spreadsheet onto which you can copy your data to ensure it links to the SampleSet when it is uploaded. The app allows you to select chemical data to be included, such as aggregate M/Z, compound name, predicted formula, and more, depending on what data you have for upload. You can also select which chemical IDs to include in the template from KEGG, ChEBI, and ModelSEED. 

Once the template has been generated and you added your data, you can upload it using the "Import Chemical Abundance Matrix from CSV/Excel/TSV File in Staging Area" app. 

## Analysis

Metabolomics, exametabolite, and chemical abundance data can be integrated with metabolic modeling and flux balance analysis tools in KBase. 

### Differential Expression data and metabolomics data with metagenome metabolic models

A metagenome metabolic model can be built from an annotated assembly or bins using the "Build Metagenome Metabolic Model" app. Similarly, metabolic models for individual community members can be built and and merged using "Merge Metabolic Models into Community Model." For more information on building metabolic models, please see the metabolic modeling section of the documentation. 

Next, 'omics data and fluxes can be mapped to the metabolic models. Metabolomics data and expression matrices can be uploaded using the "Import Chemical Abundance Matrix from CSV/Excel/TSV File in Staging Area" and "Import TSV File as Expression Matrix from Staging Area" apps. The expression and chemical abundance data can then be compared using the app "Compare Flux with Expression." You can import an Escher metabolic pathways map using the "Escher Pathway Viewer" app, which can then be combined with the flux balance analysis and metabolomics data to view the pathways. 

You can see the workflow described here in more detail in the public Narrative at [https://narrative.kbase.us/narrative/55494](https://narrative.kbase.us/narrative/55494).

### Generating Novel Compounds using PickAxe

As above, metabolic models and FBA models can be used with chemical abundances for the PickAxe app. This app takes an  FBAModel and a ChemicalAbundanceMatrix to generate novel compounds. Pickaxe is part of the MINE Databases, documentation for which can be found here: [https://github.com/tyo-nu/MINE-Database/blob/master/minedatabase/pickaxe.py](https://github.com/tyo-nu/MINE-Database/blob/master/minedatabase/pickaxe.py). 

To see this workflow in a demo Narrative, see [https://narrative.kbase.us/narrative/61753](https://narrative.kbase.us/narrative/61753). 


---
description: Analysis apps for operating on matrix-based data types.
---

# Statistical, matrix, and Generics App

## What does "Generics" mean?

The GenericsAPI module is a group of apps that, for the most part, apply generically to multiple data types. In KBase, this mostly refers to the data associated with amplicon and chemical abundance matrices. However, as the name implies, these apps are extensible and will be usable with other data types in the future.

## Apps operating on Generics

### Matrix Manipulation

These apps allow you to perform manipulation of the matrix you upload. These apps were created to enable you to upload your raw data and perform and track the provenance of filtering, normalization, and transformation steps taken on those data.

The Collapse Matrix App is an amplicon-specific app that allows you to "roll up" your amplicon matrices to a higher level of taxonomy. While many of the apps that assign taxonomy and allow viewing outputs by taxonomic level, this app creates new matrices that are summed by the level of taxonomic classification you choose, allowing you to perform the downstream statistical apps on data with differing levels of granularity.

The Rarefy Matrix, Transform Matrix, and Transform Selected Variables from Matrix apps all work with multiple matrix types. These apps can be used sequentially and in any combination you choose. For details on using each of these apps, see the respective app's catalog page.

These apps will return new matrices. It is recommended that you choose a new name for the resulting matrix so that the original matrix with raw data is still available.

### Statistical Analysis

The following apps are available for performing statistical analyses on matrices:

* Perform PCA Analysis
* Perform Categorical Variable Statistics Analysis
* Perform Categorical Variable Statistics Analysis
* Perform Mantel Test
* Perform Similarity Percentage (SIMPER) Statistics Analysis

As with the transformation and rarefaction apps, these apps work on any matrix object. You can likewise see the details for each app in that app's catalog page.

These apps will return plots with the results. You can view the plots in the Narrative, in a separate tab, or download a zip file with the results to use in an external program or script.

### Correlation Apps

The following apps are available for creating correlation matrices:

* Compute Correlation Matrix - computes correlation with a given chemical abundance, amplicon, or other matrix.
* Compute Correlation Matrix Between Two Matrices - computes correlation between two matrices based on a row or column they have in common.

The output for these apps is a report with visualizations such as heatmaps, in addition to a CorrelationMatrix object. This CorrelationMatrix can be used with the Build Correlation Network app to create a network of correlations.&#x20;

As with the other apps, refer to the app catalog for details about the parameters for each app.


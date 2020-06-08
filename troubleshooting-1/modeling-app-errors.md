---
description: >-
  This is a list of error messages found within the Job Log for Modeling App
  Jobs, what they mean and how to go about fixing them or if a job ticket needs
  to be submitted.
---

# Modeling App Errors

## **Types of Errors**

* **UE**=Probably user error or user fixable
* **KE**=KBase error

{% hint style="info" %}
Use your Browser's search tool to paste in your error message to locate your error message, information about the error and next steps. 
{% endhint %}

You can always submit a ticket for help, questions, or follow-up to the [KBase Help Board](https://kbase-jira.atlassian.net/jira/your-work). 

## \*\*\*\*[**Bulk Download Modeling Objects**](https://narrative.kbase.us/#catalog/apps/fba_tools/bulk_download_modeling_objects/release)\*\*\*\*

#### `Must provide one and only one of workspace name` 

UE: No modeling objects were found the the user’s narrative. 

_Add some objects and try resubmitting the job._

#### `GLPK does not support ID's longer than 256 characters` 

KE: This option fails when this condition exists and the app needs maintenance.

_Nothing can be done at this time. KBase is working on a solution to this problem._ 

## [**View Flux Network**](https://narrative.kbase.us/#catalog/apps/fba_tools/view_flux_network/)

#### `Can't use an undefined value as an ARRAY reference` 

KE: The app is failing and needs maintenance. 

_Nothing can be done at this time. KBase is working on a solution to this problem._ 

#### `Authentication required for AbstractHandle but no authentication header was passed` 

KE: The app is failing and needs maintenance. 

_Nothing can be done at this time. KBase is working on a solution to this problem._ 

## [**Compare Models**](https://narrative.kbase.us/#catalog/apps/fba_tools/compare_models/)

#### `Must select at least two models to compare` 

UE: The app requires two or more models for the comparison. 

_Add at least one more model and and try resubmitting the job._


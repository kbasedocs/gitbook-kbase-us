---
description: >-
  This is a list of error messages found within the Job Log for Modeling App
  Jobs, what they mean and how to go about fixing them or if a job ticket needs
  to be submitted.
---

# Modeling App Errors

## **Types of Errors**

* **UE**=User fixable or possible user error
* **KE**=KBase error

{% hint style="info" %}
Use your Browser's search tool to paste in your error message to locate your error message, information about the error and next steps.&#x20;
{% endhint %}

You can always submit a ticket for help, questions, or followup to the [KBase Help Board](https://kbase-jira.atlassian.net/jira/your-work).&#x20;

## [**Bulk Download Modeling Objects**](https://narrative.kbase.us/#catalog/apps/fba\_tools/bulk\_download\_modeling\_objects/release)

#### `Must provide one and only one of workspace name`&#x20;

UE: No modeling objects were found the the user’s narrative.&#x20;

_Add some objects and try resubmitting the job._

#### `GLPK does not support ID's longer than 256 characters`&#x20;

KE: This option fails when this condition exists and the app needs maintenance.

_Nothing can be done at this time. KBase is working on a solution to this problem._&#x20;

## [**View Flux Network**](https://narrative.kbase.us/#catalog/apps/fba\_tools/view\_flux\_network/)

#### `Can't use an undefined value as an ARRAY reference`&#x20;

KE: The app is failing and needs maintenance.&#x20;

_Nothing can be done at this time. KBase is working on a solution to this problem._&#x20;

#### `Authentication required for AbstractHandle but no authentication header was passed`&#x20;

KE: The app is failing and needs maintenance.&#x20;

_Nothing can be done at this time. KBase is working on a solution to this problem._&#x20;

## [**Compare Models**](https://narrative.kbase.us/#catalog/apps/fba\_tools/compare\_models/)

#### `Must select at least two models to compare`&#x20;

UE: The app requires two or more models for the comparison.&#x20;

_Add at least one more model and and try resubmitting the job._

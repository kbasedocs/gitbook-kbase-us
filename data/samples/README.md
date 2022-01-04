---
description: How to link environmental sampling metadata with experimental data.
---

# Linking Metadata

{% hint style="info" %}
SampleSets are still a work in progress. Watch your inbox for notifications from KBase Outreach when these workflows go live.&#x20;

If you are interested in beta testing these Apps, please contact us at engage@kbase.us.
{% endhint %}

A Sample in KBase represents measured material from an experiment. It has a unique ID internal to KBase, aliases, related Samples, and structured metadata. Samples occur within a Narrative as a SampleSet, but the same Sample may be shared by multiple SampleSets.&#x20;

One key feature is linking the same data across many users and analyses. To do this, Sample aliases allow the same data uploaded by different users to be linked and connect different analyses of the same data. These aliases can also be used to link Samples in KBase with other methods of sample registration, such as ESS-DIVE or SESAR.&#x20;

Because the metadata about a sample is critically important for, KBase provides the option to [upload metadata spreadsheet](../upload-download-guide/sampleset.md)s to link Samples for more detailed analysis.

{% embed url="https://youtu.be/PFWNWji8p0U?t=1536" %}
Managing Linked Data
{% endembed %}

### During upload and import

Once a [SampleSet](../upload-download-guide/sampleset.md) is in system, it can be used when uploading [amplicon](../upload-download-guide/amplicon-matrix.md) or [chemical abundance](../upload-download-guide/chemical-abundance-matrix.md) matrices into KBase. This allows the amplicon and chemical abundance analysis to remain linked to the sample metadata and enrich analysis.

When uploading and importing either an amplicon matrix or chemical abundance matrix, select the corresponding SampleSet from the dropdown menu for the input before running the Import App.

# Managing Samples

## Permissions for Samples

The permissions for Samples are managed separately from the Narrative workspace with some exceptions. Similar to Narrative, a user can have read, write, and share privileges for a Sample.  The permissions for a Sample can be viewed in the Sample landing page under the Access tab and they can be modified using the Update SampleSet Access Controls app in the narrative.  

![Viewing Samples Access Permissions](../../.gitbook/assets/sample_access.gif)

In addition, when a SampleSet is shared with a user, that user automatically has read access to  all Samples included in the SampleSet.  Read access will automatically be given when they first access the SampleSet by going to its landing page or viewing it in the Narrative.  If you need to grant a user increased permissions \(e.g. to modify Samples\), you should use the Update SampleSet Access Controls app. Be warned that this permissions will be granted for all Samples in the SampleSet. We do not currently provide a mechanism to change the permissions on a single app and we do not currently provide a method to easily revoke permissions.

## Updating Sample Attributes

Currently, an in system Sample editor is not available. If you need to edit your Sample attributes by adding, modifying or removing columns or updating values, you will need to export a CSV file of the Samples from a SampleSet, modify the columns and/or their values, then re-import the Samples CSV using the Samples Importer App. This will not modify existing data or analysis that has already been run. To update the analysis results, you will need to re-run the analysis apps using the new SampleSet with your recently updated Samples.  
Similarly, subsets and supersets are under development. Currently, the most efficient way manage subsets of samples is to upload separate SampleSets for each subset, and a complete SampleSet to represent the parent set. In the same way, a superset can be created by downloading SampleSets, combining them, and then uploading the combined set.


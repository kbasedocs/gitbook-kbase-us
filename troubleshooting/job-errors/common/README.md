# Common Job Errors

This is a list of common job error messages found within the Job Log for all KBase Apps, what they mean and how to go about fixing them or if a job ticket needs to be submitted. 

You can always submit a ticket for help, questions, or follow-up to the [KBase Help Board](https://kbase-jira.atlassian.net/jira/your-work). 

## **Types of Errors**

* **UE**=User fixable or possible user error
* **KE**=KBase error
* **UK**=Unknown or multiple possibles causes
* **TE**=Temporary system problem

{% hint style="info" %}
Use your Browser's search tool to paste in your error message to locate your error message and next steps. 
{% endhint %}

## Common Job Error Messages

#### `(2, No such file or directory)` 

UK: The app did not produce any output or it produced output but none passed the filters. There may also be app-specific reasons described below. 

_Check the logs for more information and adjust filters as needed._ 

#### `Unable to build output viewer` 

UK: The job ran for more than 7 days and crashed. There is no output. Dependent on the reason for the crash, rerunning the job may work. 

_Resubmit job._ 

#### `Output file is not found, exit code 123` 

UK: No space left on device. The job may be too big for KBase in the current configuration. 

_Resubmit job to make certain the issue isn’t a conflict with other jobs. If this doesn’t work, submit a ticket to the_ [_Help Board_](https://kbase-jira.atlassian.net/projects/PUBLIC/issues)_._ 

#### `Output file is not found, exit code is 137` 

UK: Cause unknown. Job probably cancelled by another process but not the user. 

_Resubmit job._

#### `Job was cancelled as it ran overMax allotted time (604800000) milliseconds (10080) minutes` 

UE: Job ran for more than 7 days and finished cleanly. Likely the job is too big. 

_Resubmit job, dependent on the reason it took so long._ 

#### `'listener timeout after waiting for [600000] ms'` 

TE: The utility ElasticSearch went down. The fix is a manual process and may not get fixed during nights, weekends, and holidays. 

_Submit a ticket the the_ [_Help Board_](https://kbase-jira.atlassian.net/projects/PUBLIC/issues)_. Resubmitting the job every couple of hours until it runs may also work._ 

#### `kafka` 

TE: Any messages with the word kafka in the error. Something went wrong with the system. 

_Resubmit job. Report the issue to the_ [_Help Board_](https://kbase-jira.atlassian.net/projects/PUBLIC/issues) _if resubmitting doesn’t fix the problem._ 

#### `ProtocolError, Connection aborted., BadStatusLine` 

UK: Something went wrong with the reporting and cleanup at the end of the job. Intermittent error. The data is fine, but there will be no report at the end. If an object was created, clicking on it in the data panel will create a viewer for the object, which is likely missing. 

_Resubmit job if you need the end report._

#### `User XXXX may not read workspace nnnnn` 

UE: The app requires data owned by another user and you do not have access. In another scenario, either you or the user have deleted the original file. 

_Ask the user for access to the needed file or re-import file if deleted._ 

#### `GET` [`http://elasticsearch.kbase.us:9200/kbaseprod.taxon_*,-*_sub/data/_search`](http://elasticsearch.kbase.us:9200/kbaseprod.taxon_*,-*_sub/data/_search)`: HTTP/1.1 503 Service Unavailable` 

TE: A component in KBase needed to be rebooted and will recover in a few minutes. 

_Try resubmitting the job in 10-15 minutes._ 

#### `No such container:...`

TE: A known temporary error. 

_Resubmit job._ 

#### `Token validation failed: Too many open files'` 

TE: A known temporary error .

_Try resubmitting the job in 10-15 minutes._ 

#### `502 Server Error: Bad Gateway….` 

TE: A known temporary error.

_Resubmit job._ 

#### `Gee whiz, I sure am sorry, but an error occurred. Gosh!...... Object 19 cannot be accessed`

UE: User’s browser cache is retaining old information. In this case, it is 'Object 19'. One symptom is that the user gets the error but the narrative looks fine to others. 

_Try the following:_

* _Reload the page_ 
* _Close and reopen your narrative_ 
* _Log out and log back in again_
* _Clear your cache_

_If you find something that works, no need to try the others._

#### `Details: 500 globus_xio: ICE negotiation failed.`

UE: The error generally indicate a firewall issue. 

_Please refer to this question on the Globus forum for a similar question with its solution. If you are working from home, you can view the Globus documentation for configuring the firewall. If you are on an institution network, you'll probably have to request an exception from IT._




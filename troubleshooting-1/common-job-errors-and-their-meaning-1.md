# Common Job Errors and Their Meaning

Some job errors give an explanation of the problem and others are much more cryptic. In some cases, there is more information in the job log. The job log can be found in two places: the app’s Job Status tab and the Job Browser \(off the Dashboard\).

**The app’s Job Status tab**

![](http://kbase.us/wp-content/uploads/2014/10/AppErrorStatus-1.png)

**The Job Browser**

![](http://kbase.us/wp-content/uploads/2014/10/JobsPageError.png)

In the app’s Job Status tab, the job log starts at the bottom with the error highlighted in pink. Sometimes there is useful information just above the pink section. In the Job Browser, find the line with the job and click on the icon for the piece of paper. This will open up the log, starting at the top. The advantages of the Job Browser are: 1\) jobs not associated with an app \(e.g., export\) are included in the list, 2\) the job ID and worker node on the top line are easy to find, and 3\) it is easier to scroll through the log.

Some useful tips:

* Even if you find an explanation for your error on this page, it is okay to [submit a Help Board ticket](support.md) with follow-up questions.
* If the output object is created but the job ends in an error, assume that the error didn’t affect the data. Errors sometimes occur in the cleanup and reporting at the end but do not affect the output data.
* Jobs do not run more than 7 days. If the narrative and/or the Job Browser say that a job is still running after 7 days, assume that it is dead. Resubmitting might solve the problem but the job might be too big for KBase at this time. 
* Assemblers currently have an upper limit of between 180,263,840 paired reads and 240,351,788 reads depending on complexity. If the job has been run twice, exceeded the 7 day limit, and your data is in this size range, it may be too big for KBase at this time.
* Bowtie appears to have an upper limit between 3.5E+10 and 4.0E+10 bases. This appears to be due to not enough space at this time.
* If asked for a job ID, it is a 24-digit hexadecimal number that looks similar to this: 5e1e3234e4b0fb2e6517240a. It is in the first line of the job log.
* If asked for the node where the job ran, it is on the first line of the job log and looks similar to Running on chicagoawe163 or Running on uploadworker or Running on uploadworker-prod-dtn2
* Any file uploaded from a Windows machine might have  DOS-style carriage-return line files along with new-lines. This has been known to cause problems with importing FASTQ files \(described below\) and may affect other files as well.

Some problems can be solved without looking at the job log and others may be harder to decipher. The errors with a known cause and known solution are identified in the table below.

#### Table of Common Error Messages

Types: **UE**=Probably user error or user fixable, **KE**=KBase error, **UK**=Unknown or multiple possibles causes, **TE**=Temporary system problem

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Error Message</b>
      </th>
      <th style="text-align:left"><b>App(s)</b>
      </th>
      <th style="text-align:left"><b>Type</b>
      </th>
      <th style="text-align:left"><b>Most Likely Meaning</b>
      </th>
      <th style="text-align:left"><b>Action to Take</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">(2, No such file or directory)</td>
      <td style="text-align:left">All apps</td>
      <td style="text-align:left">UK</td>
      <td style="text-align:left">The app did not produce any output or it produced output but none passed
        the filters. There may also be app-specific reasons described below.</td>
      <td
      style="text-align:left">Check the logs for more information. It may be necessary to adjust filters.</td>
    </tr>
    <tr>
      <td style="text-align:left">Unable to build output viewer</td>
      <td style="text-align:left">All apps</td>
      <td style="text-align:left">UK</td>
      <td style="text-align:left">The job ran for more than 7 days and crashed. There is no output. Rerunning
        might work, depending on the reason for the crash.</td>
      <td style="text-align:left">Try resubmitting.</td>
    </tr>
    <tr>
      <td style="text-align:left">Output file is not found, <b>exit code 123</b>
      </td>
      <td style="text-align:left">All apps</td>
      <td style="text-align:left">UK</td>
      <td style="text-align:left">No space left on device. The job may be too big for KBase in the current
        configuration.</td>
      <td style="text-align:left">Try rerunning to make certain that it isn&#x2019;t a conflict with other
        jobs. If this doesn&#x2019;t work, a workaround that reduces the problem
        is probably needed.</td>
    </tr>
    <tr>
      <td style="text-align:left">Output file is not found, <b>exit code is 137</b>
      </td>
      <td style="text-align:left">Mostly import apps</td>
      <td style="text-align:left">UK</td>
      <td style="text-align:left">Cause unknown. Job probably cancelled by another process but not the user.</td>
      <td
      style="text-align:left">Try resubmitting.</td>
    </tr>
    <tr>
      <td style="text-align:left">Job was cancelled as it ran overMax allotted time (604800000) milliseconds
        (10080) minutes</td>
      <td style="text-align:left">All apps</td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The job ran for more than 7 days and finished cleanly. The job is probably
        too big.</td>
      <td style="text-align:left">Rerunning might work, depending on the reason it took so long.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x2018;listener timeout after waiting for [600000] ms&#x2019;</td>
      <td
      style="text-align:left">All apps</td>
        <td style="text-align:left">TE</td>
        <td style="text-align:left">A necessary utility called ElasticSearch went down. The fix is a manual
          process and may not get fixed during nights, weekends, and holidays.</td>
        <td
        style="text-align:left">Report the problem or resubmit the job every couple of hours until it
          runs.</td>
    </tr>
    <tr>
      <td style="text-align:left">Kafka &#x2013; Any messages with the word kafka in the error.</td>
      <td
      style="text-align:left">All apps</td>
        <td style="text-align:left">TE</td>
        <td style="text-align:left">Something went wrong with the system.</td>
        <td style="text-align:left">Report the issue if resubmitting doesn&#x2019;t fix the problem.</td>
    </tr>
    <tr>
      <td style="text-align:left">ProtocolError, Connection aborted., BadStatusLine</td>
      <td style="text-align:left">All apps</td>
      <td style="text-align:left">UK</td>
      <td style="text-align:left">Something went wrong with the reporting and cleanup at the end of the
        job.</td>
      <td style="text-align:left">It is only necessary to resubmit if you need the report at the end. The
        data is fine. If an object was created, clicking on it in the data panel
        will create a viewer for the object (which is probably missing).</td>
    </tr>
    <tr>
      <td style="text-align:left">User XXXX may not read workspace nnnnn</td>
      <td style="text-align:left">All apps</td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The app requires data which is owned by another user and you do not have
        access. For example, you copied a genome from another user and now you
        want to do annotation. The annotation needs access to the assembly object
        but the user may have the assembly in a different narrative that you cannot
        access. In another scenario, either you or the user have deleted the original
        assembly.</td>
      <td style="text-align:left">Ask the user for access to the needed file.</td>
    </tr>
    <tr>
      <td style="text-align:left">GET http://elasticsearch.kbase.us:9200/kbaseprod.taxon_*,-*_sub/data/_search:
        HTTP/1.1 503 Service Unavailable</td>
      <td style="text-align:left">All apps</td>
      <td style="text-align:left">TE</td>
      <td style="text-align:left">A component in KBase needed to be rebooted and will recover in a few minutes.</td>
      <td
      style="text-align:left">Try again in 10-15 minutes.</td>
    </tr>
    <tr>
      <td style="text-align:left">No such container:&#x2026;</td>
      <td style="text-align:left">All apps</td>
      <td style="text-align:left">TE</td>
      <td style="text-align:left">A known temporary error</td>
      <td style="text-align:left">Resubmit</td>
    </tr>
    <tr>
      <td style="text-align:left">Token validation failed: Too many open files&#x2019;</td>
      <td style="text-align:left">All apps</td>
      <td style="text-align:left">TE</td>
      <td style="text-align:left">A known temporary error</td>
      <td style="text-align:left">Wait awhile and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">502 Server Error: Bad Gateway&#x2026;.</td>
      <td style="text-align:left">All apps</td>
      <td style="text-align:left">TE</td>
      <td style="text-align:left">A known temporary error</td>
      <td style="text-align:left">Resubmit</td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Import</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Cannot connect to URL: ftp://ftp.imicrobe.us&#x2026;..</td>
      <td style="text-align:left">All import apps</td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The provided URL cannot be accessed from within KBase.</td>
      <td style="text-align:left">Double check the URL and its permission. Try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">Invalid FTP Link:&#x2026;</td>
      <td style="text-align:left">All import apps</td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The provided URL cannot be accessed from within KBase. Perhaps the option
        for &#x2018;Direct&#x2019; download should be specified instead of &#x2018;FTP&#x2019;
        (e.g., when downloading from the SRA)</td>
      <td style="text-align:left">Double check the URL and its permission. Try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">Invalid Google Drive Link&#x2026;</td>
      <td style="text-align:left">All import apps</td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The provided URL cannot be accessed from within KBase.</td>
      <td style="text-align:left">Double check the URL and its permission. Try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">(2, No such file or directory)</td>
      <td style="text-align:left">Bulk/Batch import</td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The file is not in the staging area.</td>
      <td style="text-align:left">Verify that the name is correct and upload is complete. Then resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">(2, No such file or directory)</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fastq_sra_as_reads_from_staging">Import file from SRA</a>
      </td>
      <td style="text-align:left">KE</td>
      <td style="text-align:left">The fastqdump ran but the file names are not the expected names. Error
        in KBase.</td>
      <td style="text-align:left">While KBase works on a fix, the following is a workaround. First, use
        the app &#x201C;Upload File to Staging from Web&#x201D; the upload all
        of your data. You can add all of the URLs you have listed in this app.
        Then, open up the staging area tab and follow the link to Globus online
        (you will need a Globus account linked to your KBase account). Rename the
        files by removing the &#x201C;.1&#x201D; from the end. Go back to KBase,
        and choose &#x201C;SRA Reads&#x201D; as the from the &#x201C;Import as&#x201D;
        dropdown menu and click the upload button (the first button to the right
        of that dropdown). That will open up an app that will add it to your narrative</td>
    </tr>
    <tr>
      <td style="text-align:left">SRA input file type selected. But missing SRA file</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fastq_sra_as_reads_from_staging">Import SRA</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The format of the file is not recognized.</td>
      <td style="text-align:left">Double check the file and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">Invalid FASTQ file &#x2026;..</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fastq_sra_as_reads_from_staging">Import SRA</a>
      </td>
      <td style="text-align:left">KE/ UE</td>
      <td style="text-align:left">Sometimes the user has specified the file name wrong. It can also happen
        because the importer has problems with file names that end in .1</td>
      <td
      style="text-align:left">While KBase works on a fix, the following is a workaround. First, use
        the app &#x201C;Upload File to Staging from Web&#x201D; the upload all
        of your data. You can add all of the URLs you have listed in this app.
        Then, open up the staging area tab and follow the link to Globus online
        (you will need a Globus account linked to your KBase account). Rename the
        files by removing the &#x201C;.1&#x201D; from the end. Go back to KBase,
        and choose &#x201C;SRA Reads&#x201D; as the from the &#x201C;Import as&#x201D;
        dropdown menu and click the upload button (the first button to the right
        of that dropdown). That will open up an app that will add it to your narrative</td>
    </tr>
    <tr>
      <td style="text-align:left">Error running command: /kb/deployment/bin/<b>fastq-dump</b>&#x2026;..</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fastq_sra_as_reads_from_staging">Import SRA</a>
        </td>
        <td style="text-align:left">UE</td>
        <td style="text-align:left">The file does not appear to be in the expected SRA format</td>
        <td style="text-align:left">Double check the file and try again</td>
    </tr>
    <tr>
      <td style="text-align:left">Error running command:<b>pigz&#x2026;..</b>
      </td>
      <td style="text-align:left">
        <p><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/unpack_staging_file">Unpack_staging_file</a>
        </p>
        <p><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fastq_sra_as_reads_from_staging">import_fastq/SRA</a>
        </p>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The file could not be unzipped by KBase and most likely couldn&#x2019;t
        be unzipped by the user either.</td>
      <td style="text-align:left">Verify the file is can be unzipped locally.</td>
    </tr>
    <tr>
      <td style="text-align:left">Both SRA and FASTQ/FASTA file given.</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fastq_sra_as_reads_from_staging">import _fastq/SRA</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The inputs should be either all FASTQ or all SRA.</td>
      <td style="text-align:left">Modify the inputs and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">Same file [XXX.XXXX.gz] is used for forward and reverse. Please select
        different files and try again.</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fastq_sra_as_reads_from_staging">Import FASTQ</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">There are names for both a forward and reverse strand and they are identical.</td>
      <td
      style="text-align:left">A Single-end read library only needs one name. A Paired-end read library
        needs two files with different names.</td>
    </tr>
    <tr>
      <td style="text-align:left">File /kb/XXX.fasta is not a FASTQ file</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fastq_sra_as_reads_from_staging">Import FASTQ</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">Either the file is not in FASTQ format or the file extension is not recognized.</td>
      <td
      style="text-align:left">Double check that the file is in the right format. Changing the extension
        to .fastq may be needed.</td>
    </tr>
    <tr>
      <td style="text-align:left">Invalid FASTQ file</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fastq_sra_as_reads_from_staging">Import FASTQ</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">
        <p>* The fastq file includes one or more sequences that are less than 10
          bases. Short reads are a problem for some of the tools.</p>
        <p>* The fastq file doesn&#x2019;t have the right number of lines. For example,
          the lines in a single-end file needs to be a multiple of four and interleaved
          paired-end library should be a multiple of eight.</p>
        <p>* The file</p>
        <p>* The options haven&#x2019;t been selected correctly. For example, using
          an interleaved fastq file but failing to check the Interleaved box. The
          page <a href="http://kbase.us/data-upload-download-guide/short-reads/">http://kbase.us/data-upload-download-guide/short-reads/</a> might
          be helpful here.</p>
        <p>* DOS-style carriage-return line files along with new-lines. Our fasta
          validation doesn&#x2019;t handle this properly. To remove the carriage
          return characters use can this unix command</p>
        <p>tr -d &#x2018;\015&#x2019; &lt; 1.fastq &gt;cleaned_1.fastq</p>
        <p><a href="https://support.nesi.org.nz/hc/en-gb/articles/218032857-Converting-from-Windows-style-to-UNIX-style-line-endings">https://support.nesi.org.nz/hc/en-gb/articles/218032857-Converting-from-Windows-style-to-UNIX-style-line-endings</a>
        </p>
        <p><a href="https://kb.iu.edu/d/acux">https://kb.iu.edu/d/acux</a>
        </p>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Reading FASTQ record failed &#x2013; non-blank lines are not a multiple
        of four.</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fastq_sra_as_reads_from_staging">Import FASTQ</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The number of lines in the FASTQ file are not a multiple of four.</td>
      <td
      style="text-align:left">Double check the file and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">Interleave failed &#x2013; reads files do not have an equal number of
        records&#x2026;.</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fastq_sra_as_reads_from_staging">Import FASTQ</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">Something went wrong trying to interleave the Paired-end files.</td>
      <td
      style="text-align:left">Double check the line count of the files. Hidden carriage returns or linefeeds
        in the file could contribute to the problem.</td>
    </tr>
    <tr>
      <td style="text-align:left">Deinterleave failed &#x2013; line count is not divisible by 8</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fastq_sra_as_reads_from_staging">Import FASTQ</a>
        </td>
        <td style="text-align:left">UE</td>
        <td style="text-align:left">The interleaved file does not appear to be the correct format.</td>
        <td
        style="text-align:left">Double check the file and try again</td>
    </tr>
    <tr>
      <td style="text-align:left">Object 1: Illegal character in object name</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fastq_sra_as_reads_from_staging">Import FASTQ</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The name of the output reads object can&#x2019;t have spaces or special
        characters.</td>
      <td style="text-align:left">Rename the output file and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">There are no contigs to save, thus there is no valid assembly.</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fasta_as_assembly_from_staging">Import FASTA</a>
        </td>
        <td style="text-align:left">UE</td>
        <td style="text-align:left">There are no contigs that passed the minimum contig size.</td>
        <td style="text-align:left">Adjust the minimum contig size or other optional parameters.</td>
    </tr>
    <tr>
      <td style="text-align:left">The FASTA header key XXX appears more than once in the file</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fasta_as_assembly_from_staging">Import FASTA</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The FASTA header lines may not be unique.</td>
      <td style="text-align:left">Double check the format of the header lines and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">This FASTA file has non nucleic acid characters</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fasta_as_assembly_from_staging">Import FASTA</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The file appears to be proteins or special characters instead of DNA.</td>
      <td
      style="text-align:left">Double check the file contents and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">This FASTA file may have amino acids in it instead of the required nucleotides.</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fasta_as_assembly_from_staging">Import FASTA</a>
        </td>
        <td style="text-align:left">UE</td>
        <td style="text-align:left">The file appears to be proteins instead of DNA.</td>
        <td style="text-align:left">Double check the file contents and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">FASTQ/FASTA input file type selected. But missing FASTQ/FASTA file</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fasta_as_assembly_from_staging">Import FASTA</a>
        </td>
        <td style="text-align:left">UE</td>
        <td style="text-align:left">The selected file does not match the import selected.</td>
        <td style="text-align:left">Select a valid combination and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">(\utf-8\, b\PK\\x03\\x04\\x14\\x00\\x08&#x2026;&#x2026;.</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_fasta_as_assembly_from_staging">Import FASTA</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">Attempt to import a zip file with multiple files as a single data object.</td>
      <td
      style="text-align:left">
        <p>Run the app</p>
        <p>&#x2018;Unpack a Compressed File in Staging Area&#x2019; on the file and
          resubmit.</p>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Duplicate gene ID: XXXX_xxxx</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_genbank_as_genome_from_staging">Import GenBank</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The gene IDs in the input file are not unique.</td>
      <td style="text-align:left">Edit the gene IDs and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">The input directory does not have any files with one of the following
        extensions .gbff,.gbk,.gb,.genbank,.dat,.gbf</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_genbank_as_genome_from_staging">Import GenBank</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The app only recognizes the listed file extensions as valid GenBank files.</td>
      <td
      style="text-align:left">Change the file extension and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">XXX is not a valid KBase taxon ID.</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_genbank_as_genome_from_staging">Import GenBank</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The Taxonomy ID in the advanced parameters is optional and needs to be
        an integer when specified. The user provided the text string &#x2018;XXX&#x2019;.</td>
      <td
      style="text-align:left">Use an integer taxon ID or leave it blank. The information will be picked
        up from the GenBank file or from the scientific name.</td>
    </tr>
    <tr>
      <td style="text-align:left">Every feature sequence id must match a fasta sequence id</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_gff_fasta_as_genome_from_staging">Import GFF</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">There is a problem with the GFF format. The IDs in the &#x2018;sequence
        source&#x2019; lines must match the header lines in the FASTA file.</td>
      <td
      style="text-align:left">Correct the format and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">unable to parse &gt;&#x2026;..</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_gff_fasta_as_genome_from_staging">Import GFF</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The file may not be in GFF format.</td>
      <td style="text-align:left">Double check the format of the file and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">Features must be completely contained within the Contig in the Fasta file.</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_gff_fasta_as_genome_from_staging">Import GFF</a>
        </td>
        <td style="text-align:left">UE</td>
        <td style="text-align:left">The coordinates for the feature are outside the bounds of the contig.</td>
        <td
        style="text-align:left">Double check the file where indicated and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">Starch.csv&#x201D; is not a valid EXCEL nor TSV file</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_tsv_excel_as_media_from_staging">Import media</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The file format is not recognized.</td>
      <td style="text-align:left">Double check the file and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">data file 4.xml either does not use commas or tabs as a separator</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_file_as_fba_model_from_staging">Import models</a>
        </td>
        <td style="text-align:left">UE</td>
        <td style="text-align:left">The file format is not recognized</td>
        <td style="text-align:left">Double check the file contents and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">No object with name _Nostoc_azollae__0708</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_uploadmethods/import_file_as_fba_model_from_staging">Import models</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The genome does not exist in the narrative</td>
      <td style="text-align:left">Correct the genome name and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Assembly</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">There are no contigs to save, thus there is no valid assembly.</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_SPAdes/">Assemble with SPAdes</a>,
        <a
        href="https://narrative.kbase.us/#catalog/apps/kb_assembly_compare/run_filter_contigs_by_length">Filter assembled contigs by length</a>
          </td>
          <td style="text-align:left">UE</td>
          <td style="text-align:left">There are no contigs that passed the minimum contig size.</td>
          <td style="text-align:left">Adjust the minimum contig size or other optional parameters.</td>
    </tr>
    <tr>
      <td style="text-align:left">Error running SPAdes, return code: 1</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_SPAdes">Assemble with SPAdes</a> or
        <a
        href="https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_hybridSPAdes">Assemble with hybridSPAdes</a>or <a href="https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_metaSPAdes/release">Assemble Reads with metaSPAdes</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">
        <ol>
          <li>The coverage of your input is so uneven that everything is disconnected.</li>
          <li>The reads contain too many k-mers to fit into available memory.</li>
          <li>Incomplete write! Reason: No space left on device.</li>
          <li>Coverage not uniform</li>
          <li>hybridSPAdes ended abnormally</li>
          <li>Failed to align paired reads</li>
          <li>left paired reads is not equal to right paired reads</li>
          <li>cannot specify any data types except a single paired-end library (optionally
            accompanied by a single library of TSLR-contigs, or PacBio reads, or Nanopore
            reads) in metaSPAdes mode</li>
          <li>The program was terminated by segmentation fault</li>
          <li>Too many erroneous kmers, the estimates might be unreliable</li>
        </ol>
      </td>
      <td style="text-align:left">Look for an explanation from SPAdes in the log.</td>
    </tr>
    <tr>
      <td style="text-align:left">Deinterleave failed &#x2013; line count is not divisible by 8</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_SPAdes">Assemble with SPAdes</a> or
        <a
        href="https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_hybridSPAdes">Assemble with hybridSPAdes</a>or <a href="https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_metaSPAdes/release">Assemble Reads with metaSPAdes</a>
          </td>
          <td style="text-align:left">UE</td>
          <td style="text-align:left">The interleaved file does not appear to be the correct format.</td>
          <td
          style="text-align:left">Double check the files are labeled properly and try again</td>
    </tr>
    <tr>
      <td style="text-align:left">Reads object XXX is marked as containing metagenomic data but the assembly
        method was not specified as metagenomic</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_SPAdes">Assemble with SPAdes</a> or
        <a
        href="https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_hybridSPAdes">Assemble with hybridSPAdes</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The input object and the selected parameters disagree</td>
      <td style="text-align:left">Change the data input or the app parameters and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">Plasmid assembly requires that one and only one library as input.</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_SPAdes">Assemble with SPAdes</a>
        </td>
        <td style="text-align:left">UE</td>
        <td style="text-align:left">There is more than one input library.</td>
        <td style="text-align:left">Change the input to be just one library, change the library source, or
          merge the libraries and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">Invalid type for object 27459/32/1&#x2026;..</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_hybridSPAdes/release">Assemble with hybridSPAdes</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The user is allowed to enter an Assembly for the long reads (like in the
        MaSuRCA app) but this results in an error.</td>
      <td style="text-align:left">Only use the object types listed and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">QUAST reported an error, return code was 4</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_SPAdes/run_metaSPAdes/release">Assemble Reads with metaSPAdes</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">None of the assembly files contains correct contigs (none greater than
        the minimum contig filter).</td>
      <td style="text-align:left">Provide different files or decrease &#x2013;min-contig threshold</td>
    </tr>
    <tr>
      <td style="text-align:left">Error on ObjectIdentity #1: Illegal character in object name</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/Velvet/run_velvet">Assemble with Velvet</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">Velvet did not assemble any contigs longer than the minimum length.</td>
      <td
      style="text-align:left">Change the configuration and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x2018;list index out of range&#x2019;</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/hipmer/run_hipmer_hpc">Assemble with Hipmer</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">There is no input data</td>
      <td style="text-align:left">Add data to the app and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">Error in HipMER execution</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/hipmer/run_hipmer_hpc/release">Assemble with Hipmer</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">
        <p>Possible causes:</p>
        <ol>
          <li>The data was a metagenome but the <b>metagenome flag was not enabled</b>
          </li>
          <li>The the metagenome flag was enabled but the data was <b>not a metagenome</b>
          </li>
          <li>Exceeded time limit at NERSC</li>
          <li></li>
          <li>Other data/parameter combinations that result in no returned assembly</li>
        </ol>
      </td>
      <td style="text-align:left">Change the configuration and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">Using input parameters, you have filtered all contigs from the HipMer
        assembly. Decrease the minimum contig size and try again</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/hipmer/run_hipmer_hpc/release">Assemble with Hipmer</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The minimum contig length is too large.</td>
      <td style="text-align:left">Lower the minimum contig length and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">(2, No such file or directory)</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/hipmer/run_hipmer_hpc">Assemble with Hipmer</a>
      </td>
      <td style="text-align:left">TE</td>
      <td style="text-align:left">Hipmer was in the queue too long and did not run.</td>
      <td style="text-align:left">Resubmit</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p>Error running command: XXX/config.txt</p>
        <p>Exit Code: 1</p>
      </td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_MaSuRCA/run_masurca_assembler">MaSuRCA Assembler</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">
        <ol>
          <li>invalid file for PACBIO</li>
          <li>invalid file for NANOPORE</li>
        </ol>
      </td>
      <td style="text-align:left">Double check the file and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">Genome at 48203/40/2 does not have reference to the assembly object</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_stringtie/run_stringtie/">Assemble with StringTie</a>
        </td>
        <td style="text-align:left">UE</td>
        <td style="text-align:left">A previous step (e.g., HISAT) used an assembly instead of a genome as
          input.</td>
        <td style="text-align:left">Go back to the previous step and use a genome as input.</td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Annotation</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Error invoking method call_features_rRNA_SEED</td>
      <td style="text-align:left">Annotate a <a href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/annotate_contigset/">contig</a> or
        <a
        href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/annotate_contigsets/">contigs</a>or a <a href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/reannotate_microbial_genome/">genome</a> or
          <a
          href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/reannotate_microbial_genomes/">genomes</a>with RAST</td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">One or more of the FASTA header lines are extremely long.</td>
      <td style="text-align:left">Shorten them, reupload, and resubmit. KBase is working on a solution to
        this problem.</td>
    </tr>
    <tr>
      <td style="text-align:left">too many contigs</td>
      <td style="text-align:left">Annotate a <a href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/annotate_contigset/">contig</a> or
        <a
        href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/annotate_contigsets/">contigs</a>or a <a href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/reannotate_microbial_genome/">genome</a> or
          <a
          href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/reannotate_microbial_genomes/">genomes</a>with RAST or <a href="https://narrative.kbase.us/#catalog/apps/ProkkaAnnotation/annotate_contigs/">annotate with PROKKA</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">RAST has a limit of 10,000 contigs. Prokka has a limit of 30,000 contigs.</td>
      <td
      style="text-align:left">Divide the file or bin the contigs before running RAST again.</td>
    </tr>
    <tr>
      <td style="text-align:left">The genome does not contain any CDSs or features!</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/modules/kb_plant_rast">Annotate plant transcripts</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The input genome does not have the needed features.</td>
      <td style="text-align:left">Double check the file and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">Object #1, 0ae7adb1-6351-4d26-a526-cc09c15e46ee.report has invalid reference:
        &#x2026;.</td>
      <td style="text-align:left">Annotate a <a href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/annotate_contigset/">contig</a> or
        <a
        href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/annotate_contigsets/">contigs</a>or a <a href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/reannotate_microbial_genome/">genome</a> or
          <a
          href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/reannotate_microbial_genomes/">genomes</a>with RAST</td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">There are no input datasets listed</td>
      <td style="text-align:left">Supply the dataset(s) and resubmit</td>
    </tr>
    <tr>
      <td style="text-align:left">Error on ObjectSpecification #1: Unable to parse version portion of object
        reference nnnn/2/1, nnnn to an integer</td>
      <td style="text-align:left">Annotate <a href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/annotate_contigsets/">contigs</a> or
        or <a href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/reannotate_microbial_genomes/">genomes</a> with
        RAST</td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The wrong delimiter was used in the free text of the Assembly list or
        Genome list. The list was by object ID, e.g., 54079/2/1</td>
      <td style="text-align:left">Change the delimiter to a semicolon (;) and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">Error on ObjectSpecification #1: Illegal number of separators /</td>
      <td
      style="text-align:left">Annotate <a href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/annotate_contigsets/">contigs</a> or
        or <a href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/reannotate_microbial_genomes/">genomes</a> with
        RAST</td>
        <td style="text-align:left">UE</td>
        <td style="text-align:left">The wrong delimiter was used in the free text of the Assembly list or
          Genome list. The list was by object name, e.g., My_genome</td>
        <td style="text-align:left">Change the delimiter to a semicolon (;) and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">(2, No such file or directory)</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/ProkkaAnnotation/annotate_contigs/">Prokka-annotate an assembly</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">One or more contigs had header lines longer than 37 characters.</td>
      <td
      style="text-align:left">Edit the fasta file, upload again, and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">name assembly_info is not defined</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/ProkkaAnnotation/annotate_contigs/">Prokka-annotate an assembly</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">You are running the beta version of the app</td>
      <td style="text-align:left">Change to the released version</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Modeling</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Must provide one and only one of workspace name</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/fba_tools/bulk_down/https://narrative.kbase.us/#catalog/apps/fba_tools/bulk_download_modeling_objects/">Bulk download of modeling objects</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">No modeling objects were found the the user&#x2019;s narrative.</td>
      <td
      style="text-align:left">Add some objects and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">GLPK does not support ID&#x2019;s longer than 256 characters</td>
      <td style="text-align:left">Download models in SBML</td>
      <td style="text-align:left">KE</td>
      <td style="text-align:left">This option fails when this condition exists and the app needs maintenance.</td>
      <td
      style="text-align:left">Nothing can be done at this time. KBase is working on a solution to this
        problem.</td>
    </tr>
    <tr>
      <td style="text-align:left">Can&#x2019;t use an undefined value as an ARRAY reference</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/fba_tools/view_flux_network/">View_flux_network</a> 
      </td>
      <td style="text-align:left">KE</td>
      <td style="text-align:left">The app is failing and needs maintenance.</td>
      <td style="text-align:left">Nothing can be done at this time. KBase is working on a solution to this
        problem.</td>
    </tr>
    <tr>
      <td style="text-align:left">Authentication required for AbstractHandle but no authentication header
        was passed</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/fba_tools/view_flux_network/">View_flux_network</a> 
      </td>
      <td style="text-align:left">KE</td>
      <td style="text-align:left">The app is failing and needs maintenance.</td>
      <td style="text-align:left">Nothing can be done at this time. KBase is working on a solution to this
        problem.</td>
    </tr>
    <tr>
      <td style="text-align:left">Must select at least two models to compare</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/fba_tools/compare_models/">Compare models</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The app requires two or more models for the comparison.</td>
      <td style="text-align:left">Add at least one more model and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Other</b>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Error running service CLI for method &#x2018;ClusterServiceR.cluster_hierarchical&#x2019;
        with exit code 1 &#x2026;&#x2026;</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_cluster_hierarchical/">expression_toolkit_cluster_hierarchical</a>,
        or <a href="https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_estimate_k/">expression_toolkit_estimate_k</a>,
        or <a href="https://narrative.kbase.us/#catalog/apps/KBaseFeatureValues/expression_toolkit_cluster_k_means/">expression_toolkit_cluster_k_means</a>
      </td>
      <td style="text-align:left">KE</td>
      <td style="text-align:left">The app is failing and needs maintenance.</td>
      <td style="text-align:left">Nothing can be done at this time. KBase is working on a solution to this
        problem.</td>
    </tr>
    <tr>
      <td style="text-align:left">cannot have both input_one_sequence and input_one_ref parameter</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_blast/BLASTp_Search/">BLAST</a>
        </td>
        <td style="text-align:left">UE</td>
        <td style="text-align:left">The app requires either a single Query Sequence or a Query Object with
          single sequence.</td>
        <td style="text-align:left">Change the inputs and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">output_one_name parameter required if input_one_sequence parameter is
        provided</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_blast/BLASTp_Search/">BLAST</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">If a Query Sequence is used as input, an Output Query Sequence must be
        named.</td>
      <td style="text-align:left">Add an output name or change the input. Try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">ABORT: You must run the RAST SEED Annotation App or use SKIP option&#x2026;.</td>
      <td
      style="text-align:left">View Function Profile of <a href="https://narrative.kbase.us/#catalog/apps/kb_phylogenomics/view_fxn_profile_featureSet/">featureset</a>,
        <a
        href="https://narrative.kbase.us/#catalog/apps/kb_phylogenomics/view_fxn_profile/">genomes</a>, or <a href="https://narrative.kbase.us/#catalog/apps/kb_phylogenomics/view_fxn_profile_phylo/">phylogenetic tree</a>
          </td>
          <td style="text-align:left">UE</td>
          <td style="text-align:left">The app is expecting RAST annotation for the input genome(s).</td>
          <td
          style="text-align:left">The easiest option is to check the &#x2018;Skip missing genomes&#x2019;
            box in the advanced parameters. For more complete output 1) run <a href="https://narrative.kbase.us/#catalog/apps/RAST_SDK/reannotate_microbial_genome/">Annotate Microbial Genome</a>(s)
            with RAST on the listed genomes and 2) use the genome(s) newly created
            by RAST as the input to the View Function Profile. Because the names are
            different, the app does not know how to find the newer version of the genome.</td>
    </tr>
    <tr>
      <td style="text-align:left">ABORT: You must run the &#x2018;Domain Annotation&#x2019; App or use SKIP
        option &#x2026;.</td>
      <td style="text-align:left">View Function Profile of <a href="https://narrative.kbase.us/#catalog/apps/kb_phylogenomics/view_fxn_profile_featureSet/">featureset</a>,
        <a
        href="https://narrative.kbase.us/#catalog/apps/kb_phylogenomics/view_fxn_profile/">genomes</a>, or <a href="https://narrative.kbase.us/#catalog/apps/kb_phylogenomics/view_fxn_profile_phylo/">phylogenetic tree</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The app is expecting <a href="https://narrative.kbase.us/#catalog/modules/DomainAnnotation">Domain annotation</a> for
        the input genome(s).</td>
      <td style="text-align:left">Either run the Domain Annotation on the listed genome(s) or check the
        &#x2018;Skip missing genomes&#x2019; box in the advanced parameters.</td>
    </tr>
    <tr>
      <td style="text-align:left">Error processing genome [xxx/xxx/x] (Not one protein family member found)</td>
      <td
      style="text-align:left">Insert <a href="https://narrative.kbase.us/#catalog/apps/SpeciesTreeBuilder/insert_set_of_genomes_into_species_tree/">genome</a> or
        <a
        href="https://narrative.kbase.us/#catalog/apps/SpeciesTreeBuilder/insert_genomeset_into_species_tree">genomes</a>into a species tree</td>
          <td style="text-align:left">UE</td>
          <td style="text-align:left">The species tree is built using the predicted proteins in the genomes.</td>
          <td
          style="text-align:left">Run an app that does gene calling/genome annotation on the listed genome(s).
            Either RAST or Prokka annotation will work.</td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Feature ID AT2G30640 does not exist in the supplied genome</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/FeatureSetUtils/build_feature_set/">Build a Feature Set</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The selected feature does not exist in the genome.</td>
      <td style="text-align:left">Double check the selection and try again.</td>
    </tr>
    <tr>
      <td style="text-align:left">incompatible read library types in ReadsSet</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_ReadsUtilities/KButil_Merge_MultipleReadsLibs_to_OneLibrary/">Merge Reads Libraries</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">Every library in the input to merge must be of the same type, either all
        Paired-End or Single-End.</td>
      <td style="text-align:left">Change the inputs and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">missing or empty krona input file</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_kaiju/run_kaiju">Classify Taxonomy with Kaiju</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The filters were too restrictive and no output was generated</td>
      <td style="text-align:left">Change the input parameters and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">Object NNN cannot be accessed: User user_name may not read workspace XXXXX</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_Msuite/run_checkM_lineage_wf/release">Assess genome quality with checkM</a>
        </td>
        <td style="text-align:left">UE</td>
        <td style="text-align:left">The app requires data which is owned by another user and you do not have
          access. For example, you copied a genome from another user and now you
          want to do annotation. The annotation needs access to the assembly object
          but the user may have the assembly in a different narrative that you cannot
          access. In another scenario, either you or the user have deleted the original
          assembly.</td>
        <td style="text-align:left">Ask the user for access to the needed file.</td>
    </tr>
    <tr>
      <td style="text-align:left">(1, &#x2018;/bin/bash -c &#x201C;source activate py2 &amp;&amp; GTDBTK_DATA_PATH</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_gtdbtk/run_kb_gtdbtk/release">GTDB-Tk classify</a>
        </td>
        <td style="text-align:left">KE</td>
        <td style="text-align:left">Unknown error.</td>
        <td style="text-align:left">Nothing can be done at this time. KBase is working on a solution to this
          problem.</td>
    </tr>
    <tr>
      <td style="text-align:left">(2, &#x2018;/bin/bash -c &#x201C;source activate py2 &amp;&amp; GTDBTK_DATA_PATH</td>
      <td
      style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_gtdbtk/run_kb_gtdbtk/release">GTDB-Tk classify</a>
        </td>
        <td style="text-align:left">UE</td>
        <td style="text-align:left">The &#x2018;Minimum Alignment Percent&#x2019; was left blank</td>
        <td style="text-align:left">Assign a minimum percent in the advanced parameters and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">Invalid input:nselect Run All Paired Condition Combinations or provide
        partial condition pairs. Dont do both</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kb_deseq/run_DESeq2/release">Create Differential Expression Matrix using DeSEQ2</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The user failed to select ALL vs Partial conditions. It can&#x2019;t be
        blank and you can&#x2019;t select both.</td>
      <td style="text-align:left">
        <p>Do one and only one of the following:</p>
        <ol>
          <li>Check the box next to &#x2018;Run All Paired Condition Combinations&#x2019;</li>
          <li>Add a &#x2018;Run Partial Paried Condition Combinations&#x2019;</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">(2, No such file or directory)</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/gottcha2/run_gottcha2/">GOTTCHA</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">The wrong reference database was used</td>
      <td style="text-align:left">Change the reference database and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">(2, No such file or directory)</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/gottcha2/run_gottcha2/">GOTTCHA</a>
      </td>
      <td style="text-align:left">KE</td>
      <td style="text-align:left">More than two reads libraries were included in the input.</td>
      <td style="text-align:left">The developers have a task to fix this. The workaround is to only submit
        a maximum of two libraries at a time. Merging reads libraries can help
        with this process.</td>
    </tr>
    <tr>
      <td style="text-align:left">You must enter either an input genome or input reads</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/kraken2/run_kraken2/beta">Kraken</a>
      </td>
      <td style="text-align:left">UE</td>
      <td style="text-align:left">There are two input options and one of them must be selected.</td>
      <td
      style="text-align:left">Add a input and resubmit.</td>
    </tr>
    <tr>
      <td style="text-align:left">Cannot write data to fasta</td>
      <td style="text-align:left"><a href="https://narrative.kbase.us/#catalog/apps/VirSorter/run_VirSorter/release">VirSorter</a>
      </td>
      <td style="text-align:left">KE</td>
      <td style="text-align:left">The user interface allows users to enter a genome as input but the app
        will reject it. The error has been reported.</td>
      <td style="text-align:left">Change to an input that is not a genome and resubmit.</td>
    </tr>
  </tbody>
</table>
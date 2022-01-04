# FAQ: Assembly and Annotation

## Before submitting them for annotation. Is there a direct way to import to JGI or do we have to save FASTA files and separately submit to JGI/IMG?&#x20;

This page on transferring data from JGI to KBase takes you through the process. You can also start from the KBase search and use the JGI tab.&#x20;

## What is the typical threshold to determine whether our assembled genome is contaminated?&#x20;

In general, a genome that is >90% complete and <5% contaminated is high quality. A rough guide to the quality of MAGs and SAGs can be found here: [https://www.nature.com/articles/nbt.3893](https://www.nature.com/articles/nbt.3893)&#x20;

## Is there a limit on the size of the FASTQ files I can upload to KBase?&#x20;

Assemblers currently have an upper limit of between 180,263,840 paired reads and 240,351,788 reads depending on complexity. If the job has been run twice, exceeded the 7 day limit, and your data is in this size range, it may be too big for KBase at this time.&#x20;

## What is the best assembler?&#x20;

The “best” assembler often depends on the user. Sometimes the user may want the most contiguous metagenome, or an assembly with minimized assembly artifacts. Users can use multiple assemblers and choose whichever results in the best assembly for their purpose.&#x20;

## How do I compare the results of various assemblers?&#x20;

You can use the [QUAST App](https://kbase.us/applist/apps/kb\_quast/run\_QUAST\_app/release) to compare the contig distributions of Assembly objects.&#x20;

## Does KBase support co-assembly?&#x20;

Yes, but the results are unstable currently above 200 M reads (Illumina 150bp x 2). Use the [Merge Reads Libraries App](https://kbase.us/applist/apps/kb\_ReadsUtilities/KButil\_Merge\_MultipleReadsLibs\_to\_OneLibrary/release) to get a combined Reads Library object.&#x20;

## JGI/IMG recommends KBase for genome assembly before submission to them for annotation. Is there a direct way to import to JGI or do we have to save FASTA files and separately submit to JGI/IMG?

These [instructions on transferring data from JGI to KBase](https://docs.kbase.us/data/jgi-transfer) takes you through the process. You can also start from the KBase search and use the JGI tab.

## What is the difference between RAST and Prokka annotations?&#x20;

In addition to having different options in the app, their method for assigning the annotation is different. The determination of better or worse is in the eye of the beholder. The primary advantage of RAST is its linking to our metabolic modeling. The RAST functional roles are considered a controlled vocabulary where we map specific RAST annotations to biochemical reactions in the model, so if you plan to build metabolic models, you should annotate with RAST. Because RAST tends to assign more hypothetical proteins, some people will run Prokka first, and then reannotate with RAST using the Retain old annotation for hypotheticals option.&#x20;

## What is the difference between Annotate Microbial Genome and Annotate Microbial Assembly?

[Annotate Microbial Assembly](https://kbase.us/applist/apps/RAST\_SDK/annotate\_contigset/release) takes an Assembly object, follows it by gene calling using algorithms from Prodigal and Glimmer, and then functional annotation.&#x20;

[Annotate Microbial Genome](https://kbase.us/applist/apps/RAST\_SDK/reannotate\_microbial\_genome/release) takes a Genome object, does not call genes, and instead preserves the original gene calls. It then re-annotates the genes, overwriting previous annotations.&#x20;

## Is it possible or necessary to manually curate annotations, or are the RAST and Prokka annotations sufficient?&#x20;

Manual curation of annotations is not supported on-system. RAST and Prokka are likely sufficient for many applications, but as you mention, for difficult-to-annotate or highly divergent metabolic genes you may need to use additional tools. In addition to RAST and Prokka, there are on-system tools available for feature annotation using pre-generated hidden Markov models, which could be useful for higher-resolution annotation.&#x20;

## Does RAST annotate archaea and protists?&#x20;

[RAST](https://kbase.us/applist/apps/RAST\_SDK/annotate\_contigset/release) primarily annotates bacteria and archaea, and may be limited with protists.&#x20;

## Can I annotate plants or fungi?&#x20;

Tools available for plant annotations include [Annotate Plant Transcripts with Metabolic Functions](https://kbase.us/applist/apps/kb\_plant\_rast/annotate\_plant\_transcripts/release) and [Annotate Plant Enzymes with OrthoFinder](https://kbase.us/applist/apps/kb\_orthofinder/annotate\_plant\_transcripts/release). These tools use the PlantSEED curated Database.&#x20;

For fungi, it is recommended to use external tools and then import the annotated genomes into KBase.&#x20;

# FAQ: Assembly and Annotation

## Is there a limit on the size of the FASTQ files I can upload to KBase?

Assemblers currently have an upper limit of between 180,263,840 paired reads and 240,351,788 reads depending on complexity. If the job has been run twice, exceeded the 7 day limit, and your data is in this size range, it may be too big for KBase at this time.

## What is the best assembler?

The “best” assembler often depends on the user. Sometimes the user may want the most contiguous metagenome, or an assembly with minimized assembly artifacts. Users can use multiple assemblers and choose whichever results in the best assembly for their purpose.

## How do I compare the results of various assemblers?

You can use the QUAST App to compare the contig distributions of Assembly objects.

## Does KBase support co-assembly?

Yes, but the results are unstable currently above 200 M reads \(Illumina 150bp x 2\). Use the Merge Multiple Reads Libraries App to get a combined Reads Library object.

## What is the typical threshold to determine whether our assembled genome is contaminated?

In general, a genome that is &gt;90% complete and &lt;5% contaminated is high quality. A rough guide to the quality of MAGs and SAGs can be found here: [https://www.nature.com/articles/nbt.3893](https://www.nature.com/articles/nbt.3893)

## What is the difference between RAST and Prokka annotations?

In addition to having different options in the app, their method for assigning the annotation is different. The determination of _better_ or _worse_ is in the eye of the beholder. The primary advantage of RAST is its linking to our metabolic modeling. The RAST functional roles are considered a controlled vocabulary where we map specific RAST annotations to biochemical reactions in the model, so if you plan to build metabolic models, you should annotate with RAST. Because RAST tends to assign more hypothetical proteins, some people will run Prokka first, and then reannotate with RAST using the _Retain old annotation for hypotheticals_ option.

## What is the difference between Annotate Microbial Genome and Annotate Microbial Assembly?

Annotate Microbial Assembly takes an Assembly object, follows it by gene calling using algorithms from Prodigal and Glimmer, and then functional annotation. 

Annotate Microbial Genome takes a Genome object, does not call genes, and instead preserves the original gene calls. It then re-annotates the genes, overwriting previous annotations.

## Is it possible or necessary to manually curate annotations, or are the RAST and Prokka annotations sufficient?

Manual curation of annotations is not supported on-system. RAST and Prokka are likely sufficient for many applications, but as you mention, for difficult-to-annotate or highly divergent metabolic genes you may need to use additional tools. In addition to RAST and Prokka, there are on-system tools available for feature annotation using pre-generated hidden Markov models, which could be useful for higher-resolution annotation.

## Can I annotate plants or fungi?

Currently KBase does not have good annotation tools for eukaryotes. We recommend using external tools and then importing annotated genomes to KBase.


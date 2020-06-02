# FAQ: RNA Sequence Analysis

## Can I assemble a transciptome for a species that does not have a reference genome using KBase? 

Currently KBase only offers RNA-seq using the Tuxedo suite, which usese reference genome-guided transcriptome assembly. We do not have stand-alone tools like Trinity for _de novo_ transcriptome assembly.

## Where can I find reference genomes? 

Public genomes are available through the public data tab. You can directly import genomes from NCBI ReqSeq. You can also import genomes if they are not found in RefSeq. You can use the Upload From Web App if the files are available publicly online, or upload via Globus or the drag and drop upload if they are on your local machine.

## Are there some references to what tools \(aligner, assembler, etc\) we should apply to certain situations \(e.g. transciptomics, metatranscriptomics, extreme-conditions communitites\)? Or should we apply every combination of tools to every analysis we perform, and see which combination performs better?

 Certain tools are recommended only for prokaryotes, such as Bowtie2. We recommend HISAT2 for aligner, StringTie for assembler, and DEseq2 for differential gene expression for prokaryotes. We do offer an additional tool, Cuffdiff, for differential gene expression. For eukaryotes, we offer Tophat2 or HISAT2 for assembly and Ballgown, Cuffdiff, and DESeq2 for differential gene expression. Our suggested pipelines are below: For prokaryotes - Bowtie2/HISAT2 ? StringTie ? DESeq2 \(DESeq2 is based on gene counts\). If you want to compare it with gene abundance, you can run Cuffdiff instead of DESeq2 at the last step. For Eukaryotes - HISAT2 ? StringTie ? DEseq2/Ballgown \(you can run with Ballgown only if you want to compare these two different algorithms for differential gene expression\). Though Cuffdiff can also work with eukaryotes but it is quite slow and too compute intensive for eukaryotes. So, Cuffdiff is only recommended if you have very few samples.

## When you have replicates, is the analysis done for each of the replicates, or are the replicates pooled to do one analysis? 

The RNA-seq apps such as aligners \(HiSat, TopHat2, Bowtie\) and transcriptome assemblers \(StringTie, Cufflinks\) work on each of the replicates and generate corresponding analysis output objects. However, these apps also wrap the individual results into a set to pass conveniently for the downstream app. However, the Apps such as DESeq2 and ?Create Feature Set/Filtered Expression Matrix From Differential Expression? by definition need to operate on two or more conditions and operate on pools of replicates as opposed to individual replicates.

## Can I compare RNA sequencing data with genome-scale metabolic modes?

 Yes, the Compare Flux with Expresson allows you to compare the two. You can also use the ?Run Flux Balance Analysis? app to predict fluxes using your expression data. In this approach, you pick a threshold expression level \(as a percentile\), and the app tries to turn off reactions associated with genes expressed below the threshold and turn ?on? reactions associated with genes expressed above the threshold. We are actively working on this method now, but you are welcome to try it out. It?s fully deployed. Just load you expression data into KBase using the upload tool or by running the RNA-seq pipeline \(which will make a matrix for you\). Then select this matrix in the advanced parameters of the Run Flux Balance Analysis app, and specify which column of the matrix you want to use to constrain your fluxes.

## Does KBase support metatransciptomic assembly?

 Cufflinks and Stringtie are available for metatranscriptomics.


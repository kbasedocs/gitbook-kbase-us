# FAQ: Metabolic Modeling

KBase has a suite of analysis apps and data that support the reconstruction, prediction, and design of metabolic networks in microbes and plants. These tools can help advance efforts to optimize microbial production of a certain biofuel, find the minimal media conditions under which that fuel is generated, or predict soil amendments that improve the productivity of plant bioenergy feedstocks.

The [“Microbial Metabolic Model Reconstruction and Analysis” Narrative tutorial](./#narrative-tutorial) lets you see some of this functionality in action.

Below are answers to common questions about KBase’s metabolic modeling tools.

For more information — including descriptions of the underlying algorithms, inputs, and outputs — see the [Metabolic Modeling Apps](../../apps/analysis/metabolic-modeling.md).

## What _is_ Flux Balance Analysis?

One of the best papers on the fundamentals of FBA is the aptly titled ["What is Flux Balance Analysis" by Jeffrey Orth, Ines Thiele, and Bernhard Palsson. ](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3108565/)We highly recommend starting there to understand how FBA works in general.

For a detailed description of Model SEED, which KBase uses for modeling, see [High-throughput generation, optimization and analysis of genome-scale metabolic models by Chris Henry, et al.](https://pubmed.ncbi.nlm.nih.gov/20802497/)

## Can Prokka annotations be used for metabolic modeling?&#x20;

You can use Prokka to annotate, but we recommend using RAST for metabolic models because we use the RAST functional roles as a controlled vocabulary to derive metabolic reactions.

## **What does the KBase** [**Gapfill Metabolic Models App**](https://kbase.us/applist/apps/fba\_tools/gapfill\_metabolic\_model/release) **do?**

Draft metabolic models lack a number of essential reactions due to missing or inconsistent annotations. Some of the most common problems arise from having missing transporters (reactions that move metabolites across cell membranes) because they are difficult to annotate well. Consequently, draft models often are unable to generate biomass on media where the organism typically is capable of growing.

The KBase gapfilling process compares the set of reactions in your metabolic model to a database of all known reactions and attempts to find a minimal set of reactions that, when added to your model, will allow it to grow. The set of reactions (known as the gapfilling solution) can then be integrated into your model, creating a new model capable of growth on the media used in the gapfilling process.

The gapfilling app uses a cost function associated with each internal reaction and transporter to find a solution that uses the fewest reactions to fill all gaps, and it does this without extra knowledge about the organism’s biochemistry.

For more information on gapfilling, see the Henry et al. 2010 [ModelSEED paper](http://www.nature.com/nbt/journal/v28/n9/full/nbt.1672.html) in Nature Biotechnology.

## **How does the underlying gapfilling algorithm work (i.e., what kind of programming formulation does it use)?**

At one time, KBase used a mixed-integer linear programming (MILP) formulation in gapfilling but replaced it with simple linear programming (LP), which minimizes the sum of flux through gapfilled reactions. From extensive experience with both formulations, KBase modeling experts have found that LP solutions are just as minimal as MILP solutions but require far less time to compute. In rare cases where an LP gapfilling would not be minimal, the lower wait time to obtain and adjust a new solution is typically worth a slightly larger solution.

The LP insists on using minimal flux, which almost always corresponds with minimal reactions in a stoichiometrically consistent database. In fact, inefficient solutions were more likely to result from the former MILP formulation because KBase sometimes would cut off the solver before an optimal solution was found in order to limit run-times to 24 hours.

In gapfilling, it is important to recognize that not all reactions are created equal. For example, transporters and non-KEGG reactions are penalized, along with reactions that have missing structures or unknown deltaG. To understand all the penalties, see the Henry et al. 2010 [ModelSEED](http://www.nature.com/nbt/journal/v28/n9/full/nbt.1672.html) paper in Nature Biotechnology.

The gapfilling app always has reasons for adding the reactions it does, but those reasons admittedly are not always obvious or biologically relevant. KBase is working on an algorithm that would provide detailed explanations of why each gapfilled reaction is added; we hope to make this feature available soon.

## **What is the solver used in your Gapfill optimization?**

The Gapfill optimization uses the [SCIP solver](http://scip.zib.de/).&#x20;

We actually use two solvers in KBase. We use GLPK for most pure-linear optimizations. We use SCIP for larger more complex problems, particularly when integer variables are involved. Gapfilling is an example of a problem where we use SCIP.

## **What is “complete” media?**

\
The “Complete” media is an abstraction of what’s available in our biochemistry database. Every compound that can be transported into the extracellular compartment–or, in other words, for which a transport reaction is available–is used in the complete media. This list is built in real-time, meaning that whenever you run FBA with complete media, the available transporters are parsed from the media database–and is therefore not stored permanently in any media object in the workspace.

To find out which transport reactions are available when running FBA using Complete media, use the [KBase ModelSEED Biochemistry Database ](https://github.com/ModelSEED/ModelSEEDDatabase/tree/v1.0/Biochemistry)for a reference list of reactions and compounds or [Biochemistry Search](https://narrative.kbase.us/#biochem-search) within KBase.

To see the specific compounds that got consumed/excreted when a model was gapfilled in complete media, you can run FBA on complete media. In the ‘FBA output table’ there is a tab called “Exchange Fluxes” which gives a list of excrete/uptake compounds. You can also view the gapfilled reactions in the ‘model output table’ by choosing the “Gapfilling” tab.

## **How do I choose a media condition for gapfilling, and what is the default media used?**

“Gapfilling” refers to choosing the minimal set of reactions to add to a draft metabolic model that will enable it to produce biomass in a specified media. KBase’s gapfilling app lets you set the media condition (i.e., the metabolites available in the environment in which you want to analyze the growth of your organism). For more information, see the [Gapfilling App details page](https://kbase.us/applist/apps/fba\_tools/gapfill\_metabolic\_model/release) and the previous question.

If you leave the Media field blank, “complete” media will be used by default. Please see the next question for more details about complete media. When used on complete media, the gapfilling app is not limited by the transport reactions already available in the model and therefore invariably will add more transport reactions to the model.

In addition to the default complete media, KBase provides more than 500 media conditions you can use for gapfilling. The [Narrative Interface User Guide](../../getting-started/narrative/) describes how to add these media and other data to your Narrative. You can also [upload your own custom media condition](../../data/upload-download-guide/media.md).

Choosing minimal media for the initial gapfilling is often a good idea because it ensures that the gapfilling algorithm will add the maximal set of reactions to the genome-inferred model. This will allow the model to biosynthesize many common substrates necessary for growth—substrates that otherwise would be present in the media. The gapfilling algorithm looks for incomplete metabolic pathways and tries to make an informed guess as to which protein-encoding genes may be responsible for the missing step in the pathway. This process works best when informed by the a priori knowledge that a particular organism can grow on a defined media type (e.g., a model of _Helicobacter pylori_, an endosymbiont, might require a media containing substrates it can’t biosynthesize in vivo.) Thus, specifying a growth media is beneficial.

Note that gapfilling runs can be stacked, meaning that multiple gapfilling solutions are incorporated into the same model, one after the other. In other words, if you gapfill on Complete media first (i.e., don’t specify a media, so it defaults to Complete), gapfilling will add all reactions needed to get the model to grow assuming it can transport all compounds for which a transporter is available in the KBase biochemistry database. If you then gapfill the same (already gapfilled once) model on minimal media, the model will only add any additional reactions needed to grow on the minimal media.

If you want to gapfill on the two media independently, be careful not to overwrite your original model during your gapfilling simulations and then use the same original model in both gapfilling runs.

The [tutorial for the Microbial Metabolic Modeling and Analysis of _Shewanella oneidensis_](https://narrative.kbase.us/narrative/18302) explores the differences between two gapfilled solutions: one generated on complete media, and one generated on minimal media.

## **How can I see the compounds comprising a media used in gapfilling?**

To see the list of media compounds for a particular model, open a viewer for the model by either clicking on its name in the Data Panel or dragging it from the panel and dropping it into the main Narrative window. Select the Compounds tab and filter by “e0” (extracellular compartment). This gives you a complete list of compounds transportable by your model.

## **Which reactions were added in the gapfilling process and why were they added?**

After performing gapfilling on a metabolic model, you can sort the “Reactions” tab of the output table by the “Gapfilling” column to see which reactions were added. In order to compare the differences between the draft model and the gapfilled model, look at the directionality of the reaction in the “Equation” column of the “Reactions” tab of the output table. If the directionality is reversible in the gapfilled model, i.e. “<=>”, this means that the reaction was already in the draft model, albeit previously irreversible, and gap-filling made it reversible. However, if the reaction is irreversible e.g., “=>” or “<=”, then this means it is a new reaction that wasn’t previously present in the draft model, and has been added to the model by the gapfilling algorithm.

The primary function of gapfilling is to ensure that the model in question can produce the biomass of the organism. As gapfilling itself is a heuristic, the result of the algorithm is essentially a prediction and requires manual curation. If the addition or reversibility of a reaction is not desired, you can use the “Custom flux bounds” field to force the reaction to be zero, and re-run gap-filling to find another possible solution. For the gapfilling process, it does not necessarily matter whether a reaction was previously set to be irreversible as long as it produces biomass. However, even if it was determined that a reaction was irreversible _a priori_, the thermodynamics algorithm used to determine this is also a heuristic.

## What conventions are used for metabolic IDs, reaction IDs, etc?&#x20;

If you generate a metabolic model based on the [Build Metabolic Model App](https://kbase.us/applist/apps/fba\_tools/build\_metabolic\_model/release), the biochemistry represented is based on modelSEED. However, if you generated a model based on a published model and propagate the biochemistry into a new model based on proteome comparison data you could have a mix of ModelSEED and the native reaction and compound IDs from the published model. We recommend using the ModelSEED ontology; you can convert a mixed model using the [Integrate Imported Model into KBase Namespace App](https://narrative.kbase.us/#catalog/apps/SBMLTools/integrate\_imported\_model/beta) (_in beta_).

## **When I import a metabolic model, how do I associate it with a genome?**

Load the genome you wish to associate with a metabolic model into your Narrative. Next, when importing your metabolic model, click on the “show advanced options” link shown towards the bottom of the import metabolic model menu. When you click on this link, a new input will appear that will permit you to select the genome for your model. Refer to the [FBA Model section of the Data Upload and Download Guide](../../data/upload-download-guide/) to learn more about correctly importing and associating your model and genome.

## **When viewing a model, what do the compartment IDs mean?**

\
Compartments are the subcellular localization of compounds, enzymes, and reactions. The table below lists compartment abbreviations for microbes and plants.

Reactions and compounds belonging to each compartment are identified using compartment notation in square brackets after the five-digit reaction or compound ID (e.g., rxn00001\[c0], cpd00001\[c0]).

The integer associated with the compartment (e.g., the 0 in c0) represents the index number of the model. For a single-species model, this number will always be zero, but if individual models are merged into a community model, each sub-model will then be assigned a distinct index.

| **Compartment**           | **Microbes**   | **Plants**   |
| ------------------------- | -------------- | ------------ |
| Cytosol (c)               | ✓              | ✓            |
| Plastid (d)               |                | ✓            |
| Extracellular (e)         | ✓              | ✓            |
| Golgi apparatus (g)       |                | ✓            |
| Mitochondria (m)          |                | ✓            |
| Nucleus (n )              |                | ✓            |
| Periplasm (p)             | ✓              |              |
| Endoplasmic reticulum (r) |                | ✓            |
| Vacuole (v)               |                | ✓            |
| Cell wall (w)             |                | ✓            |
| Peroxisome (x)            |                | ✓            |

## **After merging models, why do I sometimes end up with one or two more compartments?**

When you combine models into a community model, you have two options:

1. Make a compartmentalized multi-species model where each species is contained in a separate compartment leading to the replication of compartments that you describe
2. Make a “mixed bag” model where the component models are merged non-redundantly into a single model with no additional compartments.

The first model type is better for predicting potential interactions between species. The second model type is a simpler model and at times, easier to work with. These papers and the narratives associated with these papers explain this in greater detail:

* Henry CS, Bernstein H, Weisenhorn P, Taylor RC, Lee JY, Zucker J, Song HS. Microbial Community Metabolic Modeling: A Community Data-Driven Network Reconstruction. Journal of Cellular Physiology (2016) 10.1002/jcp.25428.
* Faria JP, Khazaei T, Edirisinghe J, Weisenhorn PB, Seaver S, Conrad N, Harris N, DeJongh M, Henry CS. Constructing and Analyzing Metabolic Flux Models of Microbial Communities. Hydrocarbon and Lipid Microbiology Protocols (2016)

## **What should I know about performing metabolic modeling on plants?**

The Plant Metabolic Modeling in KBase is based on the metabolic subsystems described in the [PlantSEED](http://bioseed.mcs.anl.gov/\~seaver/FIG/seedviewer.cgi?page=PlantSEED). Because PlantSEED was focused on the primary metabolism of higher plants, performing metabolic modeling on lower plants such as bryophytes and algae is not recommended. In principal, the majority of the metabolic networks for plants will be similar. What will be different in the plant primary metabolic network between organisms the gene – reaction associations. From metabolic modeling, you can derive a prediction of the enzymes that would catalyze each of the reactions in the primary metabolic network.

## **How can I find and download all the biochemical compounds and reactions in KBase, as well as linked information such as Enzyme Commission (E.C.) Numbers?**

The biochemistry compounds and reactions can found in the [KBase ModelSEED Biochemistry Database ](https://github.com/ModelSEED/ModelSEEDDatabase/tree/v1.0/Biochemistry)for a reference list of reactions and compounds or using [Biochemistry Search](https://narrative.kbase.us/#biochem-search). This spreadsheet includes the EC numbers. You can also consult the [Enzyme database](http://enzyme.expasy.org/) to see a description of each type of characterized enzyme that has an EC number.

## **Does media in KBase include sources other than carbon (e.g., nitrogen, phosphorus, sulfur)?**

Every KBase media has all the compounds necessary for minimal growth. In most cases the significant difference among media is the carbon source, which generally dictates the media’s name (e.g., “Carbon-D-Glucose”).

## **How can I specify my own media?**

You can generate and import your own media file by specifying the biochemical compounds found in a particular growth environment. Go to  [KBase ModelSEED Biochemistry Database ](https://github.com/ModelSEED/ModelSEEDDatabase/tree/v1.0/Biochemistry)to see a list of all the biochemical compounds in KBase and find the IDs for those you wish to include in your custom media.

Media can be uploaded as a TSV (tab-separated values) or Excel file with four columns:

* Compound identifier (e.g., ModelSEED ID, KEGG ID, PubChem ID, or compound name such as “glucose”)
* Concentration (concentration of compound in mol/L)
* Min flux (minimum allowed uptake/excretion of compound)
* Max flux (maximum allowed uptake/excretion of compound)

Below is an example of a media file in TSV format. In this case, the compound IDs in the first column are ModelSEED IDs.

Note that when creating a media Excel file, the name of the worksheet that contains your media conditions must be named “MediaCompounds” or it will not upload. To rename a worksheet, find the worksheet tabs at the bottom left of the Excel file. Double-click on the default name of the spreadsheet containing your custom media and name it “MediaCompounds."

The values in the “minflux” and “maxflux” columns are absolute units that represent the range of possible fluxes for reactions that transport the media compounds into and out of the cell. A negative flux value corresponds to excretion (transport out of the cell), and a positive flux value corresponds to uptake (transport into the cell).

The combination of maximum and minimum flux will dictate whether uptake and/or excretion of a reagent is allowed. Assigning a positive number to “minflux” for a particular compound essentially forces uptake of that compound. Conversely, assigning a negative number to “maxflux” will force excretion of the compound.

If you specify a range between “minflux” and “maxflux,” then you will need to look at the list of “Exchange Fluxes” in the output after running flux balance analysis to observe what actually happened during the growth simulation.

Please see the [Media section of the Data Guide](../../data/upload-download-guide/media.md) for more information on how to configure your media file.

## **How are units of flux measured within the media?**

Minimum and maximum flux are measured in mmol per gram cell dry weight per hour.

## What is the unit of measurement for the estimated biomass from a metabolic model?

The biomass components are normalized so that a result of 1 (objective value/growth/flux through biomass reaction) is estimated to be 1 gram of dry weight of biomass.

## **How is media data structured in KBase?**

As with all KBase data types, the technical “spec” files of media data can be viewed at[ narrative.kbase.us/#spec/type/KBaseBiochem.Media](https://narrative.kbase.us/#spec/type/KBaseBiochem.Media).

From here, you can find details on the structure of media data in KBase by navigating the following path: “KBaseBiochem” → “Types”→ “Media” → “Spec file.” Scroll to the bottom of the media spec file to see the overall data structure, which should look like this:

```
typedef structure {
  media_id id;
  string name;
  source_id source_id;
  string source;
  string protocol_link;
  bool isDefined;
  bool isMinimal;
  bool isAerobic;
  string type;
  string pH_data;
  float temperature;
  string atmosphere;
  string atmosphere_addition;
  list<MediaReagent> reagents;
  list<MediaCompound> mediacompounds;
} Media;
```

## **What is the function of the .gffba file? What is the difference between the .gffba output and Flux Balance Analysis output?**

The .gffba object is generated automatically by gap filling and it holds the fluxes corresponding to the solution selected by gap filling to make your model grow in the specified environment. It is useful as a means of exploring why various reactions were added, as well as diving into the gap filling result in detail. We are working to improve the functionality of this data object.

The .gffba output and Flux Balance Analysis output are the same. It is important to understand that a gap filing simulation is a form of FBA, and as such, it generates a flux solution, which is exposing to you via the .gffba object.

## **How can I determine if my metabolic model will grow in a certain media?**

Once you have built a metabolic model, you can perform flux balance analysis ( FBA) to calculate the flow of metabolites through your model. FBA results can be used to predict the growth rate of an organism under certain conditions or the production rates for particular metabolites of interest.

To determine whether your organism grew in the media that you specified for FBA, find the Overview tab in the FBA results table. Among the summary information in this tab is the **objective value**. This value is is significant because it represents the maximum achievable flux through the biomass reaction of the metabolic model. An objective value of 0 (or something very close to 0) means that the model did not grow on the specified media.

For more information on the [Run Flux Balance Analysis](https://kbase.us/applist/apps/fba\_tools/run\_flux\_balance\_analysis/release) App.&#x20;

## **After running flux balance analysis, what does the sign of a reaction flux mean?**

A positive flux value indicates that a reaction is proceeding from left to right as written in the equation, while a negative value indicates the reaction is running from right to left.

For example, the following table shows a portion of the “Reaction fluxes” tab from the output of the [Run Flux Balance Analysis](https://kbase.us/applist/apps/fba\_tools/run\_flux\_balance\_analysis/release) App. Here, the positive flux in the “Flux” column indicates that rxn00543 is proceeding from left to right—that is, ethanol is being oxidized to acetaldehyde.

| **Reaction**  | **Name**                             | **Flux** | **Min flux (Lower bound)** | **Max flux (Upper bound)** | **Class** | **Equation**                                                                  |
| ------------- | ------------------------------------ | -------- | -------------------------- | -------------------------- | --------- | ----------------------------------------------------------------------------- |
| rxn00543\[c0] | <p>Ethanol-NAD<br>oxidoreductase</p> | 100      | <p>-100<br>(-1000) </p>    | <p>100<br>(1000) </p>      | Variable  | <p>NAD[c0] + Ethanol[c0] &#x3C;=><br>Acetaldehyde[c0] + NADH[c0] + H+[c0]</p> |

The “Min flux,” “Max flux,” and “Class” columns show that other valid FBA solutions for the model have flux values for rxn00543 that range from -100 to 100. This reaction therefore is classified as “Variable” because it can proceed in either direction.

## **What do the various reaction classifiers mean?**

Reaction classifiers are assigned when using Flux Variability Analysis, FVA. In FVA, the global objective (biomass) is fixed at its optimal value, then each reaction, iteratively, is optimized independently to find both the maximal and minimal value that is possible given that the global objective must still be reached.

* Variable – the reaction has positive maximal and negative minimal values, meaning that it can go in either direction.
* Positive variable – the reaction has a positive maximal, and a zero minimal, meaning that it can either be zero, or it can go from left to right.
* Negative variable –  the reaction has a zero maximal, and a negative minimal, meaning it can either be zero, or it can go from right to left.
* IA (InActive) – the reaction is blocked and cannot have a non-zero value.

## **Can I customize the flux boundaries for reactions in my model?**

To constrain the flux of a reaction, you can export your model, edit it, and re-import it.

Alternatively, in the case of a transport reaction, you can change the uptake of a media compound by editing the media object itself. For example, setting the maximum flux of any media compound to zero (or a small number) will prevent its uptake. This is contingent, of course, on the media itself being defined, so if you performed gapfilling on the default complete media, you will have to re-gapfill on an actual defined media object of your choice.

Also, in the [Run Flux Balance Analysis](https://kbase.us/applist/apps/fba\_tools/run\_flux\_balance\_analysis/release) App, you can change the “bounds” on a specific reaction to whatever you want using the “Custom flux bounds” field under advanced options.

Note that the help text next to the custom flux field provides an example of the proper format for setting bounds:\


* Specify a number for the lower bound (e.g. “0”)
* Insert a semicolon (no spaces!)
* Type in the reaction ID or compound ID
* Insert another semicolon
* Specify a number for the upper bound (e.g. “5”)

So to set “rxn00006” at a flux of “5,” you would set this custom bound: 5;rxn00006;5.

## **How can I edit my media or metabolic model (add or delete reactions, compounds, or biomass)?**

After you have drafted your metabolic model with the Build Metabolic Model app, you can use the [Gapfill Metabolic Model App](https://kbase.us/applist/apps/fba\_tools/gapfill\_metabolic\_model/release) to automatically fill in the gaps of necessary reactions for completing the pathway for a set of specified reactions (this can be either the biomass producing reaction or other specified pathways). You can alternatively use our [Edit Media](https://kbase.us/applist/apps/fba\_tools/edit\_media/release) or [Edit Metabolic Model](https://kbase.us/applist/apps/fba\_tools/edit\_metabolic\_model/release) Apps. This works best if the reactions you're adding at ModelSEED reactions (ID looks like rxn#####). In those cases, you can manually list several reactions to add by ID and associate genes and specify directionality. You can add completely custom reactions as well, but this is harder.

## **Why did gapfilling fail for a model containing a custom media or custom biomass reaction? What can I do about it?**

Draft metabolic models tend to have gaps by default. If you simulate FBA on a given media, you would see the objective value to be zero; means the model is not able to grow on the simulated media. In the model output viewer gapfill reactions can be seen and easy to recognize as there are no features mapped to the gapfilled reactions. There is a tool in KBase to try and find gene candidates for gapfilled reactions. If a candidate is found, this can give you more confidence that the gapfilled reaction is real. It's in beta and it's called [Find Candidate Genes for a Reaction](https://narrative.kbase.us/#catalog/apps/kb\_reaction\_gene\_finder/find\_genes\_from\_similar\_reactions/beta). Just plug in the list of gapfilled reactions and see the candidates that come out.

If the [Gapfill Metabolic Model App](https://kbase.us/applist/apps/fba\_tools/gapfill\_metabolic\_model/release) fails with custom media, first check whether the compound that you are gapfilling for is already available in the reconstructed model. (See instructions for viewing model compounds above.)

If the compound is not in the model, it may be rare or uncommon. Check [KBase ModelSEED Biochemistry Database ](https://github.com/ModelSEED/ModelSEEDDatabase/tree/v1.0/Biochemistry)or [Biochemistry Search](https://narrative.kbase.us/#biochem-search) to ensure that:

* The compound is actually available in KBase’s biochemistry collection.
* There are reactions that involve the compound in question.
* There are exchange reactions (transporters) that would enable the compound to be consumed from the media.

To help mitigate this issue, the “Gapfill Metabolic Model” app includes a field for “Source Gapfill Model” under the advanced options. You can specify a source model to supply reactions missing from the KBase database that might prevent the gapfilling from working successfully. If your biomass reaction is from an existing published model, you should import this model and use it as a source database for your gapfilling (because that model should contain all reactions needed to grow on its own biomass reaction). The source model simply supplements the KBase database, which still will be used in gapfilling.Successfully running the gapfilling app with a custom biomass reaction depends on whether the custom biomass includes compounds that can be produced given all the balanced, approved reactions in the KBase database. For now, non-standard compartments for biomass components may also be a problem.

KBase uses a  [KBase ModelSEED Biochemistry Database ](https://github.com/ModelSEED/ModelSEEDDatabase/tree/v1.0/Biochemistry)that includes all ModelSEED reactions, and some additional reactions. However, the gapfilling is restricted to a subset of the reactions in the database. First and foremost, KBase filters out imbalanced reactions from gapfilling because they cause mass leakage and a bad gapfilling solution. We also filter out several reactions that cause problems in gapfilling due to strange formulations (e.g., reactions containing lumped or undefined compounds).

## **What if my source and translated metabolic models are the same after running the “Propagate Genome-scale Model to Close Genome” App (in beta)?**

The [Propagate Model to New Genome App](https://narrative.kbase.us/#catalog/apps/fba\_tools/propagate\_model\_to\_new\_genome/beta) (in beta) builds a new metabolic model by translating the gene associations in an existing model to a new genome. This translation is conducted based on gene correspondence tables contained in a proteome comparison object generated in Step 1 of the app. A gapfilling is performed to permit the translated model to grow on a specific media. More information on the model translation step can be found on the [details page](https://narrative.kbase.us/#catalog/apps/fba\_tools/propagate\_model\_to\_new\_genome/beta).

If the translated model resulting from this app is the same as your source model, run through the following checks:

* **Make sure the reactions in the source model have genes associated with them.** If they don’t, then the source and translated models will be the same because reactions with no genes are automatically retained in the model propagation process. For this reason, it is very important to associate a genome with your model when you import it. It is equally important that the gene IDs in this associated genome match the gene IDs mapped to the reactions in your imported model **exactly**. Otherwise, the genes in the genome will not be properly mapped to the reactions in the model. This proper mapping is absolutely essential for apps such “Propagate Genome-scale Model to Close Genome” to work.
* **Look at the proteome comparison object.** How different are the genomes that are being compared? How many hits are there? If the genomes are very close, the source and translated model could end up being the same. Such a result is unlikely but not impossible.
* **Check the translated model before gapfilling.** Did you lose some reactions only to have them added back in the gapfilling process?

## **What do the “Prediction class” values mean in the output table generated by the “Simulate Growth on Phenotype Data” App?**

The [Simulate Growth on Phenotype Data](https://kbase.us/applist/apps/fba\_tools/simulate\_growth\_on\_phenotype\_data/release) App performs multiple flux balance analyses (FBA) using each media condition in a phenotype dataset and compares the results, which are listed as “Observed normalized growth” (experiments done in a laboratory) vs. “Simulated growth” (simulation of FBA on the model). You can see these results in the Phenotypes tab of the output cell.&#x20;

In the “Prediction class” column, simulated growth results against observed growth are represented in four classes:

**CP** — Correct positive (model was predicted to grow, and did)\
**CN** — Correct negative (model was predicted not to grow, and did not)\
**FP** — False positive (model was predicted to grow, but it did not)\
**FN** — False negative (model was predicted not to grow, but it did)

## What do the different colors mean in the visualization of metabolic pathways?&#x20;

Blue means that the reaction is present, white means the reaction is absent. Red means negative flux, green means positive flux. Shade represents intensity of flux. The arrows on the map do not always agree with the direction of reactions as defined in our biochemistry database, so these colors can appear confusing at times. For this reason, we are actually currently working on replacing our KEGG-based metabolic map viz with a new system using dynamically drawn maps in Escher.

## **Why did I get false negatives after simulating growth, and what can I do about it?**

False negative (FN) results from the “[Simulate Growth on Phenotype Data](https://narrative.kbase.us/#narrativestore/method/simulate\_growth\_on\_a\_phenotype\_set)” app mean that the model is not able to grow on laboratory-tested media conditions. The most likely explanation for a FN prediction is that the model is missing reactions required for viable growth in the specified media conditions (e.g., no asparagine metabolism pathway in a media where asparagine is the only carbon source). This error can be corrected by gapfilling the model on that media to add a minimal set of reactions to the model such that growth is permitted.

## Is it possible to use KBase to integrate RNA sequencing data into existing genome-scale models?&#x20;

Yes, there is an app called [Compare Flux with Expression](https://kbase.us/applist/apps/fba\_tools/compare\_flux\_with\_expression/release) that allows you to compare your GSM with RNA-seq data to identify metabolic pathways where expression and flux data agree or conflict. You can also use the [Run Flux Balance Analysis App](https://kbase.us/applist/apps/fba\_tools/run\_flux\_balance\_analysis/release) to predict fluxes using your expression data. In this approach, you pick a threshold expression level (as a percentile), and the app tries to turn off reactions associated with genes expressed below the threshold and turn on reactions associated with genes expressed above the threshold. Just load your expression data into KBase using the upload tool or by running the RNA-seq pipeline (which will make a matrix for you). Then select this matrix in the advanced parameters of the [Run Flux Balance Analysis App](https://kbase.us/applist/apps/fba\_tools/run\_flux\_balance\_analysis/release), and specify which column of the matrix you want to use to constrain your fluxes.

## What exactly is the criteria for gapfilling/ How do we know which reaction should be maximized, added, etc? Should we consider the reactions which are blocked and do gapfilling for those?

Gap filling is an optimization problem; by default, we gap fill for growth, meaning that the goal of the algorithm is to ensure that given the media provided by the user, all compounds in the biomass reaction (necessary for growth) can be produced by the model. The algorithm searches our biochemistry database and finds reactions that fill gaps that enable the production of the biomass precursors that the draft model without gap-filling can’t produce.

The algorithm tries to minimize the number of reactions that are added to the model to achieve growth since, at the moment, we don’t have a way to map the reactions being added by gap filling to genes with missing or wrong annotations in your genome. This is why gap-filling reactions don’t have gene-protein-reaction associations. If you look at the algorithm in detail in the paper mentioned above, you will see the penalty system we use for adding reactions to a model with gap-filling; for example, thermodynamic feasibility weighs heavily in deciding if a reaction is added to the model or not. Another factor can be the penalty scoring of adding a transporter vs. adding a full biosynthesis pathway if a compound is present in the media.

Reactions can be gap-filled for many reasons:

1. The genome used to build the model has missing or incorrect annotations for a given gene(s), meaning the reaction associated with the gene won’t be placed in the model.
2. Our template is missing or has incorrect mappings between gene functional roles and reactions. While we try our best to have accurate mappings in our templates, knowledge for some pathways keep evolving, EC number get re-assigned, and more specific enzyme complex roles are mapped to individual genes, etc. If you find that a reaction missing in your model should have been included, given that the gene is properly annotated in the source genome, please let us know so we can fix it in our templates.
3. There is truly unknown knowledge of how some organisms perform certain processes.
4. As mentioned above, gap filling will try to make sure all biomass precursors needed for growth are generated by the model. This biomass reaction is mostly generic/universal with some differences in cell wall biomass precursors between gram-negative and gram-positive organisms. Your organism may not have the same biomass requirements as the universal biomass formulation we use, meaning the gap-filling algorithm may gap-fill reactions to produce biomass precursors that are irrelevant to your organism.

If in the gap-filling problem, you decide to maximize the production of a different compound, for example, maximize the production of ethanol by selecting the ethanol transporter instead of the biomass reaction, the gap-filling will act in the same way. Still, this time around will only care to add reactions that fulfill this objective and address gaps in the ethanol production pathway. And important to note that gap filling may add reactions even if your organism cannot produce ethanol. The algorithm does not know the specifics of your organism, but the gap-filling results can help elucidate if this is something or organism can do. It is important to analyze the gap-filling results. Continuing with the previous example. If to produce ethanol in your organism, gap-filling fill only one gap in the pathway, that probably means there was a missing or wrong annotation in your genome, and gap-filling correctly filled the necessary gap. If, on the other hand, gap-filling fills in most of the reactions present in that pathway, it might mean that this is a metabolic capability that your organism doesn't have. Or your source genome has bad quality annotations that miss our reactions mapping completely for this pathway.

TLDR: it is very important to analyze the gap-filling results critically to understand if some reactions are truly missing or are being added to satisfy a biomass precursor that is not relevant to your organism. I also recommend you do further literature research on the subject since multiple gap-filling algorithms exist that employ different methodologies.

## Is there a tutorial, public narrative, publication, or documentation of using a high-quality, curated metabolic model to develop a new metabolic model for a genome of a different strain of the same species?

We have an app Propagate Model to New Genome which can be used to do that. The [app catalog page](https://narrative.kbase.us/#catalog/apps/fba\_tools/propagate\_model\_to\_new\_genome/release) has good documentation about using the app.

There’s a public Narrative by Chris Henry that you can view as an example here: [![](https://narrative.kbase.us/favicon.ico)KBase](https://narrative.kbase.us/narrative/13806). For context, it is part of this publication: [https://onlinelibrary.wiley.com/doi/full/10.1002/jcp.25428](https://onlinelibrary.wiley.com/doi/full/10.1002/jcp.25428).

In addition, check out this protocol paper: [https://link.springer.com/protocol/10.1007/978-1-0716-1585-0\_13](https://link.springer.com/protocol/10.1007/978-1-0716-1585-0\_13)\


#### We welcome your [feedback](https://www.kbase.us/support) on the information provided in this FAQ. If you have a question about the metabolic modeling tools and data in KBase that is not answered here, or the answer provided didn’t work for you, please [contact us](https://www.kbase.us/support).

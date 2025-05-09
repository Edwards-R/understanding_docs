>However, our example specifically mentions the interpretation to be in the GB context only. Why is this, and what are the implications for maintaining a globally-applicable taxon list?

# Interpretation Regions
Previously, we demonstrated the combination of type name, type concept, and interpretation. However, in that example it was specifically mentioned that the interpretation only applied to Great Britain. Given that a fundamental attribute of the Linnaean taxonomic system is its global capacity, what purpose does restricting interpretations to regional scope serve? What is the design issue that regionality solves, and can this regionality be removed to create a global system once more?

## Concept vs reality in the face of cryptic taxa
> Refresher of previous page on Bombus lucorum.
> - start with the type names
> - then add the type concepts
> - now run the GB scenario
> - summarise the GB scenario
> - now run the Swedish scenario
> - put the two together, sorted by time
> - summarise that the two different regions have different interpretations at different points of time

Whilst taxonomy may be global, that global nature is only in concept. In practice, various regions may have differening applications of taxonomy to match their own practical needs. The most obvious example of this regionality is when a region discovers that they harbour a cryptic complex of well-established taxa. To examine *why* regionality exists, as well as the need to accurately handle regionality in order to maximise precision, the next section will walk through a real life example of the discovery of a cryptic taxon. 

## Establishing the participating type components
The participating type names in this exercise are:

|Name|Name Author|Name Year|
|---|:-:|:-:|
|Bombus lucorum|Linnaeus|1761|
|Bombus cryptarum|Fabricius|1775|
|Bombus magnus|Vogt|1911|

Expanding this table allows us to reference the type concept version for each taxon. Note that this is approximated, as precise type concept versioning requires the attention of an experienced taxonomist.

|Name|Author|Year|Concept Author|Concept Year|
|:-:|:-:|:-:|:-:|:-:|
|Bombus lucorum|Linnaeus|1761|Latreille|1802|
|Bombus cryptarum|Fabricius|1775|Latreille|1802|
|Bombus magnus|Vogt|1911|Vogt|1911|

## A quick note on perfection (and the lack of it)
When establishing a history of the interpretations of any taxon, it is likely that complex situations will emerge. It is also possible that the pertinent information will simply have been lost to time and no-one living remembers what was done and when. For the purpose of this explanation, interpretations given in examples will be simplified versions of reality, so as to not require multiple taxonomic papers to be written (and then read) for each example given.

## The history of interpretation in Great Britain (and Ireland)
Our (slightly hyopthetical) example starts with the known presence of *Bombus lucorum* (Linnaeus 1761), concept version Latreille 1802.

|Attribute|Value|
|:--|--:|
|Name|*Bombus lucorum*|
|Name author|Linnaeus|
|Name year|1761|
|Concept author|Latreille|
|Concept year|1802|

As the concept version is by Latreille, the initial interpretation for this concept also belongs to Latreille:

|Attribute|Value|
|:--|--:|
|Name|*Bombus lucorum*|
|Name author|Linnaeus|
|Name year|1761|
|Concept author|Latreille|
|Concept year|1802|
|Interpretation author|Latreille|
|Interpretation year|1802|

### Discovery of a cryptic complex
In 2008, Murray et al positively identified a cryptic complex within the Latreille 1802 interpretation of *Bombus lucorum*. This complex included the aforementioned *Bombus lucorum*, but also *Bombus magnus* and *Bombus cryptarum*.

|Attribute|Value|
|:--|--:|
|Name|*Bombus magnus*|
|Name author|Vogt|
|Name year|1911|
|Concept author|Vogt|
|Concept year|1911|

|Attribute|Value|
|:--|--:|
|Name|*Bombus cryptarum*|
|Name author|Fabricius|
|Name year|1775|
|Concept author|Fabricius|
|Concept year|1775|

The three taxonomic concepts (*B. lucorum*, *B. magnus*, & *B. cryptarum*) were, in 2008, well established and in frequent usage. There is therefore a problem: information of *Bombus lucorum*, interpretated according to Latreille in 1802, *from the region of Great Britain* has been found to not correspond or obey the global type concept declared by Latreille in 1802. The situation in Great Britain has reached nomenclatural divergence, yet the wider world is not in nomenclatural divergence.

To solve this, we need to use regionally isolated interpretations to refer to the globally applicable concept versions. Here, the new interpretation results from Murray et al in 2008, providing the following interpretations:

|Attribute|Value|
|:--|--:|
|Name|*Bombus lucorum*|
|Name author|Linnaeus|
|Name year|1761|
|Concept author|Latreille|
|Concept year|1802|
|Interpretation author|Murray et al|
|Interpretation year|2008|

|Attribute|Value|
|:--|--:|
|Name|*Bombus magnus*|
|Name author|Vogt|
|Name year|1911|
|Concept author|Vogt|
|Concept year|1911|
|Interpretation author|Murray et al|
|Interpretation year|2008|

|Attribute|Value|
|:--|--:|
|Name|*Bombus cryptarum*|
|Name author|Fabricius|
|Name year|1775|
|Concept author|Fabricius|
|Concept year|1775|
|Interpretation author|Murray et al|
|Interpretation year|2008|
0
>> stuuuufff

### Austria
Following the work of Murray et al, Bossert et al (2016) performed genetic analysis of *Bombus lucorum* in Austria. Their conclusion supported the findings of Murray et al, coming to the conclusion that what was regarded as *B. lucorum* in Austria was a mixture of *B. lucorum* and *B. cryptarum*. *B. magnus* was not present in any of the samples.

https://pubmed.ncbi.nlm.nih.gov/31966158/

### Previous works
As mentioned, we will be cutting short the prior history of the taxa here in order to focus on the regional variation. Whilst each region has their own lead-up to the separation of *B. lucorum*, *B. cryptarum*, and *B. magnus*, that information is not relevant to the immediate lesson.

## What happens now
From our example, we can now construct a set of interpretations for each region. These interpretations are as follows:

### UK & IE
|Type Name|Type Author|Type Year|Type Version Author|Type Version Year|Type Version Number|
|:-:|:-:|:-:|:-:|:-:|:-:|
|*Bombus lucorum*|Linnaeus|1761|Linnaeus|1761|1|
|*Bombus lucorum*|Linnaeus|1761|Murray et al|2008|1|
|*Bombus cryptarum*|Linnaeus|1761|Murray et al|2008|1|
|*Bombus magnus*|Linnaeus|1761|Murray et al|2008|1|

### Austria
|Type Name|Type Author|Type Year|Type Version Author|Type Version Year|Type Version Number|
|:-:|:-:|:-:|:-:|:-:|:-:|
|*Bombus lucorum*|Linnaeus|1761|Linnaeus|1761|1|
|*Bombus lucorum*|Linnaeus|1761|Bossert et al|2016|1|
|*Bombus cryptarum*|Linnaeus|1761|Bossert et al|2016|1|
|*Bombus magnus*|Linnaeus|1761|Bossert et al|2016|1|

### Side-by-side analysis
> Side-by-side timeline, with the type author & year, plus TVN, removed (can just look up to the previous table if confused) and replace with `A` for Austria and `B` for UK/IE. The resulting confusion is why the only practical solution is to subdivide responsibility. This is far too confusing to be practically useful in one unified block.

#### 1761
|Region|Name|TV Author|TV Year|
|:-:|---|---|:-:|
|A|*Bombus lucorum*|Linnaeus|1761|
|B|*Bombus lucorum*|Linnaeus|1761|

#### 2008
|Region|Name|TV Author|TV Year|
|:-:|---|---|:-:|
|A|*Bombus lucorum*|Linnaeus|1761|
|B|*Bombus lucorum*|Linnaeus|1761|
|B|*Bombus lucorum*|Murray et al|2008|
|B|*Bombus cryptarum*|Murray et al|2008|
|B|*Bombus magnus*|Murray et al|2008|

#### 2016
|Region|Name|TV Author|TV Year|
|:-:|---|---|:-:|
|A|*Bombus lucorum*|Linnaeus|1761|
|A|*Bombus lucorum*|Bossert et al|2016|
|A|*Bombus cryptarum*|Bossert et al|2016|
|A|*Bombus magnus*|Bossert et al|2016|
|B|*Bombus lucorum*|Linnaeus|1761|
|B|*Bombus lucorum*|Murray et al|2008|
|B|*Bombus cryptarum*|Murray et al|2008|
|B|*Bombus magnus*|Murray et al|2008|
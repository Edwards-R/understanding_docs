# Understandings - A way to solve long term nomenclatural and taxonomic instability in data

Understandings are an extension, with very slight modification, to the existing biological nomenclatural structure. The purpose of Understandings is to ensure complete type adherence in stored and un-managed data sets with the most minimal of efforts. Such a task is accomplished by the implementation of well-established relational data design patterns.

> There is only ever one correct specimen of a given taxon: the original type specimen. The rest is approximation.

## Problems in data
In 2008, [the taxon *Bombus lucorum* was split in Great Britain](https://www.semanticscholar.org/paper/Cryptic-species-diversity-in-a-widespread-bumble-Murray-Fitzpatrick/d038a049538362088065e9d493e446d041402747). This change was not surprising to many experts in the identification of the taxon and had indeed been proposed multiple times previously. It was, however, the first experiment to *conclusively* demonstrate the separation. The short version of this event is that Murray et al demonstrated that the material identified as *Bombus lucorum* in Great Britain and Ireland *also* contained *Bombus magnus* and *Bombus cryptarum*. As a result, every single record of *Bombus lucorum* prior to this work requires redetermination using genetic or chemical analysis to establish whether or not it truly is *Bombus lucorum*. The list of affected works include:

- All records submitted to the various biological recording schemes
- All scientific papers that reference *Bombus lucorum*
- All museum collections that include specimens of *Bombus lucorum*
- All private collections that include specimens of *Bombus lucorum*
- All taxon experts who are creating records and specimens of *Bombus lucorum*

Each and every single one of these items must, under the extant taxonomic/nomenclatural system, be manually modified to reflect the now discovered uncertainty. Such a level of manual modification is an utterly impractical task and, as of 2024 when this passage was first drafted, has not happened. Nor is it ever expected to happen.

## Further applicable situations
The short list of situations where there are problems is 'almost every change'. Taxon splits, merges, name changes, all cause instability to data. In particular, splits are particularly problematic for data. Understandings were developed on the aculeate hymenoptera of Great Britain, Ireland, and the Channel Islands. This is a group which has seen substantial interest over the past 20 years due to the availability of genetic sequencing and interest in pollination. Understandings have resolved every single taxonomic modification with the maximum of clarity, even in situations which have plagued the discipline for decades.

### Understandings and type modification
Understandings are also of significant use when a type requires a new specimen to be selected. The selection of a new type specimen - traditionally called a *lectotype* - is a risky process. There is always a chance that a mistake will be made in this process, which is why the process is so costly and time consuming. By creating a new Understanding for interpretations based on this lectotype, any potential damage to data is contained. If an error is discovered in a lectotype, all affected data is automatically separate from the unaffected.

### Why not use 'sensu lato'
The immediate answer from the extant nomenclatural/taxonomic structure is that all existing data be immediately considered 'sensu lato'. This idea is all very well until the repercussions of such an action are considered. Firstly, and perhaps most importantly, such an action is tantamount to changing the species name. There exist records of *Bombus lucorum*. If these are to be *considered* to be read as *Bombus lucorum sensu lato*, then there can never ever again be a use of the name *Bombus lucorum*. Re-using the name creates an environment where the intended meaning cannot be known. Using time as a proxy is a highly dangerous idea, as even in 2024 there are still people resurrecting old interpretations of taxa - including this change.

The second reason for rejecting the 'sensu' system is that the system can only work once. *Andrena scotica* and *Andrena trimmerana* are two taxa which have been conflated for many decades. Recently, there have been multiple works which attempted to separate the taxa and provide a guide to identification that covers the entire range of Great Britain. To keep the situation *reasonably* simple, only the three latest nomenclatural entries for what is now known as *Andrena scotica* will be used. The three entries of relevance are:

- *Andrena scotica* in the sense of Perkins, 1916
- *Andrena scotica* in the sense of Else & Edwards, 2018
- *Andrena scotica* in the sense of Wood et al, 2022

The summarised history is that Else & Edwards, working with Wood et al in 2018, identified that what Perkins called *Andrena scotica* was a mixture of what they called *Andrena scotica* and *Andrena trimmerana*. Accordingly, all extant data of *Andrena scotica* must be interpreted as *Andrena scotica* sensu lato. Any determinations using this new guidance must be written as *Andrena scotica* sensu stricto to prevent them from being lumped in with *Andrena scotica* sensu lato.

However, the group working on this problem was not convinced that they had, in fact, reached the correct conclusion. More material was sought and analysed, leading to the work by Wood et al in 2022. This work demonstrated that the previous conclusion which was thought to be a reliable means of separating *Andrena scotica* and *Andrena trimmerana* was not at all reliable. Accordingly, all material of *Andrena scotica* sensu stricto was, once again, to be considered an aggregate.

According to the 'sensu' nomenclature system, then the name for this is *Andrena scotica* sensu stricto sensu lato. Any other combination, derivation, or alteration of sensu nomenclature system results in significant widespread confusion as to how to interpret the given results. Such a confusing name highlights the lack of power in daisy-chaining 'sensu' epithets to provide a clean, understandable and informative approach to nomenclature.

### Numerical sequences
An alternative to the utilisation of epithets is to utilise numerical identifiers. Each 'individual' name is given a numerical identifier, which is then promoted for use instead of the name. Such a system is considered highly inferior because

- It replaces the name that taxonomists and biologists are used to
- Humans are terrible at remembering random sequences of numbers
- It doesn't fix anything, just hides the problem under another layer of obfuscation

Multiple such numerical systems exist. The UK has the Biological Record Centre system and the UK Species Inventory. None of these see significant numerical use by users.

## Introducing Understandings
Understandings are a means to sidestep the usage of 'sensu' epithets, as well as the need to use numerical representations of a name. An Understanding represents a particular interpretation of a name. For example, the three interpretations of *Andrena scotica* given above are Understandings. These are reprinted below:

- *Andrena scotica* in the sense of Perkins, 1916
- *Andrena scotica* in the sense of Else & Edwards, 2018
- *Andrena scotica* in the sense of Wood et al, 2022

The ownership of the sense, e.g. 'Perkins, 1916', must refer to a published body of work that establishes the context of the understanding. In this way, users of Understandings can refer directly to the scientific literature that establishes that particular interpretation.

### Abbreviating Understandings
Understandings are very long to write out in full. Accordingly, an Understanding may be written in short form. The 'default' method of doing so is called the 'iso' - pronounced 'eye-so' - method:

- *Andrena scotica*: iso. Perkins: 1916
- *Andrena scotica*: iso. Else & Edwards: 2018
- *Andrena scotica*: iso. Wood et al: 2022

The iso format satisfies every fulfillable requirement encountered so far. Specifically:

- Be easily distinguished from a reference to a type
- Not overlap any extant system formatting
- Be easily readable by a human
- Be easily comprehensible by a human
- Be easily parsed by a computer
- Be *very* close to unique
- Be self-contained as much as possible

### What makes an Understanding
An Understanding represents an interpretation of a type. In no way, shape, or form can an Understanding replace a type. Accordingly, an Understanding is created when an interpretation of a type changes. By far the best way to explain the basics of where and when Understandings are created is with an example. This example can be found in the next section, once a few more basics of how Understandings function have been covered.

### Relating an Understanding back to types
In order to know what type, or types, are contained within an Understanding, an Understanding must be *resolved*. Resolving an Understanding removes the ability of Understandings to adjust across time, and as such should be performed at point of use rather than point of storage. Resolving an Understanding can be done in two ways:

- By using the knowledge of the resolver
- By using a system designed to handle and manage and resolve Understandings

It is recommended to use the latter, as it removes yet another 'need to know in order to know' facet of nomenclature. What such a system entails will be discussed later in the technical documentation.

### Understandings may be regional
Unlike types, a dictionary of Understandings may be limited in geographic and taxonomic scope to suit the needs of the user base. As such, multiple different, overlapping dictionaries of Understandings may co-exist without conflict. Co-existence is possible because each Understanding resolves back to types, giving a common attribute which may be used for comparison. It is up to the user to determine which dictionaries they deem useful, accurate, or applicable.

There is no suggested minimum or maximum absolute size to these dictionaries. The best guidance is to make the lists as widely applicable as possible, whilst keeping them flexible enough to be useful. Multiple small dictionaries require more management, whilst monolithic dictionaries lose the flexibility that they require.

As an example, many invertebrate terrestrial taxa will likely operate best at country level. Larger animals, in particular those with highly mobile behaviour, will likely operate better at larger scales, sometimes even global.

## *Bombus lucorum* Understandings example

### Brief history
*Bombus lucorum* is *the* poster child for Understandings, as the name '*Bombus lucorum*' has been used worldwide for a wide range of different 'things' at different times and in different places. The name itself stems from *Apis lucorum*, described by Linnaeus in 1761. The genus *Bombus* was created in by Latreille in 1802. The type specimen itself has been changed at least once, with the current specimen being determined by M.C. Day in 1977 (correctly, though still somewhat confusingly, labelled as *Apis lucorum Linnaeus*).

Alongside these broad historic actions, there have been a plethora of other manipulations. What we current know of as *Bombus lucorum* has had a long and rich tradition of being confused and lumped with various other taxa. The story of the modern interpretation of *Bombus lucorum* starts with the splitting of the 1896 Saunders interpretation of *Bombus terrestris* by Sladen in 1912, giving us *B. terrestris* and *B. lucorum*. Rumblings of a cryptic complex within *B. lucorum* abounded for many years, though never reaching enough of a concensus to provide a definitive separation.

With the advent and proliferation of genetic sequencing, the cryptic complex was finally broken into. Various regions accepted the complex at various times, as the evidence for how widespread the cryptic complex reached took time to assemble. In the BWARS sphere of responsibility, the critical work which separated the cryptic complex surrounding *B. lucorum* was performed by Murray et al in 2008. This work conclusively demonstrated the presence of *B. lucorum*, *B. magnus*, and *B. cryptarum* in the UK and Ireland. A further species was hinted at during analysis, and still rumbles around to date, but no work has yet managed to fully separate this potential.

The last action, as of the time of writing, was the 2011 discovery by Andreas & Horst that what was termed *Bombus lucorum* in China is a cryptic complex containing *B. lucorum* and *B. minshanicola*.

### BWARS Understandings

#### Initial: Saunders, 1896
The first interpretation of *Bombus lucorum* in relevance here is the interpretation of *Bombus terrestris* by Saunders in 1896:

|Understanding|Resolved interpretation|
|---|---|
|Bombus terrestris: iso. Saunders: 1896|Bombus terrestris: iso. Saunders: 1896|

#### Change 1: Sladen, 1912
*Bombus terrestris: iso. Saunders: 1896* was split by Sladen in 1912, giving us *B. lucorum* and *B. terrestris*. Material identified using Saunders's interpretation is therefore considered to be of the aggregate of these two taxa, unless the specimen is otherwise redetermined.

|Understanding|Resolved interpretation|
|---|---|
|Bombus terrestris: iso. Saunders: 1896|Bombus terrestris agg: iso. Sladen: 1912|
|Bombus terrestris: iso. Sladen: 1912|Bombus terrestris: iso. Sladen: 1912|
|Bombus lucorum: iso. Sladen: 1912|Bombus lucorum: iso. Sladen: 1912|
|Bombus terrestris agg: iso. Sladen: 1912|Bombus terrestris agg: iso. Sladen: 1912|

#### Change 2: Murray et al, 2008
Murray et al's paper splits *B. lucorum: iso. Sladen: 1912* up, separating the cryptic complex within.

|Understanding|Resolved interpretation|
|---|---|
|Bombus terrestris: iso. Saunders: 1896|Bombus terrestris agg: iso. Sladen: 1912|
|Bombus terrestris: iso. Sladen: 1912|Bombus terrestris: iso. Sladen: 1912|
|Bombus lucorum: iso. Sladen: 1912|Bombus lucorum agg: iso. Murray et al: 2008|
|Bombus terrestris agg: iso. Sladen: 1912|Bombus terrestris agg: iso. Sladen: 1912|
|Bombus lucorum: iso. Murray et al: 2008|Bombus lucorum: iso. Murray et al: 2008|
|Bombus cryptarum: iso. Murray et al: 2008|Bombus cryptarum: iso. Murray et al: 2008|
|Bombus magnus: iso. Murray et al: 2008|Bombus magnus: iso. Murray et al: 2008|
|Bombus lucorum agg: iso. Murray et al: 2008|Bombus lucorum agg: iso. Murray et al: 2008|

#### Non-change 3: Andreas & Horst, 2011
Critically, this work *does not* affect the BWARS Understandings. This is because the work does not address the geographic area which BWARS covers. Accordingly, the interpretations within the area which BWARS covers are not changed at all, as the resolved interpretations are all considered to resolve back to their respective type.

### Resolved Understandings and types
Examining the types which each Understanding relates to paints another picture. Remember that an aggregate is resolved by resolving its components, which is why *Bombus terrestris agg: iso. Sladen: 1912* changes multiple times.

>NB: This section only handles resolved Understandings, as all Understandings **must** be resolved before being related to a type

#### Initial: Saunders, 1896
|Understanding|Type(s)|
|---|---|
|Bombus terrestris: iso. Saunders: 1896|Bombus terrestris Linnaeus 1758|

#### Change 1: Sladen, 1912
|Understanding|Type(s)|
|---|---|
|Bombus terrestris: iso. Sladen: 1912|Bombus terrestris Linnaeus 1758|
|Bombus lucorum: iso. Sladen: 1912|Bombus lucorum Linnaeus 1761|
|Bombus terrestris agg: iso. Sladen: 1912|Bombus terrestris Linnaeus 1758|
||Bombus lucorum Linnaeus 1761|

#### Change 2: Murray et al, 2008
|Understanding|Type(s)|
|---|---|
|Bombus terrestris: iso. Sladen: 1912|*Bombus terrestris* Linnaeus 1758|
|Bombus terrestris agg: iso. Sladen: 1912|*Bombus terrestris* Linnaeus 1758|
||*Bombus lucorum* Linnaeus 1761|
||*Bombus cryptarum* Fabricius 1775|
||*Bombus magnus* Vogt 1911|
|Bombus lucorum: iso. Murray et al: 2008|*Bombus lucorum* Linnaeus 1761|
|Bombus cryptarum: iso. Murray et al: 2008|*Bombus cryptarum* Fabricius 1775|
|Bombus magnus: iso. Murray et al: 2008|*Bombus magnus* Vogt 1911|
|Bombus lucorum agg: iso. Murray et al: 2008|*Bombus lucorum* Linnaeus 1761|
||*Bombus cryptarum* Fabricius 1775|
||*Bombus magnus* Vogt 1911|


## Which Understanding should I use?
A very frequent question from those new to Understandings is 'which one should I use?'. The most robust means of deciding which Understanding is applicable is to examine the literature that the given Understandings reference to see if it matches up with your or the work you are using's interpretation.

**Do** ***not*** **default to the most recent Understanding**

The most helpful method of introducing Understandings into a taxonomic group is to provide inserts for popular identification keys, denoting which Understandings are used in that work. The Understanding used by an identification key is unable to change in a way that will cause damage and there is minimal risk of loss of accuracy. Understandings are designed to be resilient in this exact use case and may be used with confidence.

If an identification key is designed so that the region it covers is contained within one Understanding dictionary, it may use Understandings directly within.

## Stablility of Understandings
Understandings have been in development since 2014-ish, with what could be recognised as the current system emerging circa 2018. The UK Bees Wasps and Ants Recording Society (BWARS) has been using Understandings for since 2018, with success. There have been a few issues that bear mention here, though the setting up and running of an Understandings system is not the focus of this work. Firstly, the predominant source of annoyance stems from being over-eager to provide a new, modern, Understanding to replace a very old interpretation.

## An Engineer's explanation
The following section lays out the logical proof of why Understandings are required to prevent the deterioration of nomenclature over time. The explanation relies on fundamental rules of logical data structures, formalised by E.F. Codd. In particular, the rule that each individual object requires a unique identifier to prevent confusion. A taxonomically-oriented explanation requires a dedicated work, as there are far more complications and rough edges to avoid.

### 2NF to 3NF
The current way of handling nomenclature is second normal form. The current system focuses on the structuring of the reference objects and completely misses the fact that references to those objects are just that - *references* - and not the objects themselves. In true textbook manner, the result is a one-to-many to one-to-many (1-*N*:1-*N*) relationship. The solution is, again, textbook, and involves the creation of the missing component to turn a potential many to many into two one to one-to-many (1:1-*N*) relationships.

### Composite keys to avoid serials or hashes
Primary keys are designed as a composite of the information presented (parent/name/author/year/count), with count existing as a serial for the purpose of a deadlock-breaker. Composite keys are specifically selected here as the target audience tends to be fragmented and disparate, with a generally low awareness and interest in managing data systems. The information in the composite key, other than 'count', are all (to some degree) familiar to the target audience, increasing the probability of correct usage.

The deadlock-breaker has not yet been used. Situations where it *would* need to be used as explicitly disallowed by the bodies which govern nomenclature for the various biological groups. However, people in these groups have repeatedly broken their own guidance in the not-so-distant past, resulting in some of the worst nomenclatural confusion. A system should not be judged based on how well it can handle regular operations, but on how well it can handle *irregular* operations. The `count` is the solution for what to do if someone *really* breaks the nomenclature rules, ensuring that Understandings will continue to operate.

### Reading Understandings
Understandings are designed to be machine readable via regex.

#### Space-agnostic regex
`^([^:]+): {0,1}iso. {0,1}([^:]+): {0,1}(.+)`

|Capture group|Contents|
|:---:|:---:|
|1|Name|
|2|Author|
|3|Year|

## Summary
Understandings are a much needed method of providing nomenclatural stability in biological taxonomic data storage, with a proven track record of use. 
# Understandings: An upgraded system for biological nomenclature

## Abstract
Understandings are an upgraded system for biological nomenclature, backed by the existing type system. Understandings solve, as much as is possible, multiple long-standing issues in biological nomenclature. The primary solved common use case regards the potential for a name to disassociate from its type, which can no longer happen when using Understandings. Overall, Understandings drastically improve the to-type precision of nomenclature whilst remaining suitable for every-day use.

## Introduction
A fundamental aspect of taxonomy, and nomenclature, is maintaining the linkage between the type's name (what it is called) against the type concept (what that type represents). However, due to the design of the above systems, there exists the potential for uses of the type name to diverge from the type concept under regular operations. The nomenclatural divergence can be caused by taxonomic modifications, which must be applied universally, or by regional modifications, which are not applied universally. Both scenarios can present a result in which there exists data under a type's name which no longer matches the type concept.

Due to the nature of their existence, nomenclatural divergences are far more common in less stable areas of taxonomy than in stable regions. The advent of genetic sequencing in particular has caused many nomenclatural divergences to occur, resulting in significant amounts of incorrect data. However, the causing of nomenclatural divergences is not an error produced by improper usage of taxonomy, but an inherent flaw in the design and utilisation of the taxonomic system. The type concept must be able to evolve, in order for taxonomy to function and adjust to our changing understanding of the world around us. Accordingly, the taxonomic system must be updated to remove the underlying flaw. This means that a type concept, which is the core feature of our taxonomic system, is *versioned* - albeit currently invisibly as no aspect of the type exists to perform version control of the type concept.

Similarly to taxonomy, nomenclatural divergences become more common in regions of the world where the biology is not well understood. This grouping of divergences are not strictly the result of taxonomy, as they only apply to a limited geographic region. These divergences impact taxonomy in the same manner, however, causing a break between a type's name and the type concept. As an example, what was called *Bombus lucorum* in the United Kingdom and Ireland was found to be a mixture of three species: *Bombus lucorum*, *cryptarum*, and *magnus*. These other taxa were already recognised and well established in other regions, meaning that this split is not a *taxonomic* action, but exists in some other space. This 'other space' is best presented from the point of view of users other than taxonomists. The vast majority of users of the taxonomic system by volume do not interact with types but with derivatives, such as keys. These keys are, in the best scenario, derived directly from types - though this is an infrequent event in many disciplines. These derivations, across the spectrum of users, are *interpretations* of the type concept.

All uses of nomenclature, other than the singular use of the name at the point of declaration, are therefore indirect, having gone through *versioning* and *interpretation* before their use by the eventual end-user. Whilst it will be neccessary to implement version control of types themselves, this will almost certainly be a long and drawn-out process. The relevant nomenclatural codes and institutions will need to weigh in on the matter, deliberate and debate the idea etc before decisions can be made. 

> Since this will take so long, require multiple hearings etc, we need an answer that will work here, now, *and* not interfere with the code. The answer are Understandings.
>
> Also, Understandings would need to be made even if the ICZN etc did implement version control of types. We need two layers of version control - one for the *versioned* layer, and one for the *interpreted* layer. Understandings address the *interpreted* layer, but as the *interpreted* layer comes after the *versioned* layer, an Understanding can safely act as a proxy for the *versioned* layer. The fact that the codes and types themselves do not need to be changed or consulted is an added bonus.

### Introducing Understandings
"Understandings" and their associated system address the issue of nomenclatural divergence by using time proven relational database design patterns to differentiate between multiple interpretations of the same taxonomic name in a standardised, non-taxon-specific manner. Understandings also do not intervene in the current taxonomic processes at all, as they are applied to the interpretative layer rather than the taxonomic layer.
 
An Understanding refers to a particular interpretation of an application of a type. The Understandings system then provides rules and guidance on how Understandings are managed, in order to maintain their accuracy to types. Within an Understanding system, any member Understanding may be interrogated to find out which currently valid types are contained within that Understanding. As information and knowledge surrounding taxa changes, the Understanding system ensures that nomenclatural changes are applied to member Understandings with the least amount of effort and intervention possible. It should be noted that there are many situations where it will take the redetermination of a specimen (or voucher of a specimen) in order to arrive at a modern single-type interpretation. In such situations, the Understandings system will return the smallest possible collection of potential member types represented by the Understanding.

The core idea behind Understandings has been in use for many years, particularly in situations where taxonomists must differentiate between multiple interpretations of the same taxon. For example, a taxonomist may talk about '*X sensu author*'(sense of) or '*X auct nec*' (of other authors). These are all variations on the theme of finding a way to talk about multiple interpretations of the same work. Understandings are a codified version of the same idea, with added functionality to ensure longevity and maintain the greatest taxonomic precision possible.

### How to write Understandings
Understandings come with a default method of being written, though it is anticipated that other formats will develop as more users test the system and identify deficiencies. The default format is called the 'iso format', short for 'In the Sense Of'. Written down, a iso-format Understanding is composed of: `Name: iso. Author: Year: Version`. The author and year refer to the interpretation being referenced. When read aloud, it is often useful to say the full text 'in the sense of' rather than the abbreviation. Doing so will allow people who are not familiar with Understandings, yet are familiar with taxonomy, to fully understand the intent. For example, `Andrena scottica: iso. Else & Edwards: 2018` can be read as 'Andrena scottica in the sense of Else & Edwards, 2018'.

The name can be a singular entry e.g. `Bombus` or a binomial e.g. `Bombus lucorum`. The most common use of Understandings in the UK Bees, Wasps and Ants Recording Scheme's implementation of Understandings, by far, are binomial Understandings e.g. `Bombus lucorum: iso. Murray et al: 2008`.

### Understandings and types
The composition of a type is formalised when considered as part of the Understandings system. The components are divided into three portions:

* The name, author, and year of declaration of the type. This forms the 'identifier' for the type  
* A physical specimen, as well as materials derived from that individual specimen e.g. genetic barcode, whole genome sequence  
* A description which establishes the limits of the taxonomic region claimed by the taxon.

Of these parts, the identifier (name, author, and year) may not be changed. The other two parts may be changed, generating a new Understanding when they are. The strict declaration of these aspects, and their handling, is central to the the core of the Understandings system's background. Notably, the separation of the components enables the safe declaration of a replacement type specimen. All material identified based on a replacement type specimen will be immediately distinguishable from any other type specimen. Should an error be made in the assignment of a replacement type specimen, the impact of that error will be minimised. Material identified according to the erroneous designation will be immediately apparent, whilst material identified not using the erroneous designation will not be affected at all.  
The ability to safely declare a new type specimen, whilst safeguarding extant data, has been specifically tested in the Understandings system. The target use cases are:

* types where the type specimen has been lost entirely  
* types where the type specimen has degraded to the point of non-functionality  
* types where the type specimen is non-existent  
* situations where the types descriptions are unclear, overlapping, or unknown

These are all critical use cases found in aculeate hymenopteran taxonomy, where the current system's lack of ability to handle error safely is causing taxonomists to hesitate in conducting broad-scale modernisation of their taxonomy. The publication of 403 new species using 'minimalist revision and description' methods by [Sharkey et al. in 2021](https://zookeys.pensoft.net/article/55600/) raised considerable tensions within the taxonomic community. As an umbrella response, Zamani et al.'s publication '[DNA barcodes on their own are not enough to describe a species](https://resjournals.onlinelibrary.wiley.com/doi/full/10.1111/syen.12538)' covers the critical points in regards to the Understandings system. Notably, Zamani et al. raise the issues of the potential for the creation of a 'parallel' taxonomic system, and the delay that accurate databasing of new taxa creates.

The Understandings system provides a solution to this discussion by enabling users to make the large-scale declarations that Sharkey et al. require, whilst maintaining and protecting existing data as required by Zamani et al.. In addition, the Understandings system provides this extra capability whilst maintaining strict adherence to the existing taxonomic system, without disrupting the nomenclatural codes. By doing so, Understandings protect and elevate the type-based system, preventing a schism from occurring, whilst enabling flexibility in the application of taxonomy.

## The Rant
Unawareness of nomenclatural divergence, and the problems it causes, is especially notable amongst users who operate primarily with small, predominantly private, collections of physical specimens in reachable drawers. To the user with access to the physical specimens, a nomenclatural divergence is a simple problem to solve - provided that they have the requisite knowledge. The informed user can reach into the drawer, pick out the specimen, and perform re-determination. They then add a label to the specimen and place the specimen back, safe in the knowledge that *they* know what the answer is. 

In contrast, those who operate primarily either on recorded datasets of 10,000+ unique records, or collections intended for use by more than one person are more likely to be aware of the issues resulting from nomenclatural divergence. For the user of data, the entire redetermination process is hidden behind multiple layers of abstraction. There is currently no way to perform the 're-determine and label' process in a digital environment outside of individually correcting each existing usage of that piece of data - an absolutely impossible task. To complete such a task, one would need to scratch out and re-write every single use of a given name in every book, paper, journal, record card, Excel sheet, database etc etc.

For users of a collection who do *not* maintain a fanatical devotion to maintaining up-to-date knowledge of the arguments of taxonomists, especially people new to the discipline, they too are left in the dark by nomenclatural divergences. When presented with information - be it in physical form e.g. a collection, or in digital form e.g. a database, these users face the same inherent problem as the taxonomist: Is this nomenclature current? Far more frequently than not, these users are not the progenitors of any of the data they consume, which means that they must go through the entire process of learning about every single nomenclatural modification, frequently well over 100 years worth, before they can *start* on utilising the data safely.

If the entry burden for a student wishing to look at, for example, the change in occupancy of *Chrysis ignita* across Europe is to obtain perfect knowledge on the various changes and errors made in the determination of this incredibly contentious and difficult-to-separate group, *as well* as obtaining the exact provenance and intention of each and every record's determination, then nothing will ever happen. This is quite simply a ridiculous level of expectation to place upon users, and highlights a substantial flaw in the way in which nomenclature is handled under the current system.

In order to implement a digital analogue to the 're-determine and add a label' process, a number of modifications need to be made to the way in which we handle nomenclature in a data-only environment. Primary to these changes is the need to make any system *pre-emptive* in design rather than *reactive*. This means that any proposed system should *start* in a fail-safe manner, rather than needing to be changed *after* the fact to avoid catastrophic failure.

## Nomenclature/Taxonomic divergence (do I need any more?)
A nomenclature/taxonomic divergence occurs when a name no longer accurately refers to a singular type. Such divergences are commoner than users tend to realise, as the current system renders divergences invisible unless looked for. The vast majority of users of the UK Bees, Wasps, and Ants Recording Society (BWARS) data - where this project was developed - first encounter a divergence when trying to make sense of discontinuity or mismatch in data during analysis.

Nomenclatural divergences occur when research determines that the interpretation of a given taxon, even in a limited region, must change. Most frequently, this change is based on the discovery of cryptic species, the decision to synonymise multiple taxa, or the discovery of previously unknown species in a geographic area. Divergences are typically most evident when a taxon is split, such as in the discovery of cryptic species. As a result from this split there will exist instances of a singular name, used in both pre- and post-split manner. This singular name will then need further interpretation (which may not be possible to complete) to arrive at the author's intended interpretation.

### Geographic ranges and their role in divergence
As mentioned above, a nomenclatural divergence can arise from a geographically limited situation. Such an occurrence is reasonably frequent in the BWARS dataset, as researchers work on uncovering the various ways in which a singular name has been used across Europe.  Whilst the 'regionality' of recording history tends to be viewed as a thing that happened in the past, regionality is still very much a current issue. Differences of opinions on the validity of taxonomic changes persist, even under the guidance of the relevant authorities. However, the main causes of regionality are a lack of regionally tested identification methods, sub-species level variations across wide ranges, poor regional taxonomic and identification knowledge, shifting taxa ranges, and the time lag in accepting taxonomic changes.

The time lag in the acceptance of taxonomic changes is particularly well observed. Within the BWARS community there are still people who are unaware of changes that happened 20 years ago, and whilst they were active in the discipline. Data also frequently arrives from people who are actively using outdated interpretations of taxa, not knowing that the interpretation has even been changed. With how few people tend to provide data, as well as their frequently highly regional tendencies of recording, the knowledge of a region's recorders actively 'flavours' that region's dataset. These flavours also affect the various, and multiple, attempts at constructing global nomenclature collections. Every single attempt to create any form of global nomenclature collection falls into the trap of 'good for these taxa, in this region'. This regionalisation of purportedly global schemes is not an accident. The local region's nomenclatural divergences are the root cause of this drift.

## The technical basis for Understandings
Understandings are based on the principle of normalised relational databases. Separating the uses of a type's name from the type itself reveals the existence of a second normal form structure. This second normal form structure is backed up by the fact that there exist multiple interpretations of the same name, and have for many decades. There are various 'hack' systems that attempt to resolve the second normal form back to third, such as the use of 'sensu', 'auct' etc, but none of these have ever been implemented to the degree where such systems would fix the root cause of the problems experienced. There are multiple reasons for the lack of integration, though the contribution of 'traditional' taxonomy is worth specific mention. There is a tendency for taxonomists to consider their work in resolving various interpretations of a type to be 'complete' once their review is performed. As outlined above, divergences are not a *past* phenomenom, but a *continuous* one. In however many years it takes for someone to notice a divergence, taxonomists will have to, once again, repeat the process of resolving a divergence. Understandings recognise divergences as continuous and, accordingly, are able to reach third normal form.

## What makes a good basis for an Understanding
Every Understanding is based on a particular interpretation of how to apply taxonomic types to the real world. This interpretation must then be published so that others may use it, reference it, and critique it, before it can be used as the basis for an Understanding.

There are three points when considering a piece of information for use as the basis of an Understanding. These points are not mandatory, but will produce substantial improvements to the quality of the output in both accuracy and ease of use. It is improbable that references for past Understandings will be able to meet all three criteria. However, it is highly recommended that the basis of any future Understanding fulfills all three criteria. The three criteria are required for accurate application of any taxonomic decisions to reality, even in the absence of any Understandings system.

### 1. Accessibility of information
Accessibility of information is divided up into three tiers. The first, and lowest quality, tier is composed of articles which are behind paywalls. These paywalls are frequently of such a magnitude that access to the article is impossible for people who are not members of an academic institution. There are a wealth of articles on how damaging paywalls are to scientific collaboration, particularly in lower-income countries. Furthermore, placing an Understanding, which is designed to be referenced by as many people as possible, behind a paywall is considered, at best, to be a highly damaging move to the respective field.

### 2. Applicable geographic coverage
Reference material utilised in any work used as a basis of Understanding should be directly applicable to the geographic range of the proposed system. The gold standard for this aspect is that the work should include multiple specimens from the geographic region in question. If a work does *not* specifically include the geographic region, then a separate study should be undertaken to ascertain whether the original work does indeed apply to that area. This new study, which can simply reference the original work and state applicability to the region of interest, would then be the basis of the Understanding. In essence, a researcher has taken a piece of work where the applicability to a given region is unknown, then validated that the work applies to a given area. This is in slight contrast with modifications to modifications to a type, which should address the entire geographic range of the taxon.

### 3. Enabling identification
The selected information should enable the identification of the taxa in question. Ideally, this should be the medium of a dichotomous key, or similar level of practical application. Works that only provide genetic or chemical identification methods are accepted, as there are many situations where other identification methods, such as morphological, are not yet discovered. However, works which only provide genetic or chemical methods of identification are considered inferior to those which provide non-laboratory methods, due to the increased cost and difficulty of applying the identification method.

## How to store an Understandings system
There are currently two options for storing Understandings. The first, and by *far* the more complex, is '[NoNomS](https://github.com/Edwards-R/nonoms)' (Normalised Nomenclatural Storage), a PostgreSQL extension purpose-built for Understandings. NoNomS requires a running PostgreSQL server, as well as the SQL knowledge of how to run & control such a database. Setting up and managing a PostgreSQL server will likely require the assistance of a software engineer (or similar). A more accessible, low-tech, option is to run an Understandings system within a spreadsheet. Hopefully in the future there will be greater support for a more user-friendly Understandings platform, but the development of such is outside the scope of planned volunteer time.

The largest challenge associated with a manually-managed Understandings system is the management of large volumes of information without assistance. This is particularly true when making modifications to higher order taxa, where changes must propagate through the child taxa according to strict rules. To mitigate this challenge, it is recommended to limit the scope of a spreadsheet-based Understandings system to one taxonomic rank - likely species. *Do not ignore this recommendation!* Systems which grow beyond the size where they can be managed and supported quickly lose usefulness as they become dated and inaccurate.

The simplest Understandings system, with the above limitation, can be run in a spreadsheet using two columns. The first column is the Understanding, known simply as the Understanding. The second column is the Understanding which reflects the current interpretation of that Understanding, known as the *Resolved* Understanding. In the case that an Understanding represents the currently correct understanding of how to interpret a type, the Understanding will match the Resolved Understanding.

## Updating/removing Understandings from the Understandings system
Once an Understanding is entered into the Understandings system, that Understanding must never be changed or removed, as there may exist references/uses to that Understanding outside of the system. Removing, or obscuring by changing, any Understanding may lead to a situation where a previously used Understandings no longer has any match within the system. Instead, any modifications must now be handled using Operations, which are specifically designed to ensure continuity of information and conformity to taxonomic types.

The *Resolved Understanding* may be changed at any time, to reflect changes in where any given Understanding is currently considered. This enables the Understandings system to consisently send users to the current interpretation of any Understanding.

### Example
Starting from one taxon, *Bombus terrestris*: iso. Saunders: 1896

||Understanding||Resolved interpretation|
|---|---|---|---|
|+|*Bombus terrestris: iso. Saunders: 1896*|+|*Bombus terrestris: iso. Saunders: 1896*|
---
---
Sladen, in 1912, performs a split operation on *Bombus lucorum*: iso. Saunders: 1896. First, add the results of the split.

||Understanding||Resolved interpretation|
|---|---|---|---|
||Bombus terrestris: iso. Saunders: 1896||Bombus terrestris: iso. Saunders: 1896|
|+|*Bombus terrestris: iso. Sladen: 1912*|+|*Bombus terrestris: iso. Sladen: 1912*|
|+|*Bombus lucorum: iso. Sladen: 1912*|+|*Bombus lucorum: iso. Sladen: 1912*|
---
---
Next, add the aggregate Understanding.

||Understanding||Resolved interpretation|
|---|---|---|---|
||Bombus terrestris: iso. Saunders: 1896||Bombus terrestris: iso. Saunders: 1896|
||Bombus terrestris: iso. Sladen: 1912||Bombus terrestris: iso. Sladen: 1912|
||Bombus lucorum: iso. Sladen: 1912||Bombus lucorum: iso. Sladen: 1912|
|+|*Bombus terrestris agg: iso. Sladen: 1912*|+|*Bombus terrestris agg: iso. Sladen: 1912*|

---
---
A 'split' operation was used by Sladen, which means that there was considered to be *significant, widespread confusion* within existing data. Accordingly, all existing records of *Bombus terrestris*: iso. Saunders: 1912 contain an unknown-yet-significant amount of data from each of the split's components. The current resolved Understanding of *Bombus terrestris*: iso. Saunders: 1912 is therefore *Bombus terrestris agg*: iso. Sladen: 1912.

||Understanding||Resolved interpretation|
|---|---|---|---|
||Bombus terrestris: iso. Saunders: 1896|+|*Bombus terrestris agg: iso. Sladen: 1912*|
||Bombus terrestris: iso. Sladen: 1912||Bombus terrestris: iso. Sladen: 1912|
||Bombus lucorum: iso. Sladen: 1912||Bombus lucorum: iso. Sladen: 1912|
||Bombus terrestris agg: iso. Sladen: 1912||Bombus terrestris agg: iso. Sladen: 1912|

---
---
Following this, in 2008 Murray et al. split *Bombus lucorum*: iso. Sladen: 1912. The same steps are followed. First, add the results of the split.

||Understanding||Resolved interpretation|
|---|---|---|---|
||Bombus terrestris: iso. Saunders: 1896||Bombus terrestris agg: iso. Sladen: 1912|
||Bombus terrestris: iso. Sladen: 1912||Bombus terrestris: iso. Sladen: 1912|
||Bombus lucorum: iso. Sladen: 1912||Bombus lucorum: iso. Sladen: 1912|
||Bombus terrestris agg: iso. Sladen: 1912||Bombus terrestris agg: iso. Sladen: 1912|
|+|*Bombus lucorum: iso. Murray et al: 2008*|+|*Bombus lucorum: iso. Murray et al: 2008*|
|+|*Bombus cryptarum: iso. Murray et al: 2008*|+|*Bombus cryptarum: iso. Murray et al: 2008*|
|+|*Bombus magnus: iso. Murray et al: 2008*|+|*Bombus magnus: iso. Murray et al: 2008*|

---
---

Next, add the aggregate Understanding

||Understanding||Resolved interpretation|
|---|---|---|---|
||Bombus terrestris: iso. Saunders: 1896||Bombus terrestris agg: iso. Sladen: 1912|
||Bombus terrestris: iso. Sladen: 1912||Bombus terrestris: iso. Sladen: 1912|
||Bombus lucorum: iso. Sladen: 1912||Bombus lucorum: iso. Sladen: 1912|
||Bombus terrestris agg: iso. Sladen: 1912||Bombus terrestris agg: iso. Sladen: 1912|
||Bombus lucorum: iso. Murray et al: 2008||Bombus lucorum: iso. Murray et al: 2008|
||Bombus cryptarum: iso. Murray et al: 2008||Bombus cryptarum: iso. Murray et al: 2008|
||Bombus magnus: iso. Murray et al: 2008||Bombus magnus: iso. Murray et al: 2008|
|+|*Bombus lucorum agg: iso. Murray et al: 2008*|+|*Bombus lucorum agg: iso. Murray et al: 2008*|

---
---

A split was used, which means that there is significant, widespread confusion within existing data. Accordingly all existing records of *Bombus lucorum*: iso. Sladen: 1912 contain an unknown-yet-significant amount of data from each of the split's components. The current resolved Understanding of *Bombus lucorum*: iso. Sladen: 1912 is therefore *Bombus lucorum agg*: iso. Murray et al: 2008.

||Understanding||Resolved interpretation|
|---|---|---|---|
||Bombus terrestris: iso. Saunders: 1896||Bombus terrestris agg: iso. Sladen: 1912|
||Bombus terrestris: iso. Sladen: 1912||Bombus terrestris: iso. Sladen: 1912|
||Bombus lucorum: iso. Sladen: 1912|+|*Bombus lucorum agg: iso. Murray et al: 2008*|
||Bombus terrestris agg: iso. Sladen: 1912||Bombus terrestris agg: iso. Sladen: 1912|
||Bombus lucorum: iso. Murray et al: 2008||Bombus lucorum: iso. Murray et al: 2008|
||Bombus cryptarum: iso. Murray et al: 2008||Bombus cryptarum: iso. Murray et al: 2008|
||Bombus magnus: iso. Murray et al: 2008||Bombus magnus: iso. Murray et al: 2008|
||Bombus lucorum agg: iso. Murray et al: 2008||Bombus lucorum agg: iso. Murray et al: 2008|
---
---

## Compound Understandings
Occasionally it is necessary to create an 'item' which represents multiple Understandings. There are two defined methods for doing so: hybrids and complexes. Each method follows similar rulings to Understandings, with the goal of ensuring that compound Understandings are well documented. Never try to 'update' the contents of a compound Understanding if one of the component Understandings is updated. Instead, declare a new compound Understanding using the new component or components.

Compound Understandings do not belong in the same 'table' as Understandings, and must occupy a separate table.

### Complex
A complex Understanding uses one of the component's names, chosen by the creator of the Understanding. The author and year of a published document that details the components of the compound is then added, forming the trinity of name, author, and year that Understandings rely on. This published document is intended to be purely a reference point, containing only the compound Understanding and its component Understandings. so that other users of the data can use with confidence. Compound Understandings may be internal to a specific project, rather than being defined for the entire scope of the Understandings system. Such is particularly the case with complexes, which may be useful in a project where the participants lack the ability to reliably determine specific taxon confusions.

A complex Understanding is written as

> *Name cpx*: iso. Author: Year

### Hybrid
Hybrid Understandings are for when a specimen is decided to be a hybrid of two taxa. A hybrid Understanding is written as two Understandings, with 'x' in the middle.

> *Name1*: iso. Author1: Year1 x *Name2*: iso. Author2: Year2

## Conclusion
The current nomenclatural system causes the meaning of a taxonomic name to disassociate from the taxon under multiple scenarios. These scenarios are crucial to the continued use of the taxonomic system and therefore cannot be prohibited. The system proposed here recognises these disassociations, as well as their root cause in design, and solves the issue as much as it is possible to be solved. As a result, the nomenclatural and taxonomic system becomes far more robust, dynamic, useful, and accurate. Using Understandings, held in Understandings systems, it is finally possible to construct a truly global database of types, as well as practical, useful, and accurate databases of nomenclature.
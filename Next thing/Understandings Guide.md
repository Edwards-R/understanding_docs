# Understandings: An archival format for biological nomenclature

## Abstract
A novel method of handling biological nomenclature bypasses multiple current blockers, whilst simultaneously improving type precision of long-term data storage.

## Introduction
This document introduces 'Understandings' as an archival format for biological nomenclature, as well as providing guidance for their usage. Understandings are a way to, differentiate between multiple interpretations of the same taxonomic name in a standardised, non-taxon-specific manner. Differentiation is achieved by attaching further information to traditional nomenclature.

The archival nature of Understandings is designed to maintain the precision of biological nomenclature over time, in ways that conventional nomenclature cannot, without requiring substantial external input. Maintaining precision of a name against taxonomic types is a high priority for many systems, including:

- Biological recording schemes
- Academic writing
- Museum specimen collections
- Private reference collections
- Academic data collection

Currently, there is a lack of awareness as to what *can* be done - with current technology, design patterns, and resources - to create archival biological nomenclature. Consequently, the vast majority of users of the above list of systems are either unaware of the potential for nomenclature and taxonomy to diverge, or unaware of solutions to manage such occurrences.

An Understandings system may be run in many formats, from highly complex, specifically designed, custom packages, all the way to a piece of paper or Excel spreadsheet. Understandings systems running on lower-technology solutions, such as paper or Excel, are advised to focus on small sub-groupings of < 50 taxa due to the workload of manual management. However, it *is* possible to manage larger groupings using lower-technology solutions.

Understandings are designed to be modular in taxonomic and geographic scope. Additionally, different Understanding systems may be used alongside each other, as well as with other type-based nomenclature. Because all Understandings are constructed on the backbone of taxonomic types, if two Understandings systems are utilising the same backbone, translation of information between any number of Understandings systems is precise and painless. Utilising a singular backbone ensures that Understandings are compliant with the International Commission of Biological Nomenclature and International Commission of Zoological Nomenclature.

> At the time of writing, Understandings have been fully implemented on the Aculeate Hymenoptera of Great Britain. Trial implementations have been successfully performed for other taxonomic groups and geographic regions, demonstrating wider applicability of the system.

## Understandings and the Understandings System
> An "Understanding" refers to a particular interpretation of a taxonomic work. The Understandings system then provides rules and guidance on how Understandings are managed. 

### Previous variants of Understandings
The core idea behind Understandings has been in use for many years, particularly in situations where taxonomists must differentiate between multiple interpretations of the same taxon. For example, a taxonomist may talk about 'X sensu author'(*sense of*) or 'X auct nec' (*of other authors*). These are all variations on the theme of finding a way to talk about multiple interpretations of the same work. Understandings are a codified version of the same idea, with added functionality to ensure longevity and maintain the greatest taxonomic precision possible.

### How to write Understandings
Understandings come with a default method of being written, though it is anticipated that other formats will develop as more users test the system and identify deficiencies. The default format is called the 'iso format', short for 'In the Sense Of'. Written down, a iso-format Understanding is composed of:

`Name: iso. Author: Year: Version`

The author and year refer to the interpretation being referenced. When read aloud, it is often useful to say the full text 'in the sense of' rather than the abbreviation. Doing so will allow people who are not familiar with Understanding, yet are familiar with taxonomy, to fully understand the intent. For example, `Andrena scottica: iso. Else & Edwards: 2018` can be read as 'Andrena scottica in the sense of Else & Edwards, 2018'.

The name can be a singular entry e.g. `Bombus` or a binomial e.g. `Bombus lucorum`. The most common use of Understandings in the BWARS system, by far, are binomial Understandings e.g.
`Bombus lucorum: iso. Murray et al: 2008`.

## Archival formats
Archival formats are designed to store information accurately for long periods of time. Understandings are an archival format for biological nomenclature which use a form of version control to operate. Within an Understanding system, any member Understanding may be interrogated to find out which currently valid types are contained within that Understanding. As information and knowledge surrounding taxa changes, the Understanding system ensures that nomenclatural changes are applied to member Understandings with the least amount of effort and intervention possible.

It should be noted that there are many situations where it will take the redetermination of a specimen (or voucher of a specimen) in order to arrive at a modern single-type interpretation. In such situations, the Understandings system will return the collection of *potential* member types represented by the Understanding.

## Nomenclature/Taxonomic disjunction
Understandings may be generated when a type is modified, or in the event of a nomenclatural disjunction. A nomenclatural disjunction occurs when research determines that the interpretation of a given taxon must change. The change does not have to be global - a disjunction may occur within a limited geographic scope. Disjunctions are typically most evident when a taxon is split. In such a case, there exists data labelled with a name which has the potential to refer to multiple taxa, without further modification or interpretation.

### Example
> This section references '*Cryptic species diversity in a widespread bumble bee complex revealed using mitochondrial DNA RFLPs*' by Murray et al., 2008. DOI: `10.1007/s10592-007-9394-z`

In 2008, Murray et al. demonstrated that what *was* known as *Bombus lucorum* in Great Britain and Ireland was a composite of three types:

- *Bombus lucorum*
- *Bombus cryptarum*
- *Bombus magnus*

The spread of these three taxa is ubiquitous, both geographically and temporally, with no reliable field or microscopic method available to separate specimens. Currently, the only known reliable method of separation is redetermination of individual specimens using genetic or chemical methods. All extant records of *Bombus lucorum* - as well as historic uses of *Bombus cryptarum* and *Bombus magnus* - are, according to the taxonomic work of Murray et al., to be considered as a mixture of *Bombus lucorum/cryptarum/magnus*.

Examination of the GBIF entry for *Bombus lucorum* as of 2024-09-19 (https://www.gbif.org/species/1340298) still shows a large volume of data for '*Bombus lucorum*' in the geographic region covered by Murray et al.. All of this data, other than ~200 records which have been genetically sequenced, relates to the mixture of types rather than the singular type. Because Murray et al.'s work only addresses a limited geographic region, the changes produced impact only that limited region. No new types were created as a result of this work, as the types were well established in other regions of the world, meaning that Murray et al. 2008 references a change in the *application* of types, rather than a change to types themselves.

As demonstrated, the multiple, uncontrolled, interpretations of a singular type prevent clear communication, resulting in lower potential for collaboration. The prevention of clear communication conflicts with the existing taxonomic system's goal of facilitating clear communication. The creation of a version control solution, such as Understandings and the accompanying Understandings system, is therefore a high priority.

## Technical basis for the Understandings system
The Understandings system is based in relational databasing, using a third normal form design. The entire purpose of Understandings is to maintain the *relation* between interpretations of taxonomy and types. Accordingly, a relational database is the logical place for such a system. Reaching third normal form guarantees continued precision of the interpretations over time, satisfying the archival requirements of the system.

## Understandings and types
The composition of a type is formalised when considered as part of the Understandings system. The components are divided into three portions:
- The name, author, and year of declaration of the type. This forms the 'identifier' for the type
- A physical specimen, as well as materials derived from that individual specimen e.g. genetic barcode, whole genome sequence
- A description which establishes the limits of the taxonomic region claimed by the taxon.

Of these parts, the identifier (name, author, and year) may not be changed. The other two parts may be changed, generating a new Understanding when they are. The strict declaration of these aspects, and their handling, is the core of the Understandings system's background. Notably, the separation of the components enables the safe declaration of a replacement type specimen. All material identified based on a replacement type specimen will be immediately distinguishable from any other type specimen. Should an error be made in the assignment of a replacement type specimen, the impact of that error will be minimised. Material identified according to the erroneous designation will be immediately apparent, whilst material identified not using the erroneous designation will not be affected at all.

The ability to safely declare a new type specimen, whilst safeguarding extant data, has been specifically tested in the Understandings system. The target use cases are:
- types where the type specimen has been lost entirely
- types where the type specimen has degraded to the point of non-functionality
- types where the type specimen is non-existent
- situations where the types descriptions are unclear, overlapping, or unknown

These are all critical use cases found in aculeate hymenopteran taxonomy, where the current system's lack of ability to handle error safely is causing taxonomists to hesitate in conducting broad-scale modernisation of their taxonomy. The publication of 403 new species using 'minimalist revision and description' methods by [Sharkey et al. in 2021](https://zookeys.pensoft.net/article/55600/) raised considerable tensions within the taxonomic community. As an umbrella response, Zamani et al.'s publication '[DNA barcodes on their own are not enough to describe a species](https://resjournals.onlinelibrary.wiley.com/doi/full/10.1111/syen.12538)' covers the critical points in regards to the Understandings system.

In summary, Sharkey et al. argue that in order to deliver the description of new taxa in a reasonable timeframe, the process of discovery and description must be sped up. Zamani et al. respond that Sharkey's process is inappropriate for multiple reasons, of which the salient points are the establishment of a 'parallel taxonomic system' and the idea that databasing of results is a significant bottleneck to the process of description.

The Understandings system provides a solution to this discussion by enabling users to make the large-scale declarations that Sharkey et al. require, whilst maintaining and protecting existing data as required by Zamani et al.. Crucially, the Understandings system protects and elevates the type-based system, preventing a schism from occurring whilst enabling flexibility in the application of taxonomy.

## Operations in an Understandings system
The ways in which an Understanding can be modified are very strictly controlled to ensure continued taxonomic precision. There are four defined operations:

- Create
- Merge
- Split
- Compound

All regular operations of an Understanding system will be one of the above. There are irregular operations, but the number of these being utilised in a well-run system should be extremely low.

### Create
Creation is used when a new Understanding, that has not derived from any existing Understanding in the system, needs to be added into the system. The most common reason for using create, outside of initial setup, is newly arrived taxa from outside of the geographic scope of the system.

A variant of creation is also used to create synonym Understandings to back-fill information. This variant may be used at any point, but never to create a non-synonym Understanding.

### Merge
Merging refers to the operation that combines multiple Understandings into one. The merge operation reflects a decision that what *was* considered multiple taxa are now considered one taxon.

### Split
A split occurs when what was considered to be one taxon is now considered to be multiple. Notably, a split operation also involves the creation of an aggregate Understanding. This aggregate, written as `x agg`, represents the novel state of the existing information. For example, when Murray et al. split *Bombus lucorum*, this also resulted in `*Bombus lucorum agg*: iso. Murray et al: 2008`. The previous Understanding of *Bombus lucorum* uses the new aggregate version, as it is impossible to assign records to any of the new taxa without redetermination of specimens.

Splits require particular attention as, when a split is performed, all existing data is moved to an aggregate. Aggregate data is of far less value to science than non-aggregate, and so the cost-benefit of performing a split vs create should be assessed. There is no definitive rule for when to utilise a split vs create. Instead, the guidance is to ask the question '*Is there significant, widespread, confusion present in the taxon?*'. If the answer is yes, use split. If no (i.e. most of the information present is clean and of only one taxon), then the situation may be better handled by a creation.

### Compound
Some operations exist that are best regarded as a compound of the previous steps. The most common of these is the transfer of one taxon to another parent. For example, transferring a species to a different genus. The logic behind this is that a genus is formed out of its component pieces - in our example, species. If a component is removed, that genus is no longer exactly the same. In fact, it is a different *Understanding* of what that genus is. 'Moving' a taxon is therefore a compound operation of a split. The taxa to be moved are then held 'in isolation', from where they are merged with their destination to form a new Understanding. 

### Irregular operations
Irregular operations are primarily concerned with fixing errors in the system which have not yet had time to propagate, as well as moving synonymy around. Irregular operations should, in a well-run system, be extremely rare. Be *absolutely certain* that the operation cannot be achieved using regular operations. Over-use of irregular operations will quickly cause far more problems than they solve.

## Propagation of higher rank changes
When an operation is performed on an Understanding, it is a rule that all Understandings with the changed Understanding as their parent are also changed. Using the BWARS Understanding system as an example, if the family 'Apidae' were to be split, this would result in new Understandings of the relevant genera, and then in turn the relevant species. The author and year of the 'children' Understandings is the same as that of the main change. Only the currently valid, non-aggregate Understandings are propagated.

The exact details of why this rule is in place, as well as a full examination of the consequences of *not* following it, would take up approximately as much time as writing and reading this entire document. As such, it is recommended to either use a prebuilt Understandings library management platform, or restrict a system to a singular rank - usually species - so as to avoid needing to interact with this aspect of Understandings manually.

Simplified, the reasoning behind the propagation of changes is to firstly prevent the perpetuation of synonymy, and secondly to prevent the creation of non-existent synonyms.

## How to create an Understandings system
This section covers how to start and fill out an Understandings system. The process is broken down into a number of steps, but please do keep in mind that there is significant potential to encounter 'holes' in taxonomic knowledge. When a hole is encountered, the Understandings system encourages the consultation of taxon experts, or the closest possible alternative. Understandings provide considerable ability to adjust nomenclature, which means that imperfections in Understandings are not nearly as dangerous as they would be in taxonomy. **Perfection is the enemy of progress**. Start in the best place possible, then use the built in abilities of the Understandings system to refine over time.

### Define a unique name for the system
Each Understandings system needs a unique name, in order to aid in comparison between systems. It is recommended to keep this name short to aid in comprehension, as when comparing between systems manually this name will prefix every entry. As an example, the system in which Understandings were developed has the tag 'BWARS'.

### Defining scope
The first stage in establishing a new Understandings system is to define the geographic and taxonomic scope. In general, an Understandings system should cover the largest taxonomic and spatial size possible. The size will be limited, both taxonomically and spatially, by numerous practical concerns. The most common problem encountered to date is when users in one area wish to make a change, whilst others in a different area do not wish to make a change. For example, the change in nomenclature for *Bombus lucorum*, introduced by Murray et al. in 2008 resulted in the UK and Ireland wishing to change, whilst the remainder of the world did not. Other concerns include funding allocation, national interests, and conflicts of opinion.

Larger scope, in both geographic and taxonomic is overall preferable, as it reduces the both the number of disparate places users need to go in order to find information and the amount of system administration. However, a larger taxonomic scope means a far higher variety of geographic ranges become subject-appropriate. For example, the appropriate geographic range for highly migratory birds will likely be global, whilst the appropriate geographic range for less-mobile taxa, such as bees, is frequently smaller. Experience suggests 'medium-sized European country' as a reasonable size here. It is recommended to follow any divisions of taxonomic recording present in the target geographic area, such as national biological schemes. These divisions will tend to contain the knowledge required to establish an Understandings system, as well as the core target audience of users of the resulting system.

For guidance, look at the distribution of taxon-specific recording schemes in Great Britain. These will give you an idea of the smaller bounds of scope. If there is still doubt as to whether the scope of a proposed system is appropriate, it is recommended to pick a size towards the larger end of the scale. Should the size be eventually considered to be too large, the system can be split by simply cloning the system and providing a copy to each resulting chunk. Splitting an Understandings system into separate areas is a much simpler task than combining, so it makes sense to over-estimate rather than under-estimate.

### Define applicable ranks
Another useful aspect of an Understandings system is that it is not required to utilise the entire rank backbone. The ability to restrict the applicable ranks is especially useful when addressing a small taxonomic grouping. For example, the BWARS Understandings system only uses the following ranks:

 - Superfamily
 - Family
 - Genus
 - Species

The most important - and unbreakable - rule is that every entity must have an entry in the ranks above it. In the BWARS system, a species *must* have a genus, family, and superfamily. A genus must have a family and superfamily.

### Identify a starting point for knowledge
Whilst it may be possible to trace the lineage of nomenclature through every change, all the way back to type declaration, most taxa do not have that luxury. There will be periods of uncertainty and confusion, where the progression of nomenclature cannot be established. It is recommended to establish a 'false start' date for an Understandings system to prevent needing to sort through increasingly old and difficult to obtain/interpret taxonomic works.

The overall goal is to start as far back in time as is possible and practical. The overall limiting factor is most likely to be the general availability of knowledge. In this regard, taxon experts are likely the best means of identifying available resources, as they tend to have the knowledge of how taxonomic papers have been applied to the geographic region in question. In the absence of taxon specialists, taxonomic papers may be used instead. This method will require more work in checking applicability to the geographic region, leading to the people performing this work developing into taxon specialists for their region themselves. In the absence of either taxon experts or significant taxonomic papers, identification keys may be used.

### Identify timespan of the assembled data
The final aspect to consider is the timespan of the assembled data. There is little reason to spend considerable amounts of time assembling and organising Understandings for time periods where there is no information or raw data. A key date here is 1960, which is a rough approximation for when digitised data starts to appear. This phenomenon is thought to be driven by easier access to personal computers.

When examining the distribution of data over time for a taxonomic group previously identified. It is almost inevitable that some data will be so old that the Understanding intended will simply be unknown. The goal here is not to identify the earliest record, but to identify any point in time where significant data does exist. It is worth spending extra effort to ensure that these points are covered by the Understandings system.

### Compare the knowledge start and data timespan
Once the starting point of knowledge and desired starting point of data are known, compare the two. If the starting point of data is equal to or after the starting point of knowledge, no further action needs to be taken. If the starting point of data is *prior* to the starting point of knowledge, then there needs to be a plan for generating an Understanding. In the development of Understandings, the name of the scheme plus current year has been used when there is no available information e.g. 'Bombus: iso. BWARS: 2021'. Doing this firmly creates an Understanding, with the added inference that no taxonomic authority could be definitively linked to that interpretation.

### What makes a good basis for an Understanding
There are three points when considering a piece of information for use as the basis of an Understanding. These points are not mandatory, but will produce substantial improvements to the quality of the output in both accuracy and ease of use.

The first concerns the accessibility of the piece of information. Accessibility is divided up into three tiers. The first tier concerns Articles published behind paywalls in journals. Such articles provide the lowest quality backings for Understandings, as they often have steep fees associated with access. These fees are a significant impediment to utilisation, especially in areas where there is considerable non-academic research being conducted. The second 'tier' of availability are published literature which the user must buy, such as many keys to identification. The third, and best, are works which are open access in a common format.

The second point is that the reference material utilised in any work should be directly applicable to the geographic range of the proposed system. The gold standard for this aspect is that the work should include multiple specimens from the geographic region in question. If a work does *not* specifically include the geographic region, then a separate study should be undertaken to ascertain whether the original work does indeed apply to that area. This new study, which can simply reference the original work and state applicability to the region of interest, would then be the basis of the Understanding. In essence, a researcher has taken a piece of work where the applicability to a given region is unknown, then validated that the work applies to a given area.

The third points is that the selected information should enable the identification of the taxa in question. Ideally, this should be the medium of a dichotomous key, or similar level of practical application. Works that only provide genetic or chemical identification methods are accepted, as there are many situations where other identification methods, such as morphological, are not yet discovered. However, works which only provide genetic or chemical methods of identification are considered inferior to those which provide non-laboratory methods, due to the increased cost and difficulty of applying the identification method.

It is improbable that references for past Understandings will be able to meet all three criteria. However, it is highly recommended that the basis of any future Understanding fulfills all three criteria. The three criteria are required for accurate application of any taxonomic decisions to reality, even in the absence of any Understandings system.

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

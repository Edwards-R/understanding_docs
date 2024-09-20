# Understandings as an archival format for biological nomenclature

## Abstract
This document introduces 'Understandings' as an archival format for biological nomenclature, as well as the guidance for their usage.

The archival nature of Understandings is designed to maintain the precision of biological nomenclature over time in ways that conventional nomenclature cannot. Maintaining precision of a name against taxonomic types is a high priority for many situations, including:

- Biological recording schemes
- Academic writing
- Museum specimen collections
- Private reference collections
- Academic data collection

Currently, there is a lack of awareness as to what *can* be done - with current technology, design patterns, and resources - to create archival biological nomenclature. Accordingly, the vast majority of users of the above list of systems are either unaware of the potentiality for nomenclature and taxonomy to diverge, or unaware of solutions to manage such occurences.

An Understandings system may be run in many formats, all the way to a piece of paper or Excel spreadsheet. Understandings systems running on paper or Excel are advised to focus on small sub-groupings of < 50 taxa due to the workload of manual management, but it *is* possible to do so.

Understandings are designed to be modular in taxonomic and geographic scope, as well as being non-exclusive in application. All Understandings are constructed on the backbone of taxonomic types. If two Understandings systems are utilising the same backbone of taxonomic types which, under the International Commission of Biological Nomenclature and International Commission of Zoological Nomenclature, users *should* be, translation of information between any number of Understandings systems is precise and painless.

> As of right now, the system has not been tested on other biological domains. There are no reasons why Understandings would fail when applied to these other domains, but this document will only cover known and tested application of Understandings.

## Nomenclature/Taxonomic disjunction
A nomenclatural disjunction occurs when research determines that the interpretation of a given taxon must change. The change does not have to be global, a disjunction may occur within in a limited geographic scope. Disjunctions are typically most evident when a taxon is split. In such a case, there exists extant data labelled with a name which, without further modification or interpretation, has the potential to refer to multiple taxa.

### Example
> This section references '*Cryptic species diversity in a widespread bumble bee complex revealed using mitochondrial DNA RFLPs*' by Murray et al, 2008. DOI: `10.1007/s10592-007-9394-z`

In 2008, Murray et al demonstrated that what was known as *Bombus lucorum* in Great Britain and Ireland was a composite of three types:

- *Bombus lucorum*
- *Bombus cryptarum*
- *Bombus magnus*

The spread of these three taxa is ubiquitous in both geographic and temporal coverage, with no 'generic' method available to separate specimens.The only reliable method of separating these taxa currently remains at redetermination of individual specimens using genetic or chemical methods. Accordingly, all extant records of *Bombus lucorum* (as well as historic uses of *Bombus cryptarum* and *Bombus magnus*) are, according to the taxonomic work of Murray et al, to be considered as a mixture of *Bombus lucorum/cryptarum/magnus*.

Examination of the GBIF entry for *Bombus lucorum* as of 2024-09-19 (https://www.gbif.org/species/1340298) still shows a large volume of data for '*Bombus lucorum*' in the geographic region covered by Murray et al. All of this data, other than ~200 records which have been genetically sequenced, is of the mixture rather than the singular type.

Because the research performed only addresses a limited geographic region, the change impacts only that limited region. Restriction to the limited geographic region is critical to preventing changes which do not cause

No new types were created as a result of this work, meaning that this work references a change in the *application* of types, rather than a change to types themselves.

### Example of impact of disjunction
 - What does the data look like at a disjunction
 - Why do we care?
 - Do we care? Really? Is this *necessary* for understanding?


## Notes
- What is an archival format?
- Understandings are are a way of writing biological nomenclature
- They add a way to keep track of nomenclature across time
  - 'Track' is defined as being able to maintain relation to type
- Useful for any situation in which accuracy of biological nomenclature across time is important
  - genetic libraries
  - academic writing
  - museum specimen collections
  - academic data collection
  - private specimen collections
  - occurrence biological recording

### Notes - two ways that Understandings change

There are 2 things that lead to Understandings change.

This is based on:
- The type
- The application of a type

#### The first is when the interpretation of the type changes.
- Split
- Move
- Merge
- New type specimen

This change affects the type, then the application

#### The second is when the application of a type changes (e.g. B. lucorum)
This change only affects the application, and the type remains untouched
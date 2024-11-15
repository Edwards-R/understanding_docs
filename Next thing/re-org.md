# Understandings: An archival format for biological nomenclature

## Abstract
A novel method of handling biological nomenclature which bypasses multiple current blockers, whilst simultaneously improving type precision of long-term data storage. This document introduces 'Understandings' as both an every-day archival format for biological nomenclature, as well as providing guidance for their usage.

## Introduction

### Problem statement
Maintaining the precision of a name against taxonomic types is a high priority for many systems, including:

- Biological recording schemes
- Academic writing
- Museum specimen collections
- Private reference collections
- Academic data collection

A major problem in the above systems is the potential for nomenclature and taxonomy to diverge across time, due to the limitations of conventional nomenclature. Currently, many users are unaware of this problem, or are unaware of solutions to manage such occurrences using available technology, design patterns, and resources.

### Introduce Understandings & how they solve the problem
"Understandings" and their associated system address the issue of divergence by using time proven relational database design patterns to differentiate between multiple interpretations of the same taxonomic name in a standardised, non-taxon-specific manner.
 
An Understanding refers to a particular interpretation of a taxonomic work. The Understandings system then provides rules and guidance on how Understandings are managed. Within an Understanding system, any member Understanding may be interrogated to find out which currently valid types are contained within that Understanding. As information and knowledge surrounding taxa changes, the Understanding system ensures that nomenclatural changes are applied to member Understandings with the least amount of effort and intervention possible. It should be noted that there are many situations where it will take the redetermination of a specimen (or voucher of a specimen) in order to arrive at a modern single-type interpretation. In such situations, the Understandings system will return the collection of potential member types represented by the Understanding.

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

The Understandings system provides a solution to this discussion by enabling users to make the large-scale declarations that Sharkey et al. require, whilst maintaining and protecting existing data as required by Zamani et al.. In addition, the Understandings system provides this extra capability whilst maintaining strict adherence to the existing taxonomic system, as well as the nomenclatural codes. By doing so, Understandings protect and elevate the type-based system, preventing a schism from occurring, whilst enabling flexibility in the application of taxonomy.

## Nomenclature/Taxonomic divergence
A nomenclature/taxonomic divergence occurs when a name no longer accurately refers to a singular type. Such divergences are commoner than users tend to realise, as the current system renders divergences invisible unless looked for. The vast majority of users of the UK Bees, Wasps, and Ants Recording Society (BWARS) data - where this project was developed - first encounter a divergence when trying to make sense of discontinuity or mismatch in data during analysis.

Nomenclatural divergences occur when research determines that the interpretation of a given taxon, even in a limited region, must change. Most frequently, this change is based on the discovery of cryptic species, the decision to synonymise multiple taxa, or the discovery of previously unknown species in a geographic area. Divergences are typically most evident when a taxon is split, such as in the discovery of cryptic species. As a result from this split there will exist instances of a singular name, used in both pre- and post-split manner. This singular name will then need further interpretation (which may not be possible to complete) to arrive at the author's intended interpretation.

### Geographic ranges and their role in divergence
> New section! Explain that divergences are frequently regional in nature. This is due to the fact that divergences often result from confusion/widespread incorrect identification in specific regions.
>
> Maybe get into the fact that every single 'global nomenclature' system ever created to date falls into the trap of 'good for these taxa in this region'. This is not an accident - the very design of the existing nomenclature systems leads to this outcome.

As mentioned above, a nomenclatural divergence can arise from a geographically limited situation. Such an occurrence is reasonably frequent in the BWARS dataset, where researchers work on uncovering the various ways in which a singular name has been used across Europe.  Whilst the 'regionality' of recording history tends to be viewed as a thing that happened in the past, regionality is still very much a current issue. Differences of opinions on the validity of taxonomic changes persist, even under the guidance of the relevant authorities. However, the main causes of regionality are a lack of regionally tested identification methods, sub-species level variations across wide ranges, poor regional taxonomic and identification knowledge, shifting taxa ranges, and the time lag in accepting taxonomic changes.

The time lag in the acceptance of taxonomic changes is particularly well observed. Within the BWARS community there are still people who are unaware of changes that happened 20 years ago, and whilst they were active in the discipline. Data also frequently arrives from people who are actively using outdated interpretations of taxa, not knowing that the interpretation has even been changed. With how few people tend to provide data, as well as their frequently highly regional tendencies of recording, the knowledge of a region's recorders actively 'flavours' that region's dataset. These flavours also affect the various, and multiple, attempts at constructing global nomenclature collections. Every single one of these attempts to create any form of global nomenclature collection falls into the trap of 'good for these taxa in this region'. This is not an accident: regional nomenclatural divergences are the root cause.
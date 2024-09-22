# Understandings as an archival format for biological nomenclature

## Introduction
This document introduces 'Understandings' as an archival format for biological nomenclature, as well as guidance for their usage. Understandings are a way to, in a standardised, non-taxon-specific manner, differentiate between multiple interpretations of the same taxonomic name. Separation is achieved by attaching further information to traditional nomenclature.

The archival nature of Understandings is designed to maintain the precision of biological nomenclature over time, in ways that conventional nomenclature cannot, without requiring substantial external input. Maintaining precision of a name against taxonomic types is a high priority for many systems, including:

- Biological recording schemes
- Academic writing
- Museum specimen collections
- Private reference collections
- Academic data collection

Currently, there is a lack of awareness as to what *can* be done - with current technology, design patterns, and resources - to create archival biological nomenclature. Accordingly, the vast majority of users of the above list of systems are either unaware of the potential for nomenclature and taxonomy to diverge, or unaware of solutions to manage such occurences.

An Understandings system may be run in many formats, from highly complex, specifically designed, custom packages, all the way to a piece of paper or Excel spreadsheet. Understandings systems running on lower-technology solutions, such as paper or Excel, are advised to focus on small sub-groupings of < 50 taxa due to the workload of manual management. However, it *is* possible to manage larger groupings using lower-technology solutions.

Understandings are designed to be modular in taxonomic and geographic scope, as well as being non-exclusive in application. All Understandings are constructed on the backbone of taxonomic types. If two Understandings systems are utilising the same backbone of taxonomic types, translation of information between any number of Understandings systems is precise and painless. Utilising a singular backbone ensures that Understandings are compliant with the International Commission of Biological Nomenclature and International Commission of Zoological Nomenclature.

> As of right now, the system has not been tested on other biological domains. There are no reasons why Understandings would fail when applied to these other domains, but this document will only cover known and tested application of Understandings.

## Nomenclature/Taxonomic disjunction
A nomenclatural disjunction occurs when research determines that the interpretation of a given taxon must change. The change does not have to be global, a disjunction may occur within in a limited geographic scope. Disjunctions are typically most evident when a taxon is split. In such a case, there exists data labelled with a name which has the potential to refer to multiple taxa, without further modification or interpretation.

### Example
> This section references '*Cryptic species diversity in a widespread bumble bee complex revealed using mitochondrial DNA RFLPs*' by Murray et al., 2008. DOI: `10.1007/s10592-007-9394-z`

In 2008, Murray et al. demonstrated that what *was* known as *Bombus lucorum* in Great Britain and Ireland was a composite of three types:

- *Bombus lucorum*
- *Bombus cryptarum*
- *Bombus magnus*

The spread of these three taxa is ubiquitous, both geographically and temporally, with no 'generic' method available to separate specimens. Currently, the only reliable method of separating these taxa is redetermination of individual specimens using genetic or chemical methods. All extant records of *Bombus lucorum* (as well as historic uses of *Bombus cryptarum* and *Bombus magnus*) are, according to the taxonomic work of Murray et al., to be considered as a mixture of *Bombus lucorum/cryptarum/magnus*.

Examination of the GBIF entry for *Bombus lucorum* as of 2024-09-19 (https://www.gbif.org/species/1340298) still shows a large volume of data for '*Bombus lucorum*' in the geographic region covered by Murray et al.. All of this data, other than ~200 records which have been genetically sequenced, is of the mixture rather than the singular type. Because Murray et al.'s work only addresses a limited geographic region, the changes impacts only that limited region. No new types were created as a result of this work, meaning that this work references a change in the *application* of types, rather than a change to types themselves.

The multiple, uncontrolled, interpretations of a singular type prevent clear communication, resulting in lower potential for collaboration. The prevention of clear communication conflicts with the existing taxonomic system's goal of facilitating clear communication. The creation of a version control solution is therefore a high priority.

## An archival format
> Archival formats are formats designed to store information accurately for long periods of time. Understandings are an archival format for biological nomenclature which use a form of version control to operate. Within an Understanding system, any member Understanding may be interrogated to find out which currently valid types are contained within that Understanding. As information and knowledge surrounding taxa changes, the Understanding system ensures that nomenclatural changes are applied to member Understandings with the least amount of effort and intervention possible.

> It should be noted that there are a great many situations where it will take the redetermination of a specimen (or voucher of a specimen) in order to arrive at a modern single-type interpretation. In such situations, the Understandings system will return the collection of *potential* member types.

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

In summary, Sharkey et al. argue that in order to deliver the description of new taxa in a reasonable timeframe, the process of discovery and decription must be sped up. Zamani et al. respond that Sharkey's process is inappopriate for multiple reasons, of which the core salient points are the establishment of a 'parallel taxonomic system' and the idea that databasing of results is a significant bottleneck to the process of description.


## How to create an Understandings system
This section covers how to start and fill out an Understandings system. The process is broken down into a number of steps, but please do keep in mind that there is significant potential to encounter 'holes' in taxonomic knowledge. When a hole is encountered, the Understandings system encourages the consultation of taxon experts, or the closest possible alternative. Understandings provide considerable ability to adjust nomenclature, which means that imperfections in Understandings are not nearly as dangerous as they would be in taxonomy. **Perfection is the enemy of progress**. Start in the best place possible, then use the built in abilities of Understandings to refine over time.

### Defining scope
The first stage in establishing a new Understandings system is to define the geographic and taxonomic scope. In general, the idea is Understandings should operate at the largest size possible before becoming unwieldy. In practice, the scope depends vastly upon the subject taxa and geographic region of interest. A larger taxonomic scope is overall preferable, as it reduces the number of disparate places users need to go in order to find information. However, a larger taxonomic scope means a far higher variety of appropriate geographic ranges become appropriate, which weakens the overall system. It is recommended to firstly follow any taxonomic of recording present in the target geographic area. These divisions will tend to contain the knowledge required to establish an Understanding system, as well as the core target audience of users.

When considering geographic scope, the goal is to reach as wide an area as possible before problems occur. The most common problem encountered will likely be when users in one portion of the covered area wish to make a change, whilst others do not wish to make a change. If the difference in such a situation becomes irreconcilable, the solution is to simply make a copy of the current state of the system, dividing the geographic area without loss of information. Splitting an Understanding system into separate areas is a much simpler task than combining, so it makes sense to over-estimate rather than under-estimate.

For guidance, look at the distribution of taxon-specific recording schemes in Great Britain. These will give you an idea of the lower bound of scope. If there is still doubt as to whether the scope of a proposed system is appropriate, either pick some scenarios to game out or simply commit to the system. Understandings are designed to be incredibly forgiving and maleable, making changes far easier to implement than traditional taxonomy.

### Identify a starting point for knowledge
Whilst it may be possible to trace the lineage of nomenclature through every change, all the way back to type declaration, most taxa do not have that luxury. There will be periods of uncertainty and confusion, where the progression of nomenclature cannot be established. It is recommended to establish a 'false start' date for an Understandings system to prevent needing to sort through increasingly old and difficult to obtain/interpret taxonomic works.

The overall goal is to start as far back in time as is possible and practical. The overall limiting factor is most likely to be the general availability of knowledge. In this regard, taxon experts are likely the best means of identifying available resources, as they tend to have the knowledge of how taxonomic papers have been applied to the geographic region in question. In the absence of taxon specialists, taxonomic papers may be used instead. This method will require more work in checking applicability to the geographic region, leading to the development of taxon specialists. In the absence of either taxon experts or significant taxonomic papers, identification keys may be used.

### Identify timespan of the assembled data
The final aspect to consider is the timespan of the assembled data. There is little reason to spend considerable amounts of time assembling and organising Understandings for time periods where there is no information or raw data. A key date here is 1960, which is a rough approximation for when digitised data starts to appear. This phenomenon is thought to be driven by easier access to personal computers.

Examine the distribution of data over time for the taxonomig group previously identified. It is almost inevitable that some data will be so old that the Understanding intended will simply be unknown. The goal here is not to identify the earliest record, but to identify any point where significant data does exist. Where such time spans exist, it is worth spending extra effort to cover that region thoroughly.

### Compare the knowledge start and data timespan
Once the starting point of knowledge and desired starting point of data are known, compare the two. If the starting point of data is equal to or after the starting point of knowledge, no further action needs to be taken. If the starting point of data is *prior* to the starting point of knowledge, then there needs to be a plan for generating an Understanding. In the development of Understandings, the name of the scheme plus current year has been used when there is no available information e.g. 'Bombus: iso. BWARS: 2021'. Doing this firmly creates an Understanding, with the added inference that no taxonomic authority could be definitively linked to that interpretation.

### What makes a good basis for an Understanding
There are three other points when considering a work for the basis of an Understanding. These points are not mandatory, but are substantial improvements to the quality of the output. The first concerns the accessibility of the taxonomic resource. Articles published behind paywalls in journals are the lowest quality backings for Understandings, as they often have steep fees associated with access. These fees are a significant impediment to utilisation, especially in areas where there is considerable non-academic research being conducted.

The second point is that the reference material should be directly applicable to the geographic realm of interest. The gold standard for this aspect is that the work should include multiple specimens from that geographic region. If a work does *not* specifically include the subject geographic region, then a separate work should be undertaken to ascertain whether the work does indeed apply to the geographic area. This new work, which can simply reference the taxonomic work and state that the work applies to the region of interest, would then be the basis of the Understanding. In essence, a researcher has taken a piece of work and validated that the work applies to a given area. It is this evidence 

---

# Notes
So at this point we've said what they are and how to get the start point. Now talk about

- What makes a good basis for an Understanding
  - Public access
  - Applicable to the geographic realm
  - Has key for people to follow

After that, I think it's on to the practical running part? Need to give this some thought.

- What to store
- Creation
- Synonyms and resolving

Then move on to complex post initiation operations
- Merge
- Split
- Compound
  - Moving a taxon
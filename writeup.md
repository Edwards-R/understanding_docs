# Understandings: An upgraded system for biological nomenclature

## Abstract
***Make one***

## Introduction
A fundamental aspect of type-based taxonomy is maintaining the linkage between the type nomenclature (what that type is called) against the type concept (what that type represents). This, in theory, allows people from across the world to communicate about types without error. Due to the design of the current type system, however, there exists the potential for the type nomenclature and type concept to diverge under regular usage. This nomenclatural divergence can be caused by taxonomic modifications, which affect all uses of a name, or by regional modifications, which only affect some uses of a name. Both scenarios can present a result in which there exists data under a type's name which no longer matches the type concept, representing a breakdown of the type system.

### Causes of nomenclatural divergence
Due to the nature of their existence, nomenclatural divergences are far more common in less stable regions of taxonomy than in stable regions. The advent of genetic sequencing in particular has caused many nomenclatural divergences to occur, often in otherwise highly stable regions, resulting in significant amounts of invisibly incorrect data. The existence of these divergences, created under correct and valid processes, highlights the fact that it is the fundamental design and utilisation of the taxonomic system which is the root cause of divergence, rather than improper usage of the taxonomic system by the operators. The type concept must be able to evolve in order for taxonomy to function and adjust to our changing understanding of the world around us. Accordingly, the type concept therefore has the potential to exist under multiple *versions* - albeit currently invisibly as no aspect of the type exists to perform version control of the type concept. To rectify this issue the taxonomic system must be updated with version control so that specific versions of the concept may be accurately referenced.

#### Example
|Type name|Version|Current system|New system|
|---|:-:|---|---|
|*Bombus lucorum*| v1 | *Bombus lucorum*| *Bombus lucorum v1* |
| - | v2 | *Bombus lucorum*| *Bombus lucorum v2* |
| - | v3 | *Bombus lucorum*| *Bombus lucorum v3* |

### Regional vs Universal nomenclature divergence
Nomenclatural divergences become more common in regions of the world where the biology is not well understood, as instability is the root cause of divergence. This collection of divergences from poorly-understood areas are not strictly the result of taxonomy - which applies universally - as the divergences often only apply to a limited geographic region. Such regionally-limited divergences impact taxonomy in the same manner as taxonomic divergences, resulting in a mismatch between a type's name and the type concept - albeit only in one specific geographic region. As an example, what was called *Bombus lucorum* in the United Kingdom and Ireland was found to be a mixture of three species: *Bombus lucorum*, *cryptarum*, and *magnus*. These other taxa were already recognised species and well established in other regions, meaning that this *regional* split cannot be considered a *taxonomic* action. Instead, this split must be handled via *nomenclature* as opposed to *taxonomy*.

### Managing nomenclatural divergences
Nomenclatural divergence cannot be avoided, as the divergence results from required functionality in the taxonomic system. However, divergence can be *managed*, and with very little effort. The vast majority of users of the taxonomic system, by volume, do not interact with types but through derivatives, such as keys. These keys are, in the best scenario, derived directly from types (though this is an infrequent event in many disciplines, that does not change the outcome). These derivations, across the spectrum of users, are *interpretations* of the type concept, and it is in this idea that the first step of a solution is found. All uses of nomenclature, other than the singular use of the name at the point of declaration, are indirect references to the type, having gone through *type versioning* and *interpretation* before their use by the eventual end-user. Whilst it will be neccessary to implement version control of types themselves, doing so will almost certainly be a long and drawn-out process. The relevant nomenclatural codes and institutions will need to weigh in on the matter, deliberate and debate the idea etc, before decisions can be arrived at and progress made towards a solution.

While the process of consulting the code, designing and proposing a solution etc is expected to take significant time, there is an urgent need to implement an immediate solution that is capable of stablising the entire system. However, any implementation must a) not interfere at all with the codes and b) not cause future issues that cannot be relatively easily solved.

The answer is to divide the problem into two parts. The first part is the *taxonomy*. This part handles the management of types and available names, and is strictly governed by the codes. The second part is the *interpretation of nomenclature*, which is responsible ensuring that the interpretations of types and usages of associated nomenclature matches, as closely as possible, to the types and names provided by the taxonomy layer. The interpretation layer is not directly governed by the codes but may only make use of types, and names, provided under the taxonomy layer - which *is* governed by the codes. Due to this separation of the overall system into two parts, all modification to biological nomenclature can be placed in the interpretation layer - at least for now. Doing so enables the proposed system to use the existing types, and codes to govern them, whilst solving the problem of nomenclatural divergence and having no impact on the types and/or codes.

As an added positive result, the interpretation layer may be used as a proxy to handle - albeit manually - versioning of the type concept. Having a place to store and manage type concept versioning without needing to interfere with either the codes or existing practices is a significantly desired option, due to the enhanced power it gives the overall system.

## Introducing Understandings
"Understandings", and their associated management system, address the issue of nomenclatural divergence using standard version control methods, coupled with fundamental relational database patterns to assist in providing human-readable identifiers. Understandings do not intervene in the current taxonomic processes, as all Understandings operations happen in the interpretation layer. The result is a light-weight versioning system, backed by proven technology and human-comprehensible identifiers, which does not in any way interfere with any nomenclatural code.
 
Each Understanding refers to a particular interpretation of an application of a type. The Understandings system then provides rules and guidance on how Understandings are managed, in order to maintain their accuracy to types. Within an Understanding system, any member Understanding may be interrogated to find out which currently valid types are contained within that Understanding. As information and knowledge surrounding taxa changes, the Understanding system ensures that nomenclatural changes are applied to member Understandings with the least amount of effort and intervention possible. It should be noted that there are many situations where it will take the redetermination of a specimen (or voucher of a specimen) in order to arrive at a modern single-type interpretation. In such situations, the Understandings system will return the smallest possible collection of potential member types represented by the Understanding.

### How to write Understandings
Understandings come with a default method of being written, though it is anticipated that other formats will develop as more users test the system and identify deficiencies or areas where their field requires different immediate access to details. The default format is called the 'iso format', short for 'In the Sense Of'. Written down, a iso-format Understanding is composed of: `Name: iso. Author: Year: Version`. The author and year refer to the interpretation being referenced, not of the declaration of the type. When read aloud, it is often useful to say the full text 'in the sense of' rather than the abbreviation. Doing so will allow people who are not familiar with Understandings, yet are familiar with taxonomy, to fully understand the intent. For example, `Andrena scottica: iso. Else & Edwards: 2018` can be read as 'Andrena scottica in the sense of Else & Edwards, 2018'.

The name can be a singular entry e.g. `Bombus` or a binomial e.g. `Bombus lucorum`. The most common use of Understandings in the UK Bees, Wasps and Ants Recording Scheme's implementation of Understandings, by far, are binomial Understandings e.g. `Bombus lucorum: iso. Murray et al: 2008`.

### Understandings and types
To the Understandings system, a `type` is an object against which an Understanding may be referenced. As previously mentioned, it is possible to use the Understandings to act as a proxy for properly version controlled types. In order to enable this feature it is neccessary to apply a stricted definition of what a 'type' is in terms of data. A type should, ideally, be composed of the following components:

* The name, author, and year of declaration of the type. This forms the 'identifier' for the type  
* A physical specimen, as well as materials derived from that individual specimen e.g. genetic barcode, whole genome sequence  
* A description which establishes the limits of the taxonomic region claimed by the taxon.

Of these parts, the identifier (name, author, and year) may not be changed. The other two parts may be changed, generating a new Understanding when they are. The strict declaration of these aspects, and their handling, is central to the the core of the Understandings system's background. Notably, the separation of the components enables the safe declaration of a replacement type specimen. All material identified based on a replacement type specimen will be immediately distinguishable from any other type specimen, as the material will use a distinct Understanding. Should an error be made in the assignment of a replacement type specimen, the impact of that error will therefore be minimised and identifiable. Material identified according to the erroneous designation will be immediately apparent, whilst material identified not using the erroneous designation will not be affected at all and may be fully recovered. The ability to safely declare a new type specimen, whilst safeguarding extant data, has been specifically tested in the Understandings system using the British aculeate hymenoptera. The target use cases are:

* types where the type specimen has been lost entirely  
* types where the type specimen has degraded to the point of non-functionality  
* types where the type specimen is non-existent  
* situations where the types descriptions are unclear, overlapping, or unknown

These are all critical use cases found in aculeate hymenopteran taxonomy, where the current system's lack of ability to handle error safely is causing taxonomists to hesitate in conducting broad-scale modernisation of their taxonomy. The publication of 403 new species using 'minimalist revision and description' methods by [Sharkey et al. in 2021](https://zookeys.pensoft.net/article/55600/) raised considerable tensions within the taxonomic community. As an umbrella response, Zamani et al.'s publication '[DNA barcodes on their own are not enough to describe a species](https://resjournals.onlinelibrary.wiley.com/doi/full/10.1111/syen.12538)' covers the critical points in regards to the Understandings system. Notably, Zamani et al. raise the issues of the potential for the creation of a 'parallel' taxonomic system, and the delay that accurate databasing of new taxa creates.

The Understandings system provides a solution to this discussion by enabling users to make the large-scale declarations that Sharkey et al. require, whilst maintaining and protecting existing data as required by Zamani et al.. In addition, the Understandings system provides this extra capability whilst maintaining strict adherence to the existing taxonomic system, without disrupting the nomenclatural codes. By doing so, Understandings protect and elevate the type-based system, preventing a schism from occurring, whilst enabling flexibility in the application of taxonomy.

## What makes a good basis for an Understanding
Every Understanding is based on a particular interpretation of how to apply taxonomic types to the real world. This interpretation must be published so that others may use it, reference it, and critique it, before it can be used as the basis for an Understanding. Different methods of publication, or different choices in what information to contain within a publication, can result in better or worse results. This section details the ways to select the most appropriate, and highest quality, basis for a given Understanding.

There are three points when considering a piece of information for use as the basis of an Understanding. These points are not mandatory, but will produce substantial improvements to the quality of the output in both accuracy and ease of use. It is improbable that references for past Understandings will be able to meet all three criteria, in part due to past conventions. However, it is highly recommended that the basis of any future Understanding fulfills all three criteria. The three criteria highlighted here are required for accurate application of any taxonomic decisions to reality, even in the absence of any Understandings system.

### 1. Accessibility of information
Accessibility of information is divided up into three tiers. The first, and lowest quality, tier is composed of articles which are behind paywalls. These paywalls are frequently of such a magnitude that access to the article is impossible for people who are not members of an academic institution. There are a wealth of articles on how damaging paywalls are to scientific collaboration, particularly in lower-income countries. Furthermore, placing an Understanding, which is designed to be referenced by as many people as possible, behind a paywall is considered, at best, to be a highly damaging move to the respective field.

### 2. Applicable geographic coverage
Reference material utilised in any work used as a basis of Understanding should be directly applicable to the geographic range of the proposed system. The gold standard for this aspect is that the work should include multiple specimens from the geographic region in question. If a work does *not* specifically include the geographic region, then a separate study should be undertaken to ascertain whether the original work does indeed apply to that area. This new study, which can simply reference the original work and state applicability to the region of interest, would then be the basis of the Understanding. In essence, a researcher has taken a piece of work where the applicability to a given region is unknown, then validated that the work applies to a given area. This is in slight contrast with modifications to modifications to a type, which should address the entire geographic range of the taxon.

### 3. Enabling identification
The selected information should enable the identification of the taxa in question. Ideally, this should be the medium of a dichotomous key, or similar level of practical application. Works that only provide genetic or chemical identification methods are accepted, as there are many situations where other identification methods, such as morphological, are not yet discovered. However, works which only provide genetic or chemical methods of identification are considered inferior to those which provide non-laboratory methods, due to the increased cost and difficulty of applying the identification method.

## How to store an Understandings system
There are currently two options for storing Understandings. The first, and by *far* the more complex, is '[NoNomS](https://github.com/Edwards-R/nonoms)' (Normalised Nomenclatural Storage), a PostgreSQL extension purpose-built for Understandings. NoNomS requires a running PostgreSQL server, as well as the SQL knowledge of how to run & control such a database. Setting up and managing a PostgreSQL server will likely require the assistance of a software engineer (or similar). A more accessible, low-tech, option is to run an Understandings system within a spreadsheet. Hopefully in the future there will be greater support for a more user-friendly Understandings platform, but the development of such is outside the scope of planned volunteer time which has produced NoNomS.

The largest challenge associated with a manually-managed Understandings system is the management of large volumes of information without assistance. This is particularly true when making modifications to higher order taxa, where changes must propagate through the child taxa according to strict rules. To mitigate this challenge, it is recommended to limit the scope of a spreadsheet-based Understandings system to one taxonomic rank - likely species. *Do not ignore this recommendation!* Systems which grow beyond the size where they can be managed and supported quickly lose usefulness as they become dated and inaccurate.

### Resolving an Understanding
The first step to interpreting any given Understanding is to identify the current interpretation of that Understanding. This process is called 'resolving' the understanding. 

Each Understanding within a complete Understandings system should have a second Understanding attached to it

### The simplest possible Understandings system
The simplest Understandings system, with the above limitation, can be run in a spreadsheet using two columns. The first column is the Understanding, known simply as the Understanding. The second column is the Understanding which reflects the current interpretation of that Understanding, known as the *Resolved* Understanding. In the case that an Understanding represents the currently correct understanding of how to interpret a type, the Understanding will match the Resolved Understanding.

## Operations within an Understanding system
The Understandings system provides three fundamental operations which may be used to manage Understandings. Each and every operation may only take place upon members of the exact same rank. It is *strictly* forbidden to cross rank when performing operations, as doing so will render the entire system and all data based upon it useless within a very short time. The operations are:

- create
- split
- merge

#### Create
A create operation is used on when the type represented by the Understanding has not ever been present in the region of interest. The predominant example of this is colonisation by a new arrival. The other significant use of the `create` operation is during the initial set up of a new Understandings system. When using `create`, be sure that `split` is not a more applicable operation.

#### Split
A split is the operation to use when it is discovered that what was thought to be one entity is in fact composed of multiple. In addition, a `split` should be preferred over a `create` if the 'novel' taxon has been in any way significantly recorded under an existing Understanding.

#### Merge
A merge is used to combine multiple understandings, within the same parent Understanding (e.g. species within the genus *Bombus: iso. BWARS: 2020*) into one output Understanding.

### Removing Understandings from the Understandings system
Once an Understanding is entered into the Understandings system, that Understanding must never be changed or removed, as there may exist references/uses to that Understanding outside of the system. Removing, or obscuring by changing, any Understanding may lead to a situation where a previously used Understandings no longer has any match within the system.

### Updating the resolved Understanding
The *Resolved Understanding* may be changed at any time to reflect changes in where any given Understanding is currently considered. This enables the Understandings system to consisently send users to the current interpretation of any Understanding.

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

## Compound Understandings
Occasionally it is necessary to create an 'item' which represents multiple Understandings. Note that this does not include aggregates (one taxon is found to be composed of multiple types), but focuses on a deliberate requirement to purposefully compound two well-known and separated Understandings. The two encountered reasons so far as:

- Taxa which cannot be easily separated in a complex
- Hybridisation of taxa
 
Each identified reason has its own creation method. The methods follow similar rulings to Understandings, with the goal of ensuring that compound Understandings are well documented. A compound Understanding should never be 'updated', even in the case of an update to one of the component Understandings. Instead, declare a new compound Understanding using the new component or components or rely on resolving the underlying Understandings.

Compound Understandings do not belong in the same space as Understandings, and must occupy a their own, separated, space.

### Complex
A complex Understanding uses one of the component's names, chosen by the creator of the Understanding. The author and year of a published document that details the components of the compound is then added, forming the trinity of name, author, and year that Understandings rely on. This published document is intended to be purely a reference point, containing only the compound Understanding and its component Understandings. so that other users of the data can use with confidence. Compound Understandings may be internal to a specific project, rather than being defined for the entire scope of the Understandings system. Such is particularly the case with complexes, which may be useful in a project where the participants lack the ability to reliably determine specific taxon confusions.

A complex Understanding is written as

> *Name cpx*: iso. Author: Year

### Hybrid
Hybrid Understandings are for when a specimen is decided to be a hybrid of two taxa. A hybrid Understanding is written as two Understandings, with 'x' in the middle.

> *Name1*: iso. Author1: Year1 x *Name2*: iso. Author2: Year2
---
---
---
## Conclusion
The current nomenclatural system causes the meaning of a taxonomic name to disassociate from the taxon under multiple scenarios. These scenarios are crucial to the continued use of the taxonomic system and therefore cannot be prohibited. The system proposed here recognises these disassociations, as well as their root cause in design, and solves the issue as much as it is possible to be solved. As a result, the nomenclatural and taxonomic system becomes far more robust, dynamic, useful, and accurate. Using Understandings, held in Understandings systems, it is finally possible to construct a truly global database of types, as well as practical, useful, and accurate databases of nomenclature.
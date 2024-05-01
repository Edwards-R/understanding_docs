# How to use Understandings
This document will guide you through the how, why, and when of managing an Understanding system. It does not cover the root 'why' of why Understandings are neccessary.

## What they are
Understandings are a way to, in a standardised, non-taxon-specific manner, differentiate between multiple interpretations of the same taxonomic name. This is achieved by attaching further information to a traditional name e.g. Genus, binomial etc.

## What makes up an Understanding
Understandings consist of four parts:

- Name
- Author
- Year
- Count

### Name
The name of the taxon being referred to

### Author
The author of the Understanding

### Year
The year of the Understanding

### Count
An anti-worst-case measure to manage the incredibly unlikely possibility that two Understandings are created in the same year by people with the same last name and in the same team. For example 'Lorelum / Johnson / 2024' and 'Lorelum / Johnson / 2024'. In such a case, one would be given a `count` of 1, the other 2, entirely at the scheme organiser's/taxon expert's discretion.

The count is ommitted where possible to avoid excessive confusion. Any Understandings with no count attached are considered to have a count of `1` by default.

If the name's parent taxa is different e.g. *Lasius niger* & *Sphecodes niger*, there is no need to ever use counts. Counts are *only* when the parent taxa is *also* identical.

### What are the author and years referring to
These are the author(s) of the work which created the need for a new Understanding, and the year in which it was accepted. The author and year of the *name* in the traditional taxonomic sense does not matter here.

## Directionality of time
It is never acceptable to 're-use' a previous work to attempt to 'restore' a taxon. 

For example, taxon `A` is split into `B`,`C`,`D` and `E`. It is subsequently agreed that this split was in error, and that `A` represents the current interpretation of the taxon. In this scenario, the author and year of `A` **must not be reused**. This is because the work of `A` *does not reflect the split that happened between then and now*.

The correct solution is to publish a new work that outlines the relevant history, states the work that was done to rebuke the split, sets out the new interpretation, name etc, and provides a method to identify the new interpretation. The resulting piece of work then becomes the basis for the Understanding.

It *is*, however, permitted to reference the work that led to `A` in the new work. At the very simplest level, the following text could be considered the basis of a new Understanding:

>The split of `A` was wrong. We looked at the type specimens and a range of specimens collected from the same region and could not reproduce the results. The interpretation of `A` according to *author* is therefore reinstated.

## Geographic restrictions and why they are used
Understanding systems are strictly limited in geographic scope. For example, the BWARS Understanding system only applies to Great Britain, the Channel Isles, and Ireland. The restriction is due to the fact that the *confusions* that Understandings attempt to solve are regional.

### What is the best sized region?
The size of the regions that Understandings apply to are not fixed. Many factors influence the size of these areas, including

- The geographic spread of the taxa in question
- The distance that the taxa regularly travel in their lifetime
- The presence of other taxa with potential for confusion
- Funding
- Expert knowledge
- Willingness to collaborate

As a rule of thumb, the best size is 'as *large* as it can be before running into significant problems'. In order to know whether a problem is significant, ask a relevant expert. Larger systems require less administration but reduce flexibility.

### Different sizes for different taxa
Different taxa within a geographic range will often times work best with differently spatially sized Understanding libraries. For example, 'birds' might operate at a European level whilst 'aculeate hymnoptera' at a country level. This is entirely expected. The simplest solution is to not attempt to try to combine significantly different taxa into 'one solution' as, quite bluntly, there is very little gained and a whole lot lost by doing so.

## Relating an Understandings back to Types
It is possible to relate an Understanding back to a type, but there are certain steps to follow to ensure that this is done correctly. The first and most important is 'resolving'. 'Resolving' is the term used to identify what the current interpretation of a given Understanding is. The process is entirely analogous to resolving synonymy in traditional nomenclature, only applied to Understandings. Understandings are different because they can differentiate between otherwise identical synonyms.

Once an Understanding is resolved, the `name` of the Understanding should match that of the current interpretation of the type.

Take note that relating an Understanding back to a type 'freezes' the information, and the name will no longer update to reflect changes in nomenclature. For this purpose it is recommended to consider such names as 'snapshots' that are frozen in time and will only be correct at the time of freezing. Don't store data in a frozen state unless you are willing to forgoe the benefits of Understandings!

### Why is there not the type author and year in an Understanding?
A frequent question/request is along the lines of '*I want to know which type an Understanding refers to, so that I know I'm talking about the same thing as other people*'. Attempting to place the author and year of the type into an Understanding is however prohibited by the Understanding system, as that would count as a *resolved* Understanding. The entire purpose of Understandings is that they provide the required flexibility for changes to happen in nomenclature while preserving the ability, through resolving, to accurately relate to type/types as per the current knowledge.

## Scoring a source for use in Understandings
Understandings are based on taxonomic and nomenclatural works, but not all works are considered equal for use. There are four metrics which should be considered when debating whether or not a piece of work may be considered for usage as the basis for an Understanding. These are:

- Relevant to the geographic area of the Understanding system in question
- Explicitly looked at significant amounts of material from the geographic region
- Published in an open format i.e. not behind paywalls, so that people may use the work
- Contains an identification key to the change so that peer review is possible

Not all works will fit each point. It is up to the organisers of each individual Understanding scheme to rule on a case-by-case basis.

## What to do when you don't know the source
It is frequently the case, especially for older interpretations, that are no works which will meet the above criteria. In such a case, the best resource to use are commonly used identification keys.

In the absolute worse case, and for synonyms only, use the name of the scheme managing the Understandings. For the year, as close a date as possible to where experts suspect the truth to be, or in extreme cases the year of founding of the scheme. For example, the BWARS Understanding scheme has a number of Understandings attributed to 'BWARS, 2017', which happen where we cannot identify the source of the synonym in question.

## 'iso' format Understandings
The 'iso' - 'In the Sense Of' - is a method for writing Understandings so that they are both human and computer readable. This format consists of the base components of
- the understanding
- the separator
- the format identifier

The 'separator' is used to aid computer interpretation of pure text, akin to the 'comma separated value' format frequently found in data handling. The 'format identifier' is used to denote that the Understanding is being written following a particular format.

For the 'default' iso format, the separator is the `:` character and the format identifier is `iso.`.

The format in entirity takes for the form:

> Name: iso. Author: Year

### Examples
- Bombus: iso. Latreille: 1802
- Pemphredon morio: iso. Dollfuss: 1995
- Bombus lucorum agg: iso. Murray et al: 2008

### Speaking an iso format Understanding
People tend to speak iso format understandings in both the acronym and expanded version. Given the Understanding *Bombus lucorum agg: iso. Murray et al: 2008*, this is typically spoken as either 'Bombus locurum *eye-so* Murray et al, 2008' or 'Bombus lucorum *in the sense of* Murray et al, 2008'. For general purpose where people might not be aware of how Understandings work, using *in the sense of* is better as it draws the listener back to the taxonomic root of how Understandings function. Any taxonomist listening should be able to immediately comprehend the Understanding in question and what types it relates to.

## Aggregates
Aggregates are used when the Understanding contains multiple types. This situation arises only in the case of a split (including when using a split as a compound operation). The use of an aggregate denotes that the Understanding is thought to represent *multiple* types.

# Operations
This section lists the operations that may take place on an Understanding. All operation inputs must be non-aggregates.

## Split
A split occurs when an Understanding that was thought to contain one type has been demonstrated to contain multiple types. The output of a split includes an aggregate Understanding, to which all of the previous data should be automatically redirected to by default. There are as many additional outputs as required by the split. Only currently valid (i.e. non-synonym) non-aggregate Understandings may be split.

|Input|Output|
|---|---|
|A: iso. origin_author: origin_year|A: iso. new_author: new_year|
| | B: iso. new_author: new_year|
| | *N*: iso. new_author: new_year|
| | A agg: iso. newauthor: new_year|

### Significant, widespread confusion
There are situations where there needs to be a decision made between a `split` and a [`create`](#create). For example:
    
>A taxon has recently expanded to the geographic scope of the Understanding system, but was only just found to be there. For a period of time, this new taxon was being recorded as a different, already present, taxon. Should this result in a split, or should the new taxon be added via creation?

The answer to this question is best answered by a question itself:
    
>Does the presence of this new taxon, in the context of the data of the extant taxon, represent **significant, widespread confusion**?

It is ***strongly*** recommended to consult with taxon experts to resolve this question of confusion. Remember that splitting an Understanding invalidates *all* associated data, therefore all other options should be explored prior to splitting. For example, it might be possible to ask recorders to double-check material from the place where the new species arrived, quarantine/suspend potentially suspect data etc. If this *is* the case, then the new taxon can be added as a `create` rather than a `split`. However, do not sacrifice *quality* of data for *volume* of data. If the answer is truly 'we can't tell', then accept the action as a split.

It is always possible to modify the Understanding once again at a later date should new information come to light. *Do not try to pre-optimise for a hypothetical situation*. Understandings are designed to change and manage the effects of change in ways that current taxonomy cannot. Splits that *can* be avoided usually should be avoided, though never at the expensive of accuracy.

## Merge
A merge occurs when what were thought to be multiple types are subsequently considered to be one type. No aggregate is neccessary for this operation. There can be as many input as required, but all inputs *must* be **non-aggregates** and **currently valid** i.e. non-synonym. Aggregates and synonyms cannot participate in a `merge`.

|Input|Output|
|---|---|
|A: iso. origin_author: origin_year|A: iso. new_author: new_year|
|B: iso. origin_author: origin_year||
|*N*: iso. origin_author: origin_year||


## Create
Creates are the rares operation performed, once the system has been populated. Before running a `create`, check whether a [`split`](#split) is more appropriate. `Create` is only for taxa which are *new* to the area **and** have not been significantly recorded as part of any aggregate or complex already.

## Maintenance
`Maintenance` covers all of the odd corrections, errata etc which *can* be performed without causing error. **Perform maintenance operations very *VERY* carefully**. Performing a `maintenance` operation is fraught with risk and the potential to break things, so tread carefully. The best way to use `maintenance` operations is to use them to fix mistakes that were made with other operations, if said operations can't be fixed with a different operation.

## Compound operations
A compound operation is a way to refer to 'operations' that the user sees as one 'action', but to the Understanding system are composed of multiple steps. Such operations are in frequent enough use to require documentation. When faced with an operation that seems as though it does not fit any of the steps outlined above, the first assumption is that the operation requires 'rephrasing' to fit. Should that fail to produce a result, the second assumption is that the operation being examined is in fact a compound operation, composed of multiple operations that need to be conducted in a specific order.

When arranging the order of operations, the priority is always to reduce the complexity of the final output. For example, when given a compound operation that requires the merging of species and the splitting of their genus, the merge should be performed first. Doing so ensures that the new genus has only the 'correct' nomenclature associated with it.

### Example
Annoyingly, I never documented any examples of taxonomists doing this and now the system is clean and running so well that compound operations don't happen. Watch this space.

## Effect on child ranks
When an operation is performed on a rank with a child rank (e.g. `genus` has the child rank `species`), the currently valid members of **all** child Understandings are re-created under the resultant Understanding, utilising the same author and year as the parent operation. Aggregate Understandings are not permitted be transferred and are treated in the same way as synonyms.

That's quite the statement and is best illustrated with an example. This example follows a fictional splitting of the Understanding `Bombus: iso. Latreille: 1802` by the author `Seppo` in `2032`. Only parts of the genus are used to preserve comprehension (there are 82 *Bombus* species Understandings tracked by BWARS!).

*Names in italics are currently valid names*

Names in plain text are synonyms

### Original situation

|***Bombus: iso. Latreille: 1802***|
|---|
|*lucorum: iso. Murray et al: 2008*|
|*pascuorum: iso. Cameron et al: 2007*|
|*muscorum: iso. Cameron et al: 2007*|
|*ruderarius: iso. Cameron et al: 2007*|
|*magnus: iso. Murray et al: 2008*|
|*lucorum agg: iso. Murray et al: 2008*|
|lucorum: iso. Sladen: 1912|
|cryptarum: iso. Rasmont: 1984|
|smithianus: iso. Smith: 1866|
|smithianus: iso. White: 1851|
|scotticus: iso. Pittioni: 1942|

### The operation
Seppo has uncovered that the taxa in the Understanding *Bombus: iso. Latreille: 1802* should be two different genera. The new genus is named 'Neuvobombus', and species are assigned as follows:

|Bombus|Nuevobombus|
|---|---|
|*lucorum: iso. Murray et al: 2008*|*pascuorum: iso. Cameron et al: 2007*|
|*magnus: iso. Murray et al: 2008*|*ruderarius: iso. Cameron et al: 2007*|
||*muscorum: iso. Cameron et al: 2007*|

> Note the absence of *lucorum agg: iso. Murray et al: 2008*

### Creation of new genera
The first stage is the creation of the new Understandings for the genera. These are:

- *Bombus: iso. Seppo: 2032*
- *Nuevobombus: iso. Seppo: 2032*
- *Bombus agg: iso. Seppo: 2032*

### Assignation of subrank
The second stage is to create the currently valid, non-aggregate, child Understandings under their respective parents.

|Bombus: iso. Seppo: 2032|Nuevobombus: iso. Seppo: 2032|
|---|---|
|*lucorum: iso. Seppo: 2032*|*pascuorum: iso. Seppo: 2032*|
|*magnus: iso. Seppo: 2032*|*ruderarius: iso. Seppo: 2032*|
||*muscorum: iso. Seppo: 2032*|

### Demonstration of reasoning
The simplest way to understand the reasoning why this is done is to imagine transferring any of the non-current or aggregate taxa into the new genus Understanding. For an extra helping of the kind of problems that could occur, consider what should be done with each *smithianus* Understanding. Transferring these across would result in:

|Bombus: iso. Seppo: 2032|
|---|
|smithianus: iso. Seppo: 2032|
|smithianus: iso. Seppo: 2032|

Not only are the two Understandings with the same name, author, and year - which breaks the rules of Understandings - but the Understandings are incredibly unlikely to ever be mentioned in the Seppo: 2032 paper. As a rule, taxonomists do not concern themselves with already resolved nomenclature & taxonomy.

Futhermore, *Bombus scotticus: iso. Pittioni: 1942* is a synonym of *Bombus pascuorum: iso. Cameron et al: 2007*. There is, according to all current best practices, no reason to ever make anything called '*Nuevobombus scotticus*'.
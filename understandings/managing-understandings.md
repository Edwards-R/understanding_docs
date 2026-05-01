# Managing Understandings
The Understandings System has very strict rules for how Understandings are to be managed. These rules are designed to create an easy to manage, easy to understand, dictionary of regional nomenclature. In order to maintain any semblance of order, as well as improve usability, certain areas of the Understandings System have been separated out into other documents. Where relevant, the document has been directly linked. If required information is present in another document entirely, that has also been noted in the requiring document.

- Should an operation take place?
    - Systematic, widespread, confusion
        - Systematic
        - Widespread
        - Confusion
- Operations
    - Creation
        - Create
            - As current
            - As synonym
    - Modification
        - Split
        - Merge
            - Name change is a single-input merge
- Change to parent = change to children
    - Tree before & after
        - Solid line = current
        - Dashed line = synonym
    - Why?
        - Maintain all existing names
        - Once a name exists, it may never stop existing
        - Prevent synonyms from transferring 'forward'

## Operations
There are three dominant operations within the Understandings System: [*Create*](operations/create.md), [*Split*](operations/split.md) and [*Merge*](operations/merge.md). Knowing when to use each of these - especially *Create* - is key to running an Understandings System. All operations may only take place within one singular rank. No operation may span multiple ranks.

For details on each operation, please see their respective page.

### Changing a taxon name
Occasionally it is necessary to change the name of a single taxon. For example, what was known in the UK as *Osmia rufa* was in fact *Osmia bicornis*. In such a situation, the operation to use is a merge with a single input.

## Changes to child taxa
When changing a taxon, all currently valid, non-aggregate, children of that taxon are recreated under the new taxon. This action is performed in order to maintain the continuity of existing nomenclature whilst adding the absolute minimum of new information.

### Example
This example shows a hypothetical change from *Psenulus: iso. Richards: 1980* to *Psenobus: iso. Edwards: 2026*. The following table outlines the starting conditions.

|Genus|Taxon|Current|Status|
|:-:|---|---|---|
|Psenulus: iso. Richards: 1980|Psenulus chevrieri: iso. Schmid-Egger: 2016|Psenulus chevrieri: iso. Schmid-Egger: 2016|Current|
|"|Psenulus pallipes: iso. Schmid-Egger: 2016|Psenulus pallipes: iso. Schmid-Egger: 2016|Current|
|"|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Current|
|"|Psenulus schencki: iso. Richards: 1980|Psenulus schencki: iso. Richards: 1980|Current|
|"|Psenulus concolor: iso. Richards: 1980|Psenulus concolor: iso. Richards: 1980|Current|
|"|Psenulus pallipes: iso. Richards: 1980|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Synonym|
|"|Psenulus rubicola: iso. Unknown: 0|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Synonym|
|"|Psenulus brevitarsis: iso. Unknown: 0|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Synonym|

When the genus is changed to *Psenobus: iso. Edwards: 2026*, we first start with declaring the currently valid, non-aggregate, taxa under the new genus. The Understanding author and year are those of the parent change.

|Genus|Taxon|Current|Status|
|:-:|---|---|---|
|Psenobus: iso. Edwards: 2026|Psenobus chevrieri: iso. Edwards: 2026|Psenobus chevrieri: iso. Edwards: 2026|Current|
|"|Psenobus pallipes: iso. Edwards: 2026|Psenobus pallipes: iso. Edwards: 2026|Current|
|"|Psenobus schencki: iso. Edwards: 2026|Psenobus schencki: iso. Edwards: 2026|Current|
|"|Psenobus concolor: iso. Edwards: 2026|Psenobus concolor: iso. Edwards: 2026|Current|

We then redirect the prior taxa accordingly, leaving the aggregate untouched:

|Genus|Taxon|Current|Status|
|:-:|---|---|---|
|Psenobus: iso. Edwards: 2026|Psenobus chevrieri: iso. Edwards: 2026|Psenobus chevrieri: iso. Edwards: 2026|Current|
|"|Psenobus pallipes: iso. Edwards: 2026|Psenobus pallipes: iso. Edwards: 2026|Current|
|"|Psenobus schencki: iso. Edwards: 2026|Psenobus schencki: iso. Edwards: 2026|Current|
|"|Psenobus concolor: iso. Edwards: 2026|Psenobus concolor: iso. Edwards: 2026|Current|
|Psenulus: iso. Richards: 1980|Psenulus chevrieri: iso. Schmid-Egger: 2016|Psenobus chevrieri: iso. Edwards: 2026|Synonym|
|"|Psenulus pallipes: iso. Schmid-Egger: 2016|Psenobus schencki: iso. Edwards: 2026|Synonym|
|"|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Current|
|"|Psenulus schencki: iso. Richards: 1980|Psenobus schencki: iso. Edwards: 2026|Synonym|
|"|Psenulus concolor: iso. Richards: 1980|Psenobus concolor: iso. Edwards: 2026|Synonym|
|"|Psenulus pallipes: iso. Richards: 1980|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Synonym|
|"|Psenulus rubicola: iso. Unknown: 0|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Synonym|
|"|Psenulus brevitarsis: iso. Unknown: 0|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Synonym|

All new nomenclature is now added, and all existing nomenclature now directs to the most precise result.

### Resolving the components of the aggregate
> This section requires knowledge ['finding the components of an aggregate'](aggregates-complexes.md#storing-the-components-of-an-aggregate).

Now that we are modifying, we need to add an additional step to finding the components of an aggregate: resolving the components after selection. Previous the workflow was:
- Resolve the Understanding
- Find the components

With the knowledge in this document we can see that this is no longer sufficient. Identifying the components of Psenulus pallipes agg: iso. Schmid-Egger: 2016 would give us:

- Psenulus pallipes: iso. Schmid-Egger: 2016
- Psenulus chevrieri: iso. Schmid-Egger: 2016

However, these are now both synonyms, so we must resolve once more to get the current interpretations:

- Psenobus pallipes: iso. Edwards: 2026
- Psenobus chevrieri: iso. Edwards: 2026

The workflow is therefore:
- Resolve the Understanding
- Find the components
- Resolve the components

Doing these three steps wll give the most modern interpretation of the components of any Understanding.

## Forward progression only
It is never permitted to directly 'roll back' any change to an Understanding. Any time there is a change, a new Understanding must be created.

For example, to reverse the change of Psenulus: iso. Richards: 1980 to Psenobus: iso. Edwards: 2026, it is not permitted to re-elevate Psenulus: iso. Richards: 1980 to the current genus, alongside all nomenclature. Instead, a new Understanding must be declared. As we are changing a name, we can use a [merge](operations/merge.md) with a single input. The Understanding for this example will be Smith: 2026, giving Psenulus: iso. Smith: 2026.

> This Understanding means that Smith looked at Edwards's work in 2026 and disagreed with the change. Accordingly, Smith decreed that *Psenulus* was the correct name, not *Psenobus*.

Following the same steps as above, this grants the following direct creations:

|Genus|Taxon|Current|Status|
|:-:|---|---|---|
|Psenulus: iso. Smith: 2026|Psenulus chevrieri: iso. Smith: 2026|Psenulus chevrieri: iso. Smith: 2026|Current|
|"|Psenulus pallipes: iso. Smith: 2026|Psenulus pallipes: iso. Smith: 2026|Current|
|"|Psenulus schencki: iso. Smith: 2026|Psenulus schencki: iso. Smith: 2026|Current|
|"|Psenulus concolor: iso. Smith: 2026|Psenulus concolor: iso. Smith: 2026|Current|

We then once again redirect the prior taxa accordingly, leaving the aggregate untouched:

|Genus|Taxon|Current|Status|
|:-:|---|---|---|
|Psenulus: iso. Smith: 2026|Psenulus chevrieri: iso. Smith: 2026|Psenulus chevrieri: iso. Smith: 2026|Current|
|"|Psenulus pallipes: iso. Smith: 2026|Psenulus pallipes: iso. Smith: 2026|Current|
|"|Psenulus schencki: iso. Smith: 2026|Psenulus schencki: iso. Smith: 2026|Current|
|"|Psenulus concolor: iso. Smith: 2026|Psenulus concolor: iso. Smith: 2026|Current|
|Psenobus: iso. Edwards: 2026|Psenobus chevrieri: iso. Edwards: 2026|Psenulus chevrieri: iso. Smith: 2026|Synonym|
|"|Psenobus pallipes: iso. Edwards: 2026|Psenulus pallipes: iso. Smith: 2026|Synonym|
|"|Psenobus schencki: iso. Edwards: 2026|Psenulus schencki: iso. Smith: 2026|Synonym|
|"|Psenobus concolor: iso. Edwards: 2026|Psenulus concolor: iso. Smith: 2026|Synonym|
|Psenulus: iso. Richards: 1980|Psenulus chevrieri: iso. Schmid-Egger: 2016|Psenobus chevrieri: iso. Smith: 2026|Synonym|
|"|Psenulus pallipes: iso. Schmid-Egger: 2016|Psenulus schencki: iso. Smith: 2026|Synonym|
|"|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Current|
|"|Psenulus schencki: iso. Richards: 1980|Psenulus schencki: iso. Smith: 2026|Synonym|
|"|Psenulus concolor: iso. Richards: 1980|Psenulus concolor: iso. Smith: 2026|Synonym|
|"|Psenulus pallipes: iso. Richards: 1980|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Synonym|
|"|Psenulus rubicola: iso. Unknown: 0|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Synonym|
|"|Psenulus brevitarsis: iso. Unknown: 0|Psenulus pallipes agg: iso. Schmid-Egger: 2016|Synonym|

### Explanation
Whilst the result of requiring forward progression may look complex, it is the only method to maintain complete data accuracy in the face of uncertainty. Anyone, at any point, may make a mistake declaring an Understanding. Allowing the reversion of an Understanding creates the chance of significant widespread confusion being introduced.

If reversion is allowed, if A is changed to B, then that change revoked, then that from B to A change revoked, there is no way to recover the original A. There are two Understandings with the same name, which defeats the entire purpose of Understandings.

### Handling the volume of nomenclature
Once an Understandings implementation reaches this point it is almost mandatory to use an automated management system instead of manual management. A good automated system runs on the three operations (create, merge, split) for the vast majority of the time. Forward progression and child taxon management can both be entirely handled by logical code, leaving the human operator the far simpler task of managing the operations. In order to understand this, it is recommended to read [how the Understandings System handles ranks](ranks.md).
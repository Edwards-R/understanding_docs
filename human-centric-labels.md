# Human-centric labels
Previously, we arrived at a way to version types and interpretations in order to solve nomenclatural divergence. However, the labelling of these versions was very rudimentary. Using pure numbers (v1, v2, v3 etc) may be logically complete, but it is typically more difficult for humans to remember the exact meaning of what a given number refers to. In order to significantly improve the usability of our proposed modification, a different solution to version identification must be found.

## Borrowing from what already exists
Luckily for us, there already exists a precedent for human-centric versioning within the field of taxonomy. Homonym taxa arise from a situation in which the same name is given to two different taxa. For example, *Ransonia* has been used a genus in two situations (see [Tonini et al](https://doi.org/10.11646/zootaxa.4097.1.7)). To pre-emptively enable such mistakes to be identified and rectified, each taxon name has the author and year of declaration attached:

|Name|Author|Year|
|:-:|:-:|:-:|
|Ransonia|Kramp|1947|
|Ransonia|Blandin|1979|

This 'author & year' system is familiar to taxonomists, human-readable, and reasonably unique. As such, it provides an excellent basis for adaptation to use when versioning type concepts and interpretations.

## Stacking up the versions
Under the redesign of the taxonomic system, the 'root' component of a type is its name. The author and year stored against a type under the current system become the author and year stored specifically against the name in the redesign. We can use this to build up a complete, documented, statement as to the status of *Bombus lucorum* in Great Britain. We start with the type name *Bombus lucorum*:

|Attribute|Value|
|:--|--:|
|Name|*Bombus lucorum*|
|Name author|Linnaeus|
|Name year|1761|

Attached to this is a version of the taxon concept. Latreille, in 1802, moved this species to Bombus. As such, Latreille is the author of the current concept.

|Attribute|Value|
|:--|--:|
|Concept author|Latreille|
|Concept year|1802|

The latest interpretation of this concept within the area of Great Britain is by Murray et al in 2008.

|Attribute|Value|
|:--|--:|
|Interpretation author|Murray et al|
|Interpretation year|2008|

These three components can be stacked together to provide a complete statement for the current interpretation of *Bombus lucorum* in Great Britain:

|Attribute|Value|
|:--|--:|
|Name|*Bombus lucorum*|
|Name author|Linnaeus|
|Name year|1761|
|Concept author|Latreille|
|Concept year|1802|
|Interpretation author|Murray et al|
|Interpretation year|2008|

### In case of emergency, add number
There exists the possibility, extremely slight as it may be, that a singular type is worked on by multiple people with the same surnames in the same year. Such a situation is far more probable in cultures where surnames are less individualistic. For example, if Wang, 2025 published a paper on *Bombus*, which was quickly followed by Wang, 2025, who refuted the work then we have:

|Name|Author|Year|
|---|---|---|
|Bombus|Wang|2025|
|Bombus|Wang|2025|

Once again, we have a disjunction: the name, author, and year are identical whilst the meaning changes. In such a scenario, it is appropriate to use the time-honoured fallback of *version numbers*.

|Name|Author|Year|Version|
|---|---|---|:-:|
|Bombus|Wang|2025|1|
|Bombus|Wang|2025|2|

Version numbers are far from ideal, but given the alternatives are:

- Force people to change their own name (Wang -> Smith)
- Force people to delay publications to the next year (2025 -> 2026)

then the use of a number is by far the least disruptive option. The most useful aspect is that, should such an occurrence become more prevalent, the scientific community is likely to adapt scientific references to cope. The taxonomic/interpretation system can then adopt whichever reference system prevails, maintaining parity with scientific referencing. Until then, the very occasional number is the price to pay for accuracy.

### Default index to 1
In the absence of any known duplication of work, the default assumed number should be `1`. This default *does not need to be stated* under regular use. Whilst this is contrary to regular design patterns, the number exists as a solution to a *hypothetical* situation which is anticipated to be extremely rare. Requiring such 'dead' information to always be included is merely adding burden for extremely minimal gain.

## What about DoI/ISBN/ISSN?
Whilst it is a good idea to store identifiers like DoI/ISBN/ISSN alongside changes, these belong in a dedicated storage rather than being attached to the name itself. None of the above identifiers are *human readable*, being designed for machine-facilitated searching instead. The goal of the system being proposed here is that it is inherently human-friendly.

## Conclusion
Using a hybrid of existing taxonomic versioning and scientific reference systems, we have produced a clean and simple version identifier. We have also identified the three tiers of versioning which need to be created as the type name, type concept, and interpretations. However, our example specifically mentions the interpretation to be in the GB context only. Why is this, and what are the implications for maintaining a globally-applicable taxon list?

[Next page](./interpretation-regions.md)
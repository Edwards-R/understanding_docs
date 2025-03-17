# Human-centric labels
Previous results gave us a way to place version labels on both the type and interpretations of the type. However, the labels are very rudimentary and very much need improvement. In particular, anything to help anchor the versions to a more human-centric, familiar object would be useful

## Borrowing from what already exists
Luckily for us, there already exists a precedent for human-centric versioning within the field of taxonomy. Each type has, attached to the name, the author and year of declaration of that type. This information serves to distinguish that particular version from other versions of that name. Whilst modern controls have largely eliminated the need for this distinction in the current age, the practice holds on for the few cases where it *is* neccessary to distinguish between multiple versions of the same name.

However, we can improve on this slightly. Scientific reference systems operate on the same protocol. As an example, this site could be referred to as *Edwards, 2025*. By specifically adopting a referencing system as our identifier, we can anchor a version to a published, ideally accessible, piece of work that contains the in-depth information on how that version differs from the previous.

### What about DoI/ISBN/ISSN?
Whilst it is a good idea to store identifiers like DoI/ISBN/ISSN alongside changes, these belong in a dedicated storage rather than being attached to the name itself. None of the above identifiers are *human readable*, being designed for machine-facilitated searching instead.

### In case of emergency, add number
There exists the possibility, extremely slight as it may be, that a singular type is worked on by people with the same surnames in the same year. Such a situation is far more probable in cultures where surnames are less individualistic. For example, if Wang, 2025 published a paper on *Bombus*, which was quickly followed by Wang, 2025, who refuted the work then we have:

|Name|Author|Year|
|---|---|---|
|Bombus|Wang|2025|
|Bombus|Wang|2025|

Once again, we have a disjunction. The name, author, and year are identical whilst the meaning changes. In such a scenario, it is appropriate to use the time-honoured fallback of *version numbers*.

|Name|Author|Year|Version|
|---|---|---|:-:|
|Bombus|Wang|2025|1|
|Bombus|Wang|2025|2|

Version numbers are far from ideal, but given the alternatives are:

- Force people to change their own name
- Force people to delay publication

then the use a number is by far the least disruptive option. The most useful aspect is that, should such an occurrence become more prevalent, the scientific community is likely to adapt references to cope. We can then simply adopt whichever reference system prevails. Until then, the very occasional number is the price to pay.

### Default index to 1
In the absence of any known duplication of work, the default assumed number should be `1`. This default *does not need to be stated* under regular use. Whilst this is contrary to regular design patterns, the number exists as a solution to a *hypothetical* situation which is anticipated to be extremely rare. Requiring such 'dead' information to always be included is merely adding burden for extremely minimal gain.

## So what does this look like?
Firstly, we find the version information for the type itself. This information *may* be the same as the declaration of the type itself, but quite frequently it is not. The methods by which this can change are the subject for later discussion, for now it is enough to know that the information is distinct. For example:

|Attribute|Value|
|---|---|
|Name| *Bombus* |
|Version author| *Example* |
|Version year| *2025* |
|(*Version number)*|*1*|

Simple, familiar, and concise.


## Separate the concerns
The supplementary information is the same for objects in both the taxonomic and interpretation areas. Whilst we may have solved the problem of identifying the correct information to include, we still do not have a clear way of indicating whether the information belongs to the taxonomic or interpretation area. This is the next step to be solved in our goal for clear and concise information.

## Conclusion
Using a hybrid of existing taxonomic versioning and scientific reference systems, we have a clean and simple version identifier. The identifier is usable as a reference to a scientific explanation of the change which has produced the version. However, protocols to differentiate between the taxonomic and interpretation layers, as both use the same suite of information to distinguish between versions.

[Next page](./separating-areas.md)
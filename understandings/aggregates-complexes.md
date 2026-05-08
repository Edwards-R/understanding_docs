# Aggregates and Complexes
Occasionally it is required to be able to represent multiple Understandings by one Understanding. The two situations supported by the Understandings System are called *aggregate* and *complex*.

## Aggregate
An aggregate is used where a *nomenclatural* or *taxonomic* change has resulted in one Understanding representing multiple taxa. This happens as the result of a *split* operation. As part of the split operation, an aggregate Understanding is created to denote that there exists data where the exact Understanding is unknown.

The example below shows the split of Bombus lucorum: iso. Sladen: 1912 by Murray et al, 2008. The three new end points are created, as well as an aggregate. All data from Bombus lucorum: iso. Sladen: 1912 will resolve to Bombus lucorum agg: iso. Murray et al: 2008. Users of data utilising Bombus lucorum: iso: Sladen: 1912 are therefore informed that the Understanding they are using has been split.

```
Bombus lucorum: iso. Sladen: 1912 ------->> Bombus lucorum agg: iso. Murray et al: 2008

                                            Bombus lucorum: iso. Murray et al: 2008
                                            Bombus magnus: iso. Murray et al: 2008
                                            Bombus cryptarum: iso. Murray et al: 2008
```

### Storing the components of an aggregate
The Understandings System maintains a table of all components of every aggregate. This table can be queried, at any time, to find the components of any given Understanding. For the example above, the table would contain the following:

|Target Understanding|Component Understanding|
|---|---|
|Bombus lucorum agg: iso. Murray et al: 2008|Bombus lucorum: iso. Murray et al: 2008|
|---|Bombus magnus: iso. Murray et al: 2008|
|---|Bombus cryptarum: iso. Murray et al: 2008|

Note that Understandings must be resolved *prior* to checking their components, otherwise the result will provide the components of the pre-resolution target. For almost all end-user scenarios, the resolved Understanding is the desired target.

## Complexes
It is frequently the case that users need a way to 'lump' taxa together. This action is particularly prevalent where there are taxa which are difficult to separate with a given identification method. Complexes, denoted with the suffix `cpx` are designed for this use case.

A complex is a *project-specific* grouping of Understandings. The contents of a complex must be stated where the complex is declared, in the same way as an aggregate. If declaring a complex of Lasioglossum calceatum: iso. Amiet et al: 2001 & Lasioglossum albipes: iso. Amiet et al: 2001, as part of a 2026 BWARS project, this would be declared as:

|Target Understanding|Component Understanding|
|---|---|
|Lasioglossum albipes cpx: iso. BWARS: 2026|Lasioglossum albipes: iso. Amiet et al: 2001|
|---|Lasioglossum calceatum: iso. Amiet et al: 2001|

This placement of this declaration will be dependent on the publishing requirements of the different journals. In general, unless the complex is especially important to the work, it is recommended to place the definitions in a supplementary document. Re-using declarations is also possible, even from other sources, if the same complex definition documentation is used. It is expected that a generic 'useful complexes' document will exist, compiled for a specific taxonomic group at a specific date. These generic documents will then be used by multiple other projects.

### Naming a complex
When naming a complex, a simplified subset of nomenclatural rulings apply. The oldest Understanding, by year only, takes priority. In cases where the year of all component Understandings is identical, the first alphabetically becomes the complex name.

## Aggregate or complex?
There are scenarios where there may exist the option to use an aggregate rather than a complex. In such situations, use the aggregate rather than declare a new complex. It is always simpler to have fewer custom parts.

## Next topic
The next topic is [how to efficiently start a new Understandings System](./efficient-start.md)
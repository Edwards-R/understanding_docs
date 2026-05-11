---
title: Interpretations, Understandings, and the Understandings System
nav_order: 1
---

# Interpretations, Understandings, and the Understandings System
This site is the documentation for Interpretations, and the Understandings system. This combination of projects is a full rework of how Linnaean taxonomy is handled, designed to remove a set of flaws which are currently passively destroying biological data viability.

## Interpretations
The foundational examination of the problem in the Linnaean taxonomic system, followed by an in-depth explanation of each aspect and it's industry-standard solution.

- [1. Introduction](/interpretations/introduction.md)
- [2. Nomenclatural Divergence](/interpretations/nomenclatural-divergence.md)
- [3. Layers in taxonomy](/interpretations//layers-in-taxonomy.md)
- [4. Human-centric labels](/interpretations//human-centric-labels.md)
- [5. Interpretation regions](/interpretations//interpretation-regions.md)
- [6. Resolving interpretations](/interpretations//resolving-interpretations.md)
- [7. Guidelines for publishing a new interpretation](./interpretations/publishing-a-new-interpretation.md)
- [8. How to add interpretations to exist keys](./interpretations/adding-interpretations-to-existing-keys.md)

## Understandings System
The Understandings System is a complete implementation of Interpretations, providing a practical structure and ruleset to follow. This section is less linear and is designed to also be usable as a reference guide.

- [1. Introduction](/understandings/intro.md)
- [2. Writing an Understanding in the `iso` format](/understandings/iso-system.md)
- [3. Managing Understandings](/understandings/managing-understandings.md)
-  ### Operations
    - [3.1 Create](/understandings/operations/create.md)
    - [3.2 Split](/understandings/operations/split.md)
    - [3.3 Merge](/understandings/operations/merge.md)
    - [3.4 Redirect](/understandings/operations/redirect.md)
    - [3.5 Add to aggregate (WIP)](/understandings/operations/add-to-agg.md)
- [4. Ranks in the Understandings System](/understandings/ranks.md)
- [5. Aggregates and Complexes](/understandings/aggregates-complexes.md)
- [6. How to efficiently start up a new Understandings System](/understandings/efficient-start.md)

## Case Study: BWARS
Interpretations and the Understandings System were developed on the UK Bees Wasps and Ants Recording Society (BWARS) dataset. The relevant parts of that process (i.e. the ones that actually worked) have been extracted and placed in a case study that covers the creation of the BWARS Understandings System implementation.

[Read the case study here](/understandings/case_study/BWARS.md)

### NoNomS

The code used by the BWARS Understandings System is called NoNomS - **No**rmalised **Nom**enclature **S**torage. It is a PostgreSQL plugin that handles the vast majority of the setup and maintenance of an Understandings System. The NoNomS project is open source and [can be found here](https://github.com/Edwards-R/nonoms).

If you like NoNomS and want to use PostgreSQL for your biological recording (which you should, it's perfect) then [Bio Rec](https://github.com/Edwards-R/bio_rec) may also be of interest to you. Bio Rec handles biological occurrence data and is designed to rely on NoNomS for taxonomic management.
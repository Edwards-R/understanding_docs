# Readme

This project is a documentation of the problems that exist when trying to store [taxonomically-adjacent](./glossary.md#taxonomically-adjacent) data for long periods of time, as well as a robust, easy-to-implement solution to solve all system-related problems.

## What's the problem

### The short version for an engineer
Scientific nomenclature is in second normal form. For example, I can't rely on a binomial to consistently relate to a singular type. Not being able to keep the relationship to the type means that I can't do anything safely. Automated verification, automated assessment, threat assessments e.g. Red Listing, it's all of it un-automatable. The whole system doesn't get treated as a system but a magic kludge that 'just works, somehow' - except it doesn't work.

This system here is a fix to that. It will work within very specifically defined rules. It will be ***strict***, whilst providing a framework by which users can implement the less-than-strict actions that are in common use.

### The short version for a non-engineer
When someone stores some taxonomic data, for example the binomial *Bombus lucorum*, it is expected that all *other* pieces of information for that taxon refer to the same *idea*. I *should* be able to look at all other data for *Bombus lucorum* and be able to compare and contrast. ***Anyone*** who has had the misfortune of working with data containing taxonomic nomenclature of a sufficient age knows that this idea is a pipe dream. People can waste weeks if not *months* attempting to resolve a given dataset to modern taxonomy. This translation is often done poorly by non-taxon-specialist users because the resources that are used can't tell them how it works to begin with.

I've had enough of that. It's annoying, it's irritating, and it's all down to a *very* simple design flaw in how hierarchical 'Linnaean-style' taxonomy is organised.

It means a few changes to how things are done. Things are going to get a lot **stricter** and names are going to get a bit longer, but the core ideas of anything that can be done now will still be able to be done in the new system. Some might just have no oversight at all, which is honestly fine since there wasn't any effective oversight to begin with. Others will involve devolved oversight where it's useful for taxa-specific things.
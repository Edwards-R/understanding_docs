# Readme

This project is a documentation of the problems that exist when trying to store [taxonomically-adjacent](./glossary.md#taxonomically-adjacent) data for long periods of time, as well as a robust, easy-to-implement solution to solve all system-related problems.

## What's the problem

### The short version for an engineer
Scientific nomenclature is in second normal form. This means that I can't rely on a binomial to consistently relate to a singular type, which is ***the** most important thing*. Not being able to keep the relationship to the type means that I can't do anything safely. Automated verification, automated assessment, threat assessments e.g. Red Listing, it's all of it un-automatable. Just *looking* for a record of a species is dangerous. The whole system gets treated as a magical mystery box that 'just works, somehow' - except it doesn't work and is constantly losing data.

The Understandings system is a fix to that by making the entire thing 3NF and best-practice compliant. Relationships are maintained, modifications strictly managed, and primary keys maintained as keys and not meanings. It will be ***strict***, whilst providing a framework by which users can implement the less-than-strict actions that are in common use.

### The short version for a non-engineer
When someone stores some taxonomic data, for example the binomial *Bombus lucorum*, it is expected that all *other* pieces of information for that taxon refer to the same *idea*. I *should* be able to look at all other data for *Bombus lucorum* and be able to compare and contrast. ***Anyone*** who has had the misfortune of working with data containing taxonomic nomenclature of a sufficient age knows that this idea is a pipe dream. People can waste weeks if not *months* attempting to resolve a given dataset to modern taxonomy. This translation is often done poorly by non-taxon-specialist users because the resources that are used can't tell them how it works to begin with.

I've had enough of that. It's annoying, it's irritating, and it's all down to a few *very* simple design flaws in how hierarchical 'Linnaean-style' taxonomy is organised.

It means a few changes to how things are done. Things are going to get a lot **stricter** and names are going to get a bit longer, but the core ideal of 'this is a group of organisms, represented by a singular ideal, with a given name' will remain. Types will ***not*** be removed, added, or modified. What a type *is*, however **will** be modified because the current system is nowhere near strict enough in handling them. Regardless of which, this new system does not need any re-declaration of types. If any redeclaration needs to happen however, this system is *much* better at actually keeping track of the fact and the repercussions of doing so. Not particularly hard, since the current system's 'keeping track' relies on 'well, you know if you know, otherwise you don't'.

## This is all new and scary and *X* exists to deal with it
New? Yes. Scary? Not really. *X* exists to deal with it? Not as far as I've tried, and believe me I have *tried*.

Take the Red List criteria for example. The guidance documentation requires a 'taxon authority list' in order for a Red List to be accepted. Why does it need this? Because the binomials it otherwise uses are insufficient for people to compare across regions and time. Understandings are a step *up* from this and can be thought of as embedding the taxon authority into the name itself rather than relying on a separate document. Both system still need someone to track the evolution of nomenclature against taxonomy, but Understandings are one less document than binomials.

## Yes but we already solve this using *X*
### Sensu stricto/senu lato
Only works once. Taxon *X* gets split into *X* s.s. and *X* s.l.. This can fail in two ways.

First of all, immediately post-split there exist records of:

- *X*
- *X* s.l.
- *X* s.s.

Fine, you might say, all *X* are *X* s.l..

Well what happens over time? The epithet gets dropped by people who never knew the taxon as anything *other* than as the new '*X* s.l.'. So now you have:

- *X*
- *X* s.l.
- *X* s.s.
- *X*

Well what if we keep it and force the epithet?

To start with, that's tantamount to changing the entire name officially. That's not a good idea when the desire is stability. Secondly, what happens when a taxon is split multiple times? If we split *X* s.s. once more, what do we get? *X* s.s. s.l. and *X* s.s. s.s. ? There's just no solution that works here.
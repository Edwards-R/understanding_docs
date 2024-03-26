# Introducing Understandings
Understandings are the simplest and most elegant solution to the [problems outlined](./heirarchical_linnaean.md) in the current hierarchical system.

## For system designers/architects
In system design terms, the Understanding system is an implementation of E.F. Codd's third normal form, coupled with the principle of extensibility to enable the use of all existing taxonomic data with the least amount of work.

## For bioinformatics
The most common point of reference for non system designers is likely R's `tidyverse` ecosystem. Tidy data is, [quite literally](https://tidyr.tidyverse.org/articles/tidy-data.html), an embodiment of E.F. Codd's third normal form. Understandings are the 'tidyverse' equivalent of nomenclature. The system also extends into taxonomy, but that is far more in-depth than most users will need.

The principle of extensibility means that the system is designed to be used ontop of as much existing infrastructure as possible. Moving from a typical 'binomial' system to 'binomial Understanding' system only requires the creation of the Understandings and nothing else. As a result, upgrading such a system is incredibly simple to do. Furthermore, an upgraded binomial Understanding system *can* still communicate with a binomial system. It probably *shouldn't*, due to the loss of information in de-transitioning back to binomials, but it could.

## For everyone else
The largest problem we have with storing data relating to taxa is that we can't rely on binomials (e.g. *Bombus lucorum*) to 'stay' correct. There are a host of, entirely supportable and reasonable, processes by which changes can happen. Understandings use some very *very* fundamental logic rules to create ways to ensure that we have a way to refer to a taxon *as precisely as possible* in the event of any changes.

Most importantly, the changes that we make so that we can refer to taxa *precisely* build from the current system. For example, Understandings

- are founded on types
- use ranks
- use accepted scientific nomenclature
- work with binomials

## What does an Understanding look like?
An Understanding is composed of three parts:
- The taxon name
- The author of the Understanding
- The year of publication of the Understanding

That's it.

### A few examples
|Part|Entry|
|---|---|
|Taxon|Bombus|
|Author|Latreille|
|Year|1802|

|Part|Entry|
|---|---|
|Taxon|Bombus lucorum|
|Author|Murray et al|
|Year|2008|

## How to write an Understanding
Understandings can be written in many ways. The 'default' way that comes with Understandings is known as the 'iso' format. The acroynm 'iso' standards for 'In the Sense Of'.

An iso-format Understanding conists of:
- the three parts that comprise an Understanding
- an additional 'identifier' that denotes the format
- a 'separator' character to enable machine interpretation

For an 'iso' format Understanding, the separator is `iso.` and the separator is `:`. Assembled together, an iso-format Understanding follows the pattern:

*Taxon*: iso. *Author*: *Year*

Please see [rules for Understandings](./Rules%20for%20Understandings.md) for a breakdown of the actions that result in new Understandings being created.

### A few examples
Bombus: iso. Latreille: 1802

*Bombus lucorum*: iso. Murray et al: 2008

## What happens if there are two Understandings with the same taxon, author, and year?
Whilst this is a *very* unlikely situation to occur, it is still theoretically possible to occur. In such a situation, the Understandings would get an incrementing counter added:

|Part|
|---|
|Taxon|
|Author|
|Year|
|Count|

### Theoretical iso format
Whilst none exist as of time of writing, an iso format would convert the 'count' from integer to capital-case character, starting on 'A' to promote visibility. For comparison:

*Loremus ipsuma*: iso. Dolorem: 1524: 1

vs

*Loremus ipsuma*: iso. Dolorem: 1524: A

Utilisation of a number for the count tends to blend into the year, hence the translation to upper-case character.

### Running out of characters
If you find yourself running out of characters to write an iso-format Understanding then something has gone horribly wrong outside of the system and a taxonomist needs to step in.

The only advice I can offer you is 'Good luck, you seem to need it'.
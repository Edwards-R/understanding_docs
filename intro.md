# Understandings - A way to solve long term nomenclatural and taxonomic instability in data

Understandings are an extension, with very slight modification, to the existing biological nomenclatural structure. The purpose of Understandings is to ensure complete type adherence in stored and un-managed data sets with the most minimal of efforts. Such a task is accomplished by the implementation of well-established relational data design patterns.

> There is only ever one correct specimen of a given taxon: the type. The rest is approximation.

## Problems in data
In 2008, [the taxon *Bombus lucorum* was split in Great Britain](https://www.semanticscholar.org/paper/Cryptic-species-diversity-in-a-widespread-bumble-Murray-Fitzpatrick/d038a049538362088065e9d493e446d041402747). This change was not surprising to many experts in the identification of the taxon and had indeed been proposed multiple times previously. It was, however, the first experiment to *conclusively* demonstrate the separation. The short version of this event is that Murray et al demonstrated that the material identified as *Bombus lucorum* in Great Britain and Ireland *also* contained *Bombus magnus* and *Bombus cryptarum*. As a result, every single record of *Bombus lucorum* prior to this work requires redetermination using genetic or chemical analysis to establish whether or not it truly is *Bombus lucorum*. The list of affected works include:

- All records submitted to the various biological recording schemes
- All scientific papers that reference *Bombus lucorum*
- All museum collections that include specimens of *Bombus lucorum*
- All private collections that include specimens of *Bombus lucorum*
- All taxon experts who are creating records and specimens of *Bombus lucorum*

Each and every single one of these items must, under the extant taxonomic/nomenclatural system, be manually modified to reflect the now discovered uncertainty. Such a level of manual modification is an utterly impractical task and, as of 2024 when this passage was first drafted, has not happened. Nor is it ever expected to happen.

### Why not use 'sensu lato'
The immediate answer from the extant nomenclatural/taxonomic structure is that all existing data be immediately considered 'sensu lato'. This idea is all very well until the repercussions of such an action are considered. Firstly, and perhaps most importantly, such an action is tantamount to changing the species name. There exist records of *Bombus lucorum*. If these are to be *considered* to be read as *Bombus lucorum sensu lato*, then there can never ever again be a use of the name *Bombus lucorum*. Re-using the name creates an environment where the intended meaning cannot be known. Using time as a proxy is a highly dangerous idea, as even in 2024 there are still people resurrecting old interpretations of taxa - including this change.

The second reason for rejecting the 'sensu' system is that the system can only work once. *Andrena scotica* and *Andrena trimmerana* are two taxa which have been conflated for many decades. Recently, there have been multiple works which attempted to separate the taxa and provide a guide to identification that covers the entire range of Great Britain. To keep the situation *reasonably* simple, only the three latest nomenclatural entries for what is now known as *Andrena scotica* will be used. The three entries of relevance are:

- *Andrena scotica* in the sense of Perkins, 1916
- *Andrena scotica* in the sense of Else & Edwards, 2018
- *Andrena scotica* in the sense of Wood et al, 2022

The summarised history is that Else & Edwards, working with Wood et al in 2018, identified that what Perkins called *Andrena scotica* was a mixture of what they called *Andrena scotica* and *Andrena trimmerana*. Accordingly, all extant data of *Andrena scotica* must be interpreted as *Andrena scotica* sensu lato. Any determinations using this new guidance must be written as *Andrena scotica* sensu stricto to prevent them from being lumped in with *Andrena scotica* sensu lato.

However, the group working on this problem was not convinced that they had, in fact, reached the correct conclusion. More material was sought and analysed, leading to the work by Wood et al in 2022. This work demonstrated that the previous conclusion which was thought to be a reliable means of separating *Andrena scotica* and *Andrena trimmerana* was not at all reliable. Accordingly, all material of *Andrena scotica* sensu stricto was, once again, to be considered an aggregate.

According to the 'sensu' nomenclature system, then the name for this is *Andrena scotica* sensu stricto sensu lato. Any other combination, derivation, or alteration of sensu nomenclature system results in significant widespread confusion as to how to interpret the given results. Such a confusing name highlights the lack of power in daisy-chaining 'sensu' epithets to provide a clean, understandable and informative approach to nomenclature.

### Numerical sequences
An alternative to the utilisation of epithets is to utilise numerical identifiers. Each 'individual' name is given a numerical identifier, which is then promoted for use instead of the name. Such a system is considered highly inferior because

- it replaces the name that taxonomists and biologists are used to
- humans are terrible at remembering random sequences of numbers
- it doesn't fix anything, just hides the problem under another layer of obfuscation

Multiple such numerical systems exist. The UK has the Biological Record Centre system (now defunct, as it was expected to be) and the UK Species Inventory (which makes several critical missteps). 

## Introducing Understandings
Understandings are a means to sidestep the usage of 'sensu' epithets 
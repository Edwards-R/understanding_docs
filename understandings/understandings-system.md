# The Understandings System
The Understandings System is responsible for maintaining accurate linkage between Interpretations and Types. Given that there is currently no versioned Type repository to rely upon, the Understandings System also has a provision for manually incorporating taxonomic changes.

The Understandings System is designed in layers, with each layer holding a distinct set of responsibilities. This document will examine each layer in turn, then culminate in real-world examples which demonstrate various aspects of the Understandings System. Firstly though we must examine the idea of *systematic, widespread, confusion*.

## Systematic Widespread Confusion
Every modification to an Interpretation involves a trade off between continuity of use and precision. Do you prefer stability and accept a certain level of inaccuracy, or does the desired level of accuracy require a change in interpretation? To answer this question, the idea of *systematic widespread confusion* was coined. When presented with an opportunity for a change which could be handled in multiple ways, ask the question *does this situation represent significant widespread confusion in the interpretation of data?*. This is a question that should be directed at the taxonomic experts for the relevant area, as only they are likely to be able to provide an answer. If the answer is *yes*, then the need for precision outweighs the need for stability. If the answer is *no*, then favour stability over precision. If the answer is *I don't know* then favour precision over stability.

## System Setup
The first phase of the Understandings System is the setup phase. This phase is where the taxonomic, temporal, and spatial limits of the system are decided upon.

### Ranks
Taxonomic ranks are a sometimes thorny issue, with different taxonomic areas preferring one set of ranks over another. The most significant constraint of the Understandings System is that all desired ranks must be declared at system setup, and every entry in the system must have an assigned Understanding at every rank. For instance, if the ranks involved in a system are:

- Family
- Subfamily
- Genus
- Species
- Subspecies

then every single entry *must* have a Family, Subfamily, Genus, Species and Subspecies. It is not permitted to have, for example, only Family, Genus, and Species.

It is theoretically possible to alter the Understandings System to allow for 'optional' ranks, and the system has been briefly tested with success. However, the results were impractical without significant code effort. Optional ranks were deemed non-essential, and development has been suspended on this front.

Whilst ranks are entirely at the discretion of each implementation of Understandings, it is recommended to use the generic set as a skeleton to build from. The generic set is considered to be:

- Kingdom
- Phylum
- Order
- Family
- Genus
- Species

The first i.e. highest rank in your system should ideally be one of these ranks. Then, all skeleton ranks between the first and lowest rank should be included. For example, if I want to go from Family to Subspecies, I need to include Genus and Species as well.

### Temporal limitations
It would be ideal to start tracking Interpretations at their point of conception (i.e. when the type is declared). However, such a goal is often either entirely unobtainable, or so difficult to obtain that it becomes impractical. It is, in some instances, perfectly acceptable to limit the start date of an Understandings system so that entirely exhaustive documentation becomes unneccessary. For example, if a taxon is well documented in a region since 1956 then an Understandings system may choosed to use 1956 as a 'false origin' start date. The limitation would then be that any data prior to 1956 would exist under the type system alone, rather than enjoying the benefits of Interpretations. However, as the question has uncovered that doing so would not result in *significant widespread confusion* then this limitation is deemed acceptable.

#### Data from before the false origin
If encountering data from before the false origin, the first action to take is to consider whether the volume of data and suspected taxonomic complexity is enough to cause *significant, widespread, confusion in the interpretation of the data*. If the answer is *yes*, then the precision option is to create a new Interpretation with a date *prior* to the false origin. The author of this Interpretation would be the author the Understanding System. If the answer is *no*, then the data can simply be assigned to the oldest Interpretation in the system. The goal is, as always, to minimise disruption whilst maximising accuracy.

## Taxonomic limitations
Whilst it is possible to implement the Understandings System to cover all life, it is expected that the majority of implementations will concern themselves with a sub-set of taxa. To do this, simply start at the highest relevant rank and progress from there. For example, the BWARS Understandings implementation starts with the superfamilies for the Aculeate hymenoptera. No ranks are present above Superfamily, and the sub-ranks of Family, Genus, and Species are present as normal.

## Notes
Need to divide this into sectors:

- The setup of the system
    - Rank limits
    - Taxonomic limits
    - Spatial limits
    - Temporal limits
- The running of the system
    - What are operations
        - Only permissible 'things' to do with the system
        - Designed to maintain constant to sychronicity with our current knowledge of the types
        - Single rank operations only
            - If an operation wants to affect multiple ranks, it has to break the operation down by rank
            - Changes can, and do, cascade down the ranks
    - Operations at single stage
        - Automated operations
            - Create
            - Split
            - Merge
        - Manual operations
            - Redirect
            - Add synonym
- What to do when there is no versioned type system
    - Just do it all manually
    - Higher workload
    - No global propagation
    - Requires someone to be aware of the change first



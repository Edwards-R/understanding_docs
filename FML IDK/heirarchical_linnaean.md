# The failing points of heirarchical Linnean taxonomy

## Modifications over time
Under the 'standard' hierarchical Linnaean system, there does not exist a way to differentiate clearly between multiple meanings to a name.

### Example: Bombus lucorum in Great Britain and Ireland

*Note: This example is based on the work of Murray et al, 2008, which can be [found in full here](https://www.researchgate.net/profile/Mark-Brown-32/publication/226718911_Cryptic_species_diversity_in_a_widespread_bumble_bee_complex_revealed_using_mitochondrial_DNA_RFLPs/links/09e41507d79ad7aaf9000000/Cryptic-species-diversity-in-a-widespread-bumble-bee-complex-revealed-using-mitochondrial-DNA-RFLPs.pdf)*

The short version is that the name 'Bombus lucorum' may refer to any of the following fairly-modern interpretations:

- *Bombus lucorum* as an amalgamation of what is currently understood to be:
    - Bombus lucorum
    - Bombus terrestris
    - Bombus cryptarum
    - Bombus magnus

- *Bombus lucorum* as an amalgamation of what is currently understood to be:
    - Bombus lucorum
    - Bombus cryptarum
    - Bombus magnus

- *Bombus lucorum* as it the type is currently understood

Consequently, the objective of [being able to identify the type with exact confidence](./objective.md#what-counts-as-exact-confidence) is not fulfilled. A mention of *Bombus lucorum* could refer to a specimen of:
- Bombus lucorum
- Bombus terrestris
- Bombus cryptarum
- Bombus magnus

In this scenario, the *only* specimen which is not subject to this confusion is the type specimen itself.

## Confusions with Phylogenetic systems
If you try and sort the same information in two different ways in one system, it won't work. For a practical demonstration, try sorting any set of objects by two parameters, *without* putting one parameter before the other. It won't work.

There have been many attempts to marry up Phylogenetic systems with Heirarchical systems. Frequently this shows up as an attempt to label Phylogenetic trees with Heirachical nomenclature, or to attempt to use pure Phylogenetic structure in Hierarchical systems.

These two systems are sorting the same information in different ways. This doesn't work. However, the other significant cause of failure is simply the fact that the current 'Linnaean-style' hierarchy doesn't have consistent units to base a correlating system on. A lack of consistency immediately results in failure, as the only option is to use inconsistent groupings with undefined meanings.

## Regional locks
Linnaean heirarchical taxonomy is, despite some very hard-fought battles to stop it being so, strictly regional in *application*. Note that this does *not* refer to the **type** itself. This can easily be demonstrated with a Venn diagram between taxon A and taxon B. In this scenario, B has been split from A. The populations have an area of overlap, but for the most part have a strict divide:

![Venn diagram of overlap](./diagram/regional_locks.drawio.svg)

Now there exist three specific interpretations of A:

- A and only A (top part)
- A now understood to be B (bottom part)
- A which could be either A *or* B (overlapping middle)

What is the one action that can be taken that will not result in *any* statement being wrong?

*All records of A are now either A or B*

This is a terrible answer is it loses data. All of the records from the north *and* south get smooshed together into the same as the middle, despite it being entirely possible to distinguish between the two based on the records themselves.

Any attempt to solve the question any other way results in one part of the populace being disregarded. This leads to disenfranchisement, splitting, arguments, civil wars etc.

For example, the answer could be 'All A are now B'. This is great for the people who reside in B, but useless for people in the overlap and actively harmful and wrong for people in A.

## Why are these points so important?
Being unable to precisely resolve information back to the type using modern information, or even being unable to tell whether it is possible to do so, it a major problem for biological recording.

When reading a paper for research, how does the student know the subject taxon is being used pre or post split?

When creating automated record validation/verification rulesets, it is imperative that the correct taxon be referred to. Understandings make this absolute. Attempting automated management of biological data without Understandings, or something that achieves the same function, is setting a project up for failure.
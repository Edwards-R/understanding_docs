# Maintaining a global system
> This doc needs to outline the one-to-many relationships and let me use interpretations without having to constantly point out that they refer to the same type concept & the type concepts refer to the same type name

> Idea from S: Do example of cardinality as human body. One body has two arms, each arm has 5 fingers. Each finger still belongs to the same body.?

In the previous chapter on designing human-centric labels, it was mentioned that interpretations may be regional in nature rather than global. Given that a core tenet of the Linnaean taxonomic system is its global nature, how can a regional nomenclature maintain global applicability? The answer lies in the hierarchy of these elements.

## The three elements
So far, we have established three separate areas of concern within the Linnaean taxonomic system:

- Type name
- Concept version
- Interpretation

These three elements exist in a strictly defined hierarchy, starting with the type name and ending with the interpretation. Each type name will have one or more concept versions, and each concept version will have one or more interpretations. In reverse, each interpretation relates to one concept version and each concept version relates to one type name. This type of design is called a one to one-to-many relationship, and is foundational to data system designs across the world and throughout history. Most importantly for us, because each interpretation relates to one concept and therefore one type name, each interpretation can be resolved back to a singular type.

### A tactile example
The typical human has one body. That body has two arms. Each arm then has multiple fingers. Each finger belongs to an arm, and each arm to the same body. Therefore, all fingers belong to the same body.

### Bombus as an example
To illustrate how the linkage between the various components is maintained, this example uses a suite of species from the genera *Bombus* (Bumblebees). The genus is found worldwide, is well studied (for an invertebrate) and, due to the typical identification methods relying on colours, contains a number of regionally cryptic taxa. The combination of factors makes *Bombus* an excellent example candidate to illustrate the various ways in which nomenclatural disjunctions occur, and how they can be solved.

## Each interpretation relates to a single type name
During this exercise, we will examine the various concept versions and interpretations of the name *Bombus lucorum* Linnaeus 1761. Please note that this is not an exhaustive list in any way, and only serves as an example.

The origin concept version of the name *Bombus lucorum* Linnaeus 1761 is, by definition, created by Linnaeaus in 1761. A similar situation is true for the origin interpretation of that concept version, which is also attributed to Linnaeus 1761.

|Attribute|Value|
|:--|--:|
|Name|*Bombus lucorum*|
|**Type Name**|
|Name author|Linnaeus|
|Name year|1761|
|**Concept Version**|
|Concept author|Linnaeus|
|Concept year|1761|
|**Interpretation**|
|Interpretation author|Linnaeus|
|Interpretation year|1761|

Latreille made changes to the type concept of *Bombus lucorum* in 1802. Accordingly, a new concept version and associated interpretation are created.

|Attribute|Value|
|:--|--:|
|Name|*Bombus lucorum*|
|**Type Name**|
|Name author|Linnaeus|
|Name year|1761|
|**Concept Version**|
|Concept author|Latreille|
|Concept year|1802|
|**Interpretation**|
|Interpretation author|Latreille|
|Interpretation year|1802|

In 2008, Murray et al corrected the interpretation of Latreille's concept version of *Bombus lucorum*.

|Attribute|Value|
|:--|--:|
|Name|*Bombus lucorum*|
|**Type Name**|
|Name author|Linnaeus|
|Name year|1761|
|**Concept Version**|
|Concept author|Latreille|
|Concept year|1802|
|**Interpretation**|
|Interpretation author|Murray et al|
|Interpretation year|2008|v

Note how the name, the name author, and the name year remain constant throughout every example. This happens because each and every example is a versioning, in some way, of the same name. Note too that it is possible, given this list of options, to provide only the name, interpretation author, and interpretation year (e.g *Bombus lucorum*, Murray et al, 2008) and still arrive at a singular type name. This ability to 'shortcut' the process will become extremely important later, as it allows the offloading of the majority of work to automated systems. Once the bulk of work is taken up by such automation, the increased complexity of utilising a three-tier system over a one-tier system is almost entirely erradicated.

## Regionality and globality
Now that the system is fully divided up into areas of concern, it is possible to divide these areas once more. Our type name and type version are *global*, as they refer to the library of types managed by the respective nomenclatural codes. Our interpretations, however, may be *regional*. Multiple, distinct, sets of regional interpretations may be attached to any given concept version, and all will still link back to a given type name.

## Summary
The Linnaean taxonomic system has been divided up into two components: name and concept version. A third component has been added, which is the interpretation. These three components have been structured to provide a clear link between the three areas of responsibility, as well as allowing interpretations to be regional. Nomenclatural disjunction is therefore identifiable at both the type concept and interpretation levels. When writing nomenclature, an interpretation can be given without needing to state the type name details or the concept version, as both of these are contained within the framework of the proposed system.

Now that there is a framework, the next step is to provide a demonstration of that framework in action.

[Next](./interpretation-regions.md)
# Maintaining a global system
> This doc needs to outline the one-to-many relationships and let me use interpretations without having to constantly point out that they refer to the same type concept & the type concepts refer to the same type name

In the previous chapter on designing human-centric labels, it was mentioned that interpretations may be regional in nature rather than global. Given that a core tenet of the Linnaean taxonomic system is its global nature, how can a regional nomenclature maintain global applicability? The answer lies in the hierarchy of these elements.

## The three elements
So far, we have established three separate areas of concern within the Linnaean taxonomic system:

- Type name
- Concept version
- Interpretation

These three elements exist in a strictly defined hierarchy, starting with the type name and ending with the interpretation. Each type name will have one or more concept versions, and each concept version will have one or more interpretations. In reverse, each interpretation relates to one concept version and each concept version relates to one type name. This type of design is called a one to one-to-many relationship, and is foundational to data system designs across the world and throughout history. Most importantly for us, because each interpretation relates to one concept and therefore one type name, each interpretation can be resolved back to a singular type.

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
|Interpretation year|2008|

> New subheader here? Maybe

As can be seen in this example, the type name never changes. All items here are versions, in some way, of that singular type name. There are two concept versions of this singular type: that of Linnaeus in 1761, and that of Latreille in 1802. Additionally, there are three interpretations of these two concept versions. One interpretation belonging to the concept version authored by Linnaeus in 1761, and two interpretations belonging to the concept version authored by Latreille in 1802.

Associating from the interpretation back to the type name here, we can see that the interpretation of *Bombus lucorum* by Murray et al in 2008 refers to the type name by Linnaeus in 1761.

In this manner, each and every interpretation belongs to a concept version. In turn, each and every concept version belongs to a type name.

> something something... IDK, getting lost in the sauce here. There's only so many ways to say 'it works if you just think about it'. To be fair, this is the part that causes most soft eng students to just blank.

> Next section is a summary (maybe turn the above into the summary?) that then leads on to 'Now that we can relate a given interpretation to a type, we can look at how we can make a regional system that ends up in a global agreement'.

> **NB** The section *after* the regional stuff probably needs to be about resolving an interpretation. Answer the question '*if A == B, then why use both A & B?*'
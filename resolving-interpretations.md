# Resolving Interpretations
In each interpretation region, each concept version has a singular interpretation which is considered to the currently correct. As a result, there are potentially multiple interpretations within any given region which are in nomenclatural divergence. Interpretations so far have only allowed the identification of different interpretations. Now they will be improved to allow for solving of nomenclatural divergence.

## Working examples
To illustrate the first stages of this example, we will use a situation of two confused types: *Hylaeus annularis* and *Hylaeus dilatatus*:

|Attribute|Value|
|:--|--:|
|Name|*Hylaeus annularis*|
|Name author|Kirby|
|Name year|1802|
|Concept author|Kirby|
|Concept year|1802|

|Attribute|Value|
|:--|--:|
|Name|*Hylaeus dilatatus*|
|Name author|Kirby|
|Name year|1802|
|Concept author|Kirby|
|Concept year|1802|

Whilst examining specimens in the British Natural History Museum, Notton & Dathe realised that the material of these two taxa did not match the concept established by Kirby in 1802. The author of this changed concept remains uncertain, predominantly due to the very lax way in which taxonomy has been handled thus far. The solution was made more complex by the way in which the solution was handled, which was to effectively swap the type concepts across these two active names. Breaking the taxonomic process down into the new system, Notton & Dathe effectively declared new concept versions as follows:

|Attribute|Value|
|:--|--:|
|Name|*Hylaeus annularis*|
|Name author|Kirby|
|Name year|1802|
|Concept author|Notton & Dathe|
|Concept year|2008|

|Attribute|Value|
|:--|--:|
|Name|*Hylaeus dilatatus*|
|Name author|Kirby|
|Name year|1802|
|Concept author|Notton & Dathe|
|Concept year|2008|

Summarising the interpretations, in this case one per concept change, we therefore have:

|Name|Interpretation author|Interpretation year|
|---|:-:|:-:|
|*Hylaeus annularis*|Kirby|1802|
|*Hylaeus dilatatus*|Kirby|1802|
|*Hylaeus annularis*|Notton & Dathe|2008|
|*Hylaeus dilatatus*|Notton & Dathe|2008|

## Interpretation synonymy
Interpretations can use a system very similar to Linnaean synonymy to identify where it should go. Each and every interpretation has an associated 'currently correct' interpretation associated with it.

|Attribute|Subject|Associated|
|:--|:-:|:-:|
|Name|*Hylaeus dilatatus*|*Hylaeus annularis*|
|Name author|Kirby|Notton & Dathe|
|Name year|1802|2008|
|Concept author|Kirby|Notton & Dathe|
|Concept year|1802|2008|

In the case that the subject interpretation *is* the currently correct interpretation, this associated interpretation is itself:

|Attribute|Subject|Associated|
|:--|:-:|:-:|
|Name|*Hylaeus dilatatus*|*Hylaeus dilatatus*|
|Name author|Notton & Dathe|Notton & Dathe|
|Name year|2008|2008|
|Concept author|Notton & Dathe|Notton & Dathe|
|Concept year|2008|2008|

By navigating to this associated interpretation, a process known as 'resolving', we arrive at the currently correct end point for this interpretation. The associated interpretation may be safely changed at any point, but should always point to an end point - a taxon whose interpretation is itself (e.g. A -> B -> B). If any interpretation ever does not point to an end point (e.g. A -> B -> C) then the interpretation should have the associated interpretation updated so that it does (e.g. A -> C -> C).

> Managing associated end points manually is quite a challenging task, especially as the scope of the system grows. It is recommended to automate the management of associated end points to improve ease of use and precision.

## Implications for storing data
Resolving an interpretation cannot be done in advance of using that interpretation, as doing so prevents modernisation. Without the ability to modernise, nomenclatural divergence once again is able to take place. Instead, nomenclature should be stored and operate on the level of interpretations, with taxonomy used at point-of-consumption. One particular use for resolving back to taxonomy is when compiling data across multiple interpretation regions.

## A practical example
For this example we will use *Bombus lucorum*, with interpretations taken from the regions of Great Britain and Austria. Using the interpretations from Great Britain, this example will demonstrate the differences between resolving at point of storage vs resolving at point of consumption. The example will then move on to demonstrate how resolving at point of consumption allows the merging of regional datasets with absolute taxonomic clarity.


### Point of storage *vs* point of consumption 
In Great Britain there are two interpretations of *Bombus lucorum*:

 - Latreille, 1802
 - Murray et al, 2008

First, an occurrence record of *Bombus lucorum* from 1996 is stored. This will be entered as '*Bombus lucorum* *interpretation* Latreille, 1802'. When resolved, this record will provide '*Bombus lucorum* Linnaeus, 1761', as the interpretation by Latreille in 1802 is the currently correct interpretation and therefore resolves to the type.

Next, fast-forward to 2010 and store another record. This record has been afforded all the benefits of modern science and has been genetically sequenced - we are therefore very confident that it is '*Bombus lucorum* *interpretation* Murray et al, 2008'. When resolved, this record will provide '*Bombus lucorum* Linnaeus 1761', as the interpretation by Murray et al in 2008 is the currently correct interpretation.

However, the first record, entered as '*Bombus lucorum* *interpretation* Latreille, 1802', has an issue. If we resolved then stored, this will be stored as the type name - *Bombus lucorum* - despite the work of Murray et al demonstrating that *Bombus lucorum* *interpretation* Latreille, 1802 does not equate to the type, being a cryptic aggregate. If we store the interpretation and resolve at point of use, we have two interpretations:

*Bombus lucorum* *interpretation* Latreille, 1802
*Bombus lucorum* *interpretation* Murray et al, 2008

When resolved in 2010 (and remembering that Murray et al showed that Latreille's 1802 interpretation was a cryptic aggregate), we get the following information:

|Origin interpretation|Resolved interpretation|Type(s) included|
|:-:|:-:|:-:|
|*Bombus lucorum* Latreille, 1802|*Bombus lucorum* aggregate Murray et al, 2008|*Bombus lucorum*, Linnaeus 1761|
|||*Bombus magnus* Vogt, 1911|
|||*Bombus cryptarum* Fabricius, 1775|
|---|---|---|
|*Bombus lucorum* Murray et al, 2008|*Bombus lucorum* Murray et al, 2008|*Bombus lucorum*, Linnaeus 1761|

> Pay attention to column headers. Without specific formatting, it is very easy to confuse interpretations and types.

With this, nomenclatural disjunction is finally solved. We have a method of identifying, storing, and now resolving, every situation where a type name no longer matches the type concept.

### Cross regional
Performing the same comparison for Austria as we did Great Britain (pre- and post- interpretation change i.e. 1996 and 2018), we achieve the following table:

|Origin interpretation|Resolved interpretation|Type(s) included|
|:-:|:-:|:-:|
|*Bombus lucorum* Latreille, 1802|*Bombus lucorum* aggregate Bossert et al, 2016|*Bombus lucorum*, Linnaeus 1761|
|||*Bombus cryptarum* Fabricius, 1775|
|---|---|---|
|*Bombus lucorum* Bossert et al, 2016|*Bombus lucorum* Bossert et al, 2016|*Bombus lucorum*, Linnaeus 1761|

#### Resolving in 1996
Using this data and storing as interpretations, we can combine data from Great Britain and Austria by resolving when we consume. Consuming and resolving our data from 1996 gives us:

|Region|Interpretation|Type(s)|
|---|---|---|
|Great Britain|*Bombus lucorum* Latreille, 1802|*Bombus lucorum* Linnaeus, 1761|
|---|---|---|
|Austria|*Bombus lucorum* Latreille, 1802|*Bombus lucorum* Linnaeus, 1761|

Both interpretations resolve to the same, singular type. In accordance with how types work, these two records should be considered to be of the exact same taxon and can therefore be compared.

#### Resolving in 2010
Moving forward to 2010, which is *after* Murray et al yet *before* Bossert et al, the same two records provide the following when resolved at consumption:

|Region|Interpretation|Type(s)|
|---|---|---|
|Great Britain|*Bombus lucorum* Latreille, 1802|*Bombus lucorum* Linnaeus, 1761|
|||*Bombus magnus* Vogt, 1911|
|||*Bombus cryptarum* Fabricius, 1775|
|---|---|---|
|Austria|*Bombus lucorum* Latreille, 1802|*Bombus lucorum* Linnaeus, 1761|

Here we can see the increased knowledge gained by Murray et al automatically reflected in the data. The consumer is *immediately* able to notice that *Bombus lucorum* from Great Britain, interpreted according Latreille, 1802, has undergone a nomenclatural disjunction.

If we add a record from Great Britain, interpreted according to Murray et al, 2008, the result is as follows:

|Region|Interpretation|Type(s)|
|---|---|---|
|Great Britain|*Bombus lucorum* Latreille, 1802|*Bombus lucorum*, Linnaeus 1761|
|||*Bombus magnus* Vogt, 1911|
|||*Bombus cryptarum* Fabricius, 1775|
|---|---|---|
|Great Britain|*Bombus lucorum* Murray et al, 2008|*Bombus lucorum* Linnaeus, 1761|
|---|---|---|
|Austria|*Bombus lucorum* Latreille, 1802|*Bombus lucorum* Linnaeus, 1761|

The user is immediately able to see the disjunction in *Bombus lucorum* data from Great Britain, as well as what data correctly resolves to the type name *Bombus lucorum* Linnaeus, 1761. This correct data can be used for scientific study, whilst the nomenclaturally disjunct data typically must be discarded.

#### Resolving in 2020

Concluding the example set, we step forward to 2020. Here, both regions of Great Britain and Austria have identified a nomenclatural disjunction in *Bombus lucorum*. The example reflects these discoveries, as well as adding a fourth record using the Bossert et al 2015 interpretation.

|Region|Interpretation|Type(s)|
|---|---|---|
|Great Britain|*Bombus lucorum* Latreille, 1802|*Bombus lucorum*, Linnaeus 1761|
|||*Bombus magnus* Vogt, 1911|
|||*Bombus cryptarum* Fabricius, 1775|
|---|---|---|
|Great Britain|*Bombus lucorum* Murray et al, 2008|*Bombus lucorum* Linnaeus, 1761|
|---|---|---|
|Austria|*Bombus lucorum* Latreille, 1802|*Bombus lucorum* Linnaeus, 1761|
|||*Bombus cryptarum* Fabricius, 1775|
|---|---|---|
|Austria|*Bombus lucorum* Bossert et al, 2015|*Bombus lucorum* Linnaeus, 1761|

## Resolving concept versions and type names
The same logic of resolving may be applied to concept versions and type names. Indeed, type names already possess a level of resolving in the current Linnaean system - synonyms. Any design specification, however, falls firmly within the realm of the *implementation* of design as opposed to the *specification* of design. As such, no further details on *how* such a system may be managed will be outlined herein.

## Conclusion
Interpretations may be used to store nomenclature in a time-safe, regional manner. Resolving an interpretation at the point of consumption means that the end user is always able to incorporate the maximum amount of taxonomic and nomenclatural knowledge, vastly increasing the taxonomic precision of end-user products.

There are multiple problems still to be addressed. Interpretations and taxonomic names are written identically whilst referring to very distinct ideas, which is a highly undesirable situation. Keeping track of interpretations, type concepts, and type names in a strict manner requires automation, which in turn requires a strict set of rules to be laid out (and for people to follow them). The absence of a suitable scheme managing taxonomy for zoology is also a significant impediment to establishing the proposed system, albeit one which can be overcome safely.

The next stage of this work is to design an implementation of the protocols set out within this document.
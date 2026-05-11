---
parent: Interpretations, Understandings, and the Understandings System
title: 6. Resolving Interpretations
---
# Resolving Interpretations
In each interpretation region, each concept version has a singular interpretation which is considered to be currently correct. As a result, there are potentially multiple interpretations within any given region which are in nomenclatural divergence. Interpretations so far have only allowed the identification of different interpretations. Now they will be improved to allow for solving of nomenclatural divergence.

## Working examples
> This example is based on reality, but has been simplified to remove extraneous information and improve the quality of the example. The alterations do not impact the outcome.

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

Whilst examining specimens in the British Natural History Museum, Notton & Dathe realised that the material of these two taxa did not match the concept established by Kirby in 1802. The material was too precisely mis-attributed to be the result of a simple determination error. Further investigation revealed the presence of an alteration of the Kirby concept that had become pervasive, with multiple well-used keys using the altered concept rather than the original. The national recording schemes were also using the altered concept, with almost all the 'original' concept uses being found in older museum collections.

The zoological codes recognise, in general, two different methods of resolving such a situation. The first is to recognise that a change has happened and then reverse that change to restore the original state. This action is the preferred course. The second, which is generally less desirable, is to accept the change as the new normal. This action is usually only taken when there is a demonstrable need to do so, such as the changed version being in common use for a significant amount of time, or where the negative impacts of correction outweigh any positives. In this scenario, the authors decided to utilise the 'default' option of reverting a discovered change. Breaking the taxonomic process down into the new system, Notton & Dathe effectively declared new concept versions as follows:

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

Summarising the concepts, one per concept change, we therefore have:

|Name|Concept author|Concept year|
|---|:-:|:-:|
|*Hylaeus annularis*|Kirby|1802|
|*Hylaeus dilatatus*|Kirby|1802|
|*Hylaeus annularis*|Notton & Dathe|2008|
|*Hylaeus dilatatus*|Notton & Dathe|2008|

## Concept synonymy
Concept can use a system very similar to Linnaean synonymy to identify where it should go. Each and every concept has an associated 'currently correct' concept associated with it.

|Attribute|Subject|Associated|
|:--|:-:|:-:|
|Name|*Hylaeus dilatatus*|*Hylaeus annularis*|
|Name author|Kirby|Notton & Dathe|
|Name year|1802|2008|
|Concept author|Kirby|Notton & Dathe|
|Concept year|1802|2008|

In the case that the subject concept *is* the currently correct concept, this associated concept is itself:

|Attribute|Subject|Associated|
|:--|:-:|:-:|
|Name|*Hylaeus dilatatus*|*Hylaeus dilatatus*|
|Name author|Notton & Dathe|Notton & Dathe|
|Name year|2008|2008|
|Concept author|Notton & Dathe|Notton & Dathe|
|Concept year|2008|2008|

By navigating to this associated concept, a process known as 'resolving', we arrive at the currently correct end point for this concept. The associated concept may be safely changed at any point, but should always point to an end point - a taxon whose concept is itself (e.g. A -> B -> B). If any concept ever does not point to an end point (e.g. A -> B -> C) then the concept should have the associated concept updated so that it does (e.g. A -> C -> C).

> Managing associated end points manually is quite a challenging task, especially as the scope of the system grows. It is recommended to automate the management of associated end points to improve ease of use and precision.

## Extending to cover Interpretations
Interpretations use the exact same system as concepts. Each interpretation is connected to the 'current' interpretation, which may again be itself.

### Hylaeus example
|Attribute|Subject|Associated|
|:--|:-:|:-:|
|Name|*Hylaeus dilatatus*|*Hylaeus annularis*|
|Name author|Kirby|Notton & Dathe|
|Name year|1802|2008|
|Concept author|Kirby|Notton & Dathe|
|Concept year|1802|2008|
|Interpretation author|Kirby|Notton & Dathe|
|Interpretation year|1802|2008|

In the case that the subject concept *is* the currently correct concept, this associated concept is itself:

|Attribute|Subject|Associated|
|:--|:-:|:-:|
|Name|*Hylaeus dilatatus*|*Hylaeus dilatatus*|
|Name author|Notton & Dathe|Notton & Dathe|
|Name year|2008|2008|
|Concept author|Notton & Dathe|Notton & Dathe|
|Concept year|2008|2008|
|Interpretation author|Notton & Dathe|Notton & Dathe|
|Interpretation year|2008|2008|

## Pre-resolving stored data
Resolving an interpretation cannot be done in advance of using that interpretation, as doing so prevents modernisation of the interpretation. Without the ability to modernise, nomenclatural divergence is once again able to take place. Instead, nomenclature should be stored and operated on the level of interpretations, with taxonomy used at point-of-consumption, should it be required to do so. If a project is examining data from entirely within on region of interpretations, it is not necessary to convert the interpretations to types. If the project wishes to cross multiple regions, such as for a pan-European study, then each region will need converting back to types.

> N.B. Should different regions disagree on what types are valid, this will still need to be handled manually. *Theoretically* this should not happen, but in practice it is fairly common for different schools of taxonomy to argue with each other. The end goal of the system presented here is that it creates a way for such disagreements to be performed at the level of nomenclature rather than types, but that is too complex for an already complicated general explanation document.

## A practical example of everything combined together
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

## Passive updating
A considerable benefit of using interpretations in this manner is that stored data is passively updated through the maintenance of a central list. Because modernisation of nomenclature is performed through resolving the interpretation there is no requirement to change specimen labels unless the specimen itself is re-determined. When dealing with museum collections that are in active use, this passive updating can easily save hours of curator and user hassle.

## Conclusion
Interpretations may be used to store nomenclature in a time-safe, regional manner. Resolving an interpretation at the point of consumption means that the end user is always able to incorporate the maximum amount of taxonomic and nomenclatural knowledge, vastly increasing the taxonomic precision of end-user products. Also of note is that data stored using interpretations is able to be passively updated by updating where any given interpretation resolves to.

There are multiple problems still to be addressed. Interpretations and taxonomic names are written identically whilst referring to very distinct ideas, which is a highly undesirable situation. Keeping track of interpretations, type concepts, and type names in a strict manner requires automation, which in turn requires a strict set of rules to be laid out (and for people to follow them). The absence of a suitable scheme managing taxonomy for zoology is also a significant impediment to establishing the proposed system, albeit one which can be overcome safely.


## Next steps
The next stage of this work is to design an implementation of the protocols set out within this document so that everything mentioned here can be put into practice - at least where it can reasonably be. Details of the implementation that was used for the testing of the system can be found [here](../understandings/intro.md), which focuses on the implementation of interpretations.

Alternatively, take a look at the [guidelines for declaring a new interpretation](./publishing-a-new-interpretation.md) or [how to add interpretations to existing keys](./adding-interpretations-to-existing-keys.md)
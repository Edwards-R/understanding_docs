# Defining Ranks
The new Understandings-based system is still going to be based on hierarchical ranks. It will still be possible for people to, for instance, create an infinite number of defined subranks (accurately or not) that only work for their specific taxa of interest. However, the *responsibility* for different things is going to shift around so that doing actions such as this does not affect others unless they desire it to.

Don't worry about this section too much unless you want to understand the inner details of how the whole system is planned out. A general user of the system does not need to know how Understandings ranks differ from 'traditional' ranks, as there is no appreciable difference to the end user.

## A brief explanation of ranks for engineers
`Ranks` are a hierarchical structure. A common set of ranks is as follows:

```
-- Kingdom
---- Phylum
------ Order
-------- Family
---------- Genus
------------ Species
```

Each entry under a `species` belongs to a `genus`, each `genus` belongs to a `family` and so on. Simple enough.

## Wibbly-wobbly rank things
The immediate problem is that there are an infinite number of ranks, only limited by the pickiness of the user. As a result, there is no exhaustive list of ranks. People are free to make up whatever they need, whatever they think fits, and try to justify it as they can. Some get accepted, others don't, some get partially accepted and cause feuds.

***This is not a bad thing and is a very useful thing***

Science is about discovery and the proposal of new ideas. Stifling innovation leads to stagnation, which leads to an inability to use new discoveries.

However, non-standardised systems make it very hard to compare from one version to another. The solution is to standardise *some* of the ranks at a fundamental level *and* provide a safe way for these ranks to be built upon in an open fashion. In software-parlance, we'd call this an *extendable* system. Any person can, without contacting, notifying, or bothering the 'original owner', build a new section off of the backbone. Of course, this requires that they follow the system design rules for doing so, but that's not a hard thing to do.

### So why do we have a backbone to start with?
Well, strictly speaking, we don't design one here. Strictly speaking, we're just making a bunch of optional ranks from the start and going with 'whatever works for the most people' and calling it a backbone. Practically speaking, a backbone is useful because it provides a point for people to communicate from. Systems used by one person aren't very good for sharing information. The establishment of a backbone makes it so that multiple *can* use this system, as well as providing *something* for them to split up as they see fit, without going to the *N*th degree. The backbone is the 'lowest common denominator' of ranks. 

## Taxonomic backbone
The goal here is to pick a set of ranks that are universally applied. This should be as small a set as possible, whilst being as specific as possible, whilst being **entirely** globally applicable.

For example, many taxa do not have defined subspecies, which removes `subspecies` as a candidate for inclusion in the taxonomic backbone. See [custom ranks](#custom-ranks) and [below the backbone](#below-the-backbone) for details on how to manage subspecies.

For now, we'll start with the following as candidates for the backbone:


>-- Kingdom
>
>---- Phylum
>
>------ Order
>
>-------- Family
>
>---------- Genus
>
>------------ Species


There's also an interesting opportunity here to codify three interesting ideas.

### Exo-biology
*You can skip this one entirely if you're not interested in fringe use-cases*

A `biota` is a rank above `kingdom`. It refers to the 'origin of life' and is designed to designate a grouping of 'life' that stems from a common origin i.e. Earth. The *only* time this would become applicable is if life is found on a different planet.

Another option is make a rank above `biota` to represent life that shares a common set of chemical components. I'm not even going to speculate a name for this one. The important thing is to state how it is possible to add higher groupings at will - though this does require careful thought as to the *need* that these higher groupings fill.

Given the whole *'Do not prematurely optimise'* guideline for any project, exo-biology ranks won't be present in the system I make.

### The individual
*Don't skip this one*

A rank needs adding as a child node to `species`. Whilst it is tempting, and common, to imagine the tree of life in descending order, this is *wrong* from the strict point of view of system design.

What does that even mean?

Simply put, we have created this tree of life by observing *individuals* and attempting to classify these *individuals*. We *can't* look at *'all life'* and subsequently try to split that up. The hierarchy is created from the *bottom up* from *individuals*, even if it can be viewed from either direction.

So what is the impact of that?

Other than keeping it in mind? Not a lot. *Individuals* are what we classify into the higher structure. They are a valid rank as follows, but they won't ever be part of the higher classification structures as they are the input to them.

>-- Kingdom
>
>---- Phylum
>
>------ Order
>
>-------- Family
>
>---------- Genus
>
>------------ Species
>
>-------------- *Individual*

From a system design point of view this means that *individuals* belong to *species* which belong to *genus* etc. However, as *individuals* are what this system takes as an input (as well as practical common sense), the rank of *individual* will not be part of the overall classification system. It's mainly a neat way of wrapping up responsibility and relationships.

### Versioning
*Skip this if you're not interested in long-long-term stability*

It is sheer hubris to believe that this document is going to catch every problem or possibility of a problem. In the [exo-biology](#exo-biology) section alone there are possibilities for problems that can't be solved right now. Thankfully, there's a really nice way to ensure easy communication across different versions of this structure.

By creating a rank at the very *very* top, above even any exo-biology ranks, we can version the whole structure:

>-- *Version*
>
>---- Kingdom
>
>------ Phylum
>
>-------- Order
>
>---------- Family
>
>------------ Genus
>
>-------------- Species
>
>---------------- *Individual*

A `kingdom` now belongs to a `version`. This `version` tag will need managing in a separate, non-linked table, as it refers to versions of the *structure* not versions of the *content*. For example, we can name our current demonstration structure 'alpha':

>-- *Version* :: **Alpha**
>
>---- Kingdom
>
>------ Phylum
>
>-------- Order
>
>---------- Family
>
>------------ Genus
>
>-------------- Species
>
>---------------- *Individual*

If the scientific community decides that `Superfamily` is now mandatory and common to all taxa, then a new version of the structure needs making to reflect this:

>-- *Version* :: **Beta**
>
>---- Kingdom
>
>------ Phylum
>
>-------- Order
>
>---------- Superfamily
>
>------------ Family
>
>-------------- Genus
>
>---------------- Species
>
>------------------ *Individual*

New versions should be created ***VERY*** carefully and with ***CONSIDERABLE*** thought. They will be disruptive to implement - but nowhere near as disruptive as the shift to this whole system, thanks to this planning.

## Custom Ranks
Now that we have a backbone we can allow user-defined custom ranks. As an example starting with:

>-------- Order
>
>---------- Family

we can add two ranks between Order and Family: Suborder and Superfamily

>-------- Order
>
>---------- Suborder
>
>------------ Superfamily
>
>-------------- Family

The trick then is how to express the contents of a `subfamily` to anyone not using this particular set of custom ranks. We can achieve this by simply going up *or* down the tree to the closest rank on the backbone. Go *up* if you would prefer to lump them all together, go *down* if you'd prefer to be able to separate them. After all, a `suborder` is a group of `families`, thanks to the hierarchy.

### A practical example
*Note: This isn't a perfect example as I have already cleaned up my act too much to have a bad example to use. Still, it shows how any rank may be expressed as the sum of the subranks*

**Raw data**
<details>

|Superfamily| Family | Genus|
|---|---|---|
|Pompiloidea|Sapygidae|Monosapyga|
|Pompiloidea|Sapygidae|Sapyga|
|Pompiloidea|Pompilidae|Aporinellus|
|Pompiloidea|Pompilidae|Cryptocheilus|
|Pompiloidea|Pompilidae|Episyron|
|Pompiloidea|Pompilidae|Auplopus|
|Pompiloidea|Pompilidae|Dipogon|
|Pompiloidea|Pompilidae|Calicurgus|
|Pompiloidea|Pompilidae|Agenioideus|
|Pompiloidea|Pompilidae|Anoplius|
|Pompiloidea|Pompilidae|Aporus|
|Pompiloidea|Pompilidae|Homonotus|
|Pompiloidea|Pompilidae|Evagetes|
|Pompiloidea|Pompilidae|Salius|
|Pompiloidea|Pompilidae|Pompilus|
|Pompiloidea|Pompilidae|Caliadurgus|
|Pompiloidea|Pompilidae|Arachnospila|
|Pompiloidea|Pompilidae|Priocnemis|
|Pompiloidea|Pompilidae|Ceropales|
|Pompiloidea|Mutillidae|Smicromyrme|
|Pompiloidea|Mutillidae|Myrmosa|
|Pompiloidea|Mutillidae|Mutilla|
</details>


Here, the `family` *Sapygidae* may be expressed as the sum of the `Genera`:
|Genus|
|---|
|Monosapyga|
|Sapyga|

*Pompilidae* is therefore expressed as the sum of:

|Genus|
|---|
|Aporinellu|
|Cryptochei|
|Episyron|
|Auplopus|
|Dipogon|
|Calicurgus
|Agenioideu
|Anoplius|
|Aporus|
|Homonotus|
|Evagetes|
|Salius|
|Pompilus|
|Caliadurgu
|Arachnospi
|Priocnemis
|Ceropales|

Finally, *Mutillidae* is expressed as the sum of:
|Genus|
|---|
|Myrmosa|
|Mutilla|

By going to the next backbone rank below the custom rank, the contents of that custom rank can be shared across multiple customised sub-versions preciesly.

### Communal subranks
One of the key facets is that it is possible for groups to come together to define 'communal' sub ranking systems. As an example if enough people studying bats believe that `subgenera` is a core aspect to their work, they can decide to create a custom rank database with the rank of `subgenera` that others can use. The normal limitations apply: anyone *not* using this custom rank database will be able to communicate at the `species` level, preserving information.

The core idea here is to establish the backbone as the taxonomic lowest common denominator. It is practically impossible to create a single system which will cater to every need of every single person studying every living thing. Instead it is far better to create an expandable framework, with guidance on how to apply the standardisation, so that people may communicate as freely as possible without being constrained. Science is about discovering new things after all, which frequently involves the need to create new systems as new information arises.

### Below the backbone
It is not possible to transfer information about ranks below the lowest non-individual rank on the backbone. This is an unavoidable logical fact. For example:

The backbone stops at `species`

Custom Ranking 1 (CR1) goes below `species` to `subspecies`

Custom Ranking 2 (CR2) goes below `species` and `subspecies` to `infraspecies`

All three systems are limited to talking at the level of `species` through the backbone. However, should the owners of the custom ranking systems desire, they can easily implement their own translation system to communicate at `subspecies` level. This would require CR2 to build off of CR1, so that their `subspecies` layers were identical. This is achieved through the principle of *extensibility* that got mentioned under [this chapter](#wibbly-wobbly-rank-things).

### Extendable design
*This section goes into some design-technical aspects. If you are looking to create your own custom ranking, you can't skip this and will need to understand (or find someone else to understand) this section.*

The key take away from this section is that this system of managin ranks is inherently *extensible*. The process is replicate - there's an exposed rank object by the parent tree, which can have subranks attached to it by the child tree. This child tree can then act as a parent tree itself.

```
Parent
|
|- Child
    |
    | - Subchild
```

This is just another relational structure extension. As long as the child rank correctly references the parent's primary key, the subsystem will integrate perfectly while allowing freedom of development by multiple sources.

Also, very importantly, creating a custom ranking system that buds off of the backbone does not require the attention nor permission of any administrators in the parent system.
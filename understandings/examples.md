# Examples
## Normal use
Examples of the Understandings System during normal use.

> We didn't have one so we used a key as basis
> 
> Ellen is attempting to find out the person from FERA, but don't hold my breath
### Adding a new interpretation
In 2016, *Vespula velutina* was first sighted in the United Kingdom. Whilst the public regularly confuses this species with multiple other taxa, it does not take much ability to identify. This first confirmed record in 2016 was from the area of Tetbury - a highly suspicious location for any of the usual colonisation routes that such organisms take. *Vespula velutina* is, however, well known for synanthropic dispersal. Many specimens have since turned up in fresh vegetables from countries such as France.

With this information, we can now evaluate the presence of 'significant, widespread, confusion'. Our taxon is easily recognised, and almost certainly not present in the area for a significant amount of time before its recognition. Accordingly, there is close to zero potential for confusion. *Vespula velutina* is therefore added to the Understandings system as an *addition*.

Now that we know the operation to use, we need to find a suitable author and year to use as the basis for our Understanding. The year is easy - 2016. The author is a little harder. Ideally, we want to have a person as the author, as that allows us to tie a decision to a person rather than a faceless organisation where it could be any number of people. If we do not know the person, then we have a much harder time knowing if the person *got it wrong* when identifying the taxon. Not so much a problem when working with a taxon this simple, but absolutely crucial for the majority of situations. We have three options here:

- Identify the person who performed the identification
- Use the generic name of the Understandings System implementation
- Pick a reliable key to use

#### Identify the person
In this scenario, we find out who the person was that identified the specimens from Tetbury. There are any number of avenues we can take. Contacting the organisation that performed the organisation is the most straightforward, though in our scenario slightly more complex as the organisation has been absorbed and moved through various names since then. In smaller and more niche situations, the pool of potential identifiers is often small enough that *someone* knows who it is directly. Asking around can often find out the answer very easily.

For purely demonstrative purposes we will use the fictional name 'Arvdan', who wrote their paper 'Vespula velutina *in Great Britain*' in 2016. This produces the Understanding of `Vespula velutina: iso. Arvdan: 2016`.

#### Use the generic name of the Understandings System implementation
Each implementation of the Understandings Systems comes with its own 'generic' name. This name can be anything, but is recommended to be the same as the organisation managing the implementation. In this scenario, the organisation is BWARS, providing the Understanding `Vespula velutina: iso. BWARS: 2016`.

#### Pick a reliable key to use
When faced with a situation where we don't have a known author to base an Understanding on, we can instead fall back on a key to provide *an* author for a citable reference. The same guidance applies to selecting a key as does selecting a taxonomic work. The ideal key should:

- cover the geographic region in question
- cover the temporal range in question
- provide the means to uniquely identify the taxon in question

In this example, we can use Archer's 1989 key. This key covers the Channel Islands, where *V. velutina* is known to have been found for a while as a synanthropic import. The Channel Islands are directly adjacent to the subject area for this example, and it is a reasonable assumption that it is the same strain that will eventually colonise the south of England.

Using the Archer key produces the Understanding `Vespula velutina: iso. Archer: 1989`.

### Splitting an Interpretation
In 2025, the UK population of the ant *Tetramorium caespitum* (Linnaeus, 1758) was found to contain specimens of *Tetramorium alpestre* Steiner et al, 2010. The first question is, as always, on the presence of *significant, widespread, confusion*. Ants in the UK tend to attract far less attention than bees or even wasps, typically being very difficult to identify. As a result, when changes are found in established ant taxa, there tends to be a significant degree of confusion when examining past data. Such is the case in this instance, with the authors finding significant material of each taxon within the existing pool of data. This confusion is also *widespread*, as the confusions within that pool of data covers almost the entire range of the originating taxon. The answer is therefore that there *is* significant, widespread, confusion. To add the newly discovered presence of *Tetramorium alpestre* thus requires the use of a *split*.

The author of this split in this scenario is easy to find. The discovery was published in the British Journal of Entomology and Natural History:
> Jarman, A.P. and Seifert, B. (2025) The alpine ant, Tetramorium alpestre Steiner et al., 2010, newly recognised as a native British species from Scotland (Hymenoptera: Formicidae). British Journal of Entomology and Natural History 38: 7-20

This information is perfect. We have the authors, which we can format appropriately to be 'Jarman & Seifert'. The paper details everything we need to know about the discovery, applies to the whole geographic range of the Understandings implementation, and provides the characters required for determination.

All that is left to do before we implement the `split` operation is find the original Understanding, which is

> Tetramorium caespitum: iso. Schlick-Steiner: 2006

We now have everything we need to perform a split. Our input understanding is `Tetramorium caespitum: iso. Schlick-Steiner: 2006`, our two output Understandings are `Tetramorium caespitum: iso. Jarman & Seifert: 2025` and `Tetramorium alpestre: iso. Jarman & Seifert: 2025`. We also need to make the aggregate that results from this split, which is `Tetramorium caespitum agg: iso. Jarman & Seifert: 2025`. All data of `Tetramorium caespitum: iso. Schlick-Steiner: 2006` is now considered to be of the aggregate `Tetramorium caespitum agg: iso. Jarman & Seifert: 2025`, preventing any extant data from interfering with the new Understandings. New data can be assigned to any of the now four Understandings present, in accordance with the determination made.

### Merging Interpretations
The most common use of merging is in dealing with synonymy. Under the rules of Interpretations, declaring an Interpretation to be a synonym of another Interpretation creates a `merge` operation. For an example of this, we will examine the synonymisation of *Passaloecus gracilis*, *Passaloecus insignis*, and *Passaloecus turionum* with the UK. This synonymisation does not have a paper directly attached to it that the BWARS scheme is aware of. Instead, the synonymisation comes from Guichard's 2002 key that covers these taxa. The use of this key is further sub-optimal for this scenario as the key itself is in French. The options to base the Interpretation on were this French key, or to write and publish an entirely new paper to use as a basis. In the interest of expediency, the French language key was used.

The input Understandings are:
- `Passaloecus gracilis: iso. Bitsch et al: 2001`
- `Passaloecus insignis: iso. Saunders: 1896`
- `Passaloecus turionum: iso. de Beaumont: 1964`

The output Understanding, using Guichard's 2002 key is `Passaloecus turionum: iso. de Beaumont: 1964`. All data previously ending at any of the inputs is automatically redirected to the output.

## Changing a name
Whilst there is the facade of conformity in the Linnaean taxonomic system, reality is far from conforming. A fairly frequent action taken is to 'rename' a taxon - either as the result of inadvertant synonymy or the discovery of an older name.

> ***IMPORTANT***
>
> 'Old' names which have simply fallen out of disuse for the global scientific community for significant periods of time should be **suppressed** upon discovery. Any and every change creates an increase in confusion. Increases in confusion should only happen if there is clarity to be gained from doing so. Reinstating an 'old' name because "that's what the code says to do" is ***not*** increasing clarity.

For this example, we will use *Andrena confinis*, which is the modern name for what was *Andrena congruens*, as per an article in the BWARS newsletter by Wood, 2022. Here, the name change is performed because the GB name was being used incorrectly. Changing brings the Understandings System in line with the international standard, thereby improving clarity at the slight cost of increased confusion.

Technically speaking, a name change is a merge with only one participant. Following the merge protocols, we find our input Understandings (only one in the case of a name change). In this situation, the input is `Andrena congruens: iso. Amiet et al: 2010`. We then find our output, which is `Andrena confinis: iso. Wood: 2022`, and use the input and output to perform a merge.

## Other use
### Data from before an Understanding's start
If a 'false origin' has been used to declare the first Understanding of a Type, there is a probability that data older than the date of the first origin may arrive in the system.

For example, the first Understanding of *Hylaeus pictipes* in our implementation of the Understandings System is `Hylaeus pictipes: iso. Amiet et al: 1999`. This Understanding is a *false origin*, using Amiet et al's 1999 key as a foundation. However, there exist multiple records of *Hylaeus pictipes* prior to this date. The question is then 'what do we do with the data that predates the Understanding?'.

The first question to ask is 'does this data represent a significant volume?'. The second is 'has this taxon been subject to significant confusion in the time before the current Understanding?'. Note that the answer to the second question may well be 'we don't know' - this is not a problem!

The next step is to use a risk matrix to decide on the action to take. A risk matrix in this situation is to examine the potential for *significant, widespread, confusion* to occur as a result of us making the *wrong* decision.

||Significant volume|Insignificant volume|
|---|:-:|:-:|
|**High confusion**|High risk|Moderate risk|
|**Low *or* unknown confusion**|Moderate risk|Low risk|

#### High risk
If the risk is *high*, then a new Understanding should be created. Try to avoid using the template Understanding author and year (e.g. BWARS: 2025) if at all possible, and instead root the Understanding. This new Understanding should be assigned as a junior synonym of the most appropriate currently valid Understanding.

In this scenario, we were able to identify the *probable* author and year of the pre-Understanding data. We then create the Understanding `Hylaeus pictipes: iso. Saun: 1894` and set it as a junior synonym of `Hylaeus pictipes: iso. Amiet et al: 1999`. The incoming old data is now transparently contained within `Hylaeus pictipes: iso. Saun: 1894` so that, if the need arises, the uncertain data can be immediately separated from the certain. As an example of need would be a discovery that Saun misused the name *Hylaeus pictipes*.

#### Low risk
If the risk is *low*, then simply use the current and more modern Understanding.

#### Moderate risk
If the risk is moderate, then first ask a taxon expert where they place the risk and follow either the low or high risk strategy. If the taxon expert also doesn't know, the scheme organisers should decide between
- More work, more confusion, but more precision (high risk)
- Less work, less confusion, but less precision (low risk)

There is no perfect answer to this scenario, and the correct route will depend entirely on what the taxon experts say or the scheme organisers decide. 

## The presence of significant widespread confusion
The presence of absence of significant widespread confusion is the most pivotal question when needing to add a new Understanding. The following examples present some guidance on how and why each action was chosen.

### Absence of significant widespread confusion
In 2023, a surveyor picked up an odd-looking wasp whilst conducting a survey near the Royal Portbury Docks. Whilst the surveyor could immediately identify the genus, the specimen did not conform to any of the small group of species known to be present in the country. Further consultation with available literature sources identified the wasp as *Eumenes mediterraneus*, which was not previously known to have been found in the country. As a new Understanding must therefore be created, the question of significant widespread confusion is then posed.

The largest hint to the potential of confusion in this scenario is the location in which the specimen was found: the docks. *Eumenes* contains a number of species which have been documented to spread via containers, as the metal walls of said containers offer an abundant and well suited site on which to construct their mud nests. In particular, *E. mediterraneus* is exceptionally commonly found using this technique - allowing it to spread widely across European ports.

The second hint is that the surveyor immediately picked the wasp out as different. There are two species of non-synanthropic *Eumenes* known in the Understandings region, one of which is vagrant. One other species is known synanthropically, though has only been seen once (that the author is aware of). The key aspect here is that the genus had *one* potential confusion with a resident and well-recorded taxon, and the surveyor discounted that one whilst in the field. It is therefore extremely unlikely that this species has been present in the region for any length of time, as surveyors would have picked it out. The probability of significant confusion is therefore incredibly low.

When it comes to the presence or not of widespread confusion, the predominant mainland species in the region, `Eumenes coarctatus: iso. Richards: 1980`, is only found in a very restricted range. This is likely a climate restriction, which tend to be very strictly delineated in this taxonomic group. Given the immediacy of identifying 'something different' the surveyor display, the probability of there being any widespread confusion within this very restricted range is very minimal.

In conclusion, the presence of *Eumenes mediterraneus* in the Understanding's region is almost certainly a synanthropic arrival via container ship. There is no evidence of significant confusion with any extant group, nor indeed any realistic probability of confusion at all. The correct course of action to take is to add *Eumenes mediterraneus* as a new Understanding rather than a split of an existing Understanding.

### Present
The names *Andrena scotica*, *Andrena carantonia*, and *Andrena trimmerana* have been embroiled in dispute for well over a hundred years. The genus *Andrena* is one of the largest genera of bees and covers a wide range globally. The genus is also known to have radiated quite substantially, suggesting a high degree of change is somehow inherent in the group. This combination of factors has led to a number of significant confusions in the taxonomic group


- Messy split with taxon that is everywhere and no-one knows where the problems are
- Andrena scotica/trimmerana

- Long standing disagreement over the presence & validity of taxa
- Andrena trimmerana was agreed upon, it exists
- Something else there, but not always easy to find
- 

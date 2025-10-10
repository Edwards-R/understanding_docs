# Examples
## Normal use
Examples of the Understandings System during normal use.
### Adding a new interpretation
In 2016, *Vespula velutina* was first sighted in the United Kingdom. Whilst the public regularly confuses this species with multiple other taxa, it does not take much ability to identify. This first confirmed record in 2016 was from the area of Tetbury - a highly suspicious location for any of the usual colonisation routes that such organisms take. *Vespula velutina* is, however, well known for synanthropic dispersal. Many specimens have since turned up in fresh vegetables from countries such as France.

With this information, we can now evaluate the presence of 'significant, widespread, confusion'. Our taxon is easily recognised, and almost certainly not present in the area for a significant amount of time before its recognition. Accordingly, there is close to zero potential for confusion. *Vespula velutina* is therefore added to the Understandings system as an *addition*.

Now that we know the operation to use, we need to find a suitable author and year to use as the basis for our Understanding. The year is easy - 2016. The author is a little harder. Ideally, we want to have a person as the author, as that allows us to tie a decision to a person rather than a faceless organisation where it could be any number of people. If we do not know the person, then we have a much harder time knowing if the person *got it wrong* when identifying the taxon. Not so much a problem when working with a taxon this simple, but absolutely crucial for the majority of situations. We have two options here:

- Identify the person who performed the identification
- Use the generic name of the Understandings System implementation

#### Identify the person
In this scenario, we find out who the person was that identified the specimens from Tetbury. There are any number of avenues we can take. Contacting the organisation that performed the organisation is the most straightforward, though in our scenario slightly more complex as the organisation has been absorbed and moved through various names since then. In smaller and more niche situations, the pool of potential identifiers is often small enough that *someone* knows who it is directly. Asking around can often find out the answer very easily.

For purely demonstrative purposes we will use the name 'Arvdan'. This produces the Understanding of `Vespula velutina: iso. Arvdan: 2016`.

#### Use the generic name of the Understandings System implementation
Each implementation of the Understandings Systems comes with its own 'generic' name. This name can be anything, but is recommended to be the same as the organisation managing the implementation. In this scenario, the organisation is BWARS, providing the Understanding `Vespula velutina: iso. BWARS: 2016`.

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
> 'Old' names which have simply fallen out of disuse for the global scientific community for significant periods of time should be **suppressed** upon discovery. Any and every change creates an increase in confusion. Increases in confusion should only happen if there is clarity to be gained from doing so. Re-instating an 'old' name because "that's what the code says to do" is ***not*** increasing clarity.

For this example, we will use *Andrena confinis*, which is the modern name for what was *Andrena congruens*, as per an article in the BWARS newsletter by Wood, 2022.

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

- Example of what happens when a record comes in from pre Understandings system start. e.g. 'Bombus terrestris' starts in 1956, but a record comes in from 1890. Record gets assigned to 1956 version, and then do a version with the 'trap' Understanding of 'Bombus terrestris: iso. BWARS: 1800'
- Systematic widespread confusion. Give example where there is minimal and where there is a lot of confusion.
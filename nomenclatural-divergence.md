# Nomenclatural Divergence
The core critical flaw in current Linnaean nomenclature that Understandings solve is the *nomenclatural divergence*. A nomenclatural divergence is a term for when the type concept and type name diverge in use from one another. In such a situation, there exists data under a type's name which no longer obeys the type concept. This mnismatch leads to all sorts of problems in any downstream applications of that name, such as Red Lists, genetic libraries, scientific papers etc etc. Nomenclatural divergence is the source of one of the largests wastes of time when dealing with scientific nomenclature - checking that all the nomenclature in a given sample/study are modern and trustworthy. Many researchers don't even realise that divergences *can* happen, which leads to some rather interesting scenarios. In one situation, two names were swapped over (*Hylaeus annularis* and *Hylaeus dilatatus*) during the focal period of a study. What is currently known as *H. annularis* has 36 total occurrence records in the total dataset. *H. dilatatus* has 1,579. This led to the researchers 'uncovering' a vast and sudden increase in *H. dilatatus*, with an accompanying catastrophic crash in *H. annularis*

![](image/hylaeus.drawio.svg)

This result was, of course, entirely false. The changes in perceived populations were driven entirely by the *nomenclatural divergence* in the data. The fault was noticed due to the researchers, who weren't taxon experts, doing the very intelligent thing of *asking an expert* when they found such a strong signal that had no obvious explanation.

## Solving Nomenclatural Divergence
Nomenclatural Divergence is, at its base level, caused by a *failure to implement version control*. Linnaean nomenclature, governed by the codes, states that there may only be one valid use of a name at one time. It would be forbidden to declare a new genus *Bombus* as a child of *Apidae*, given that one already exists. However, the codes and their accompanying systems do not have a provision to manage multiple instances of the same name, if only one of them exists at a time.

For example, the above example using *Hylaeus* was deemed valid according to the codes. The names never repeated themselves - there was one *H. annularis* and one *H. dilatatus*, and then there was one *H. dilatatus* and one *H. annularis*.

|Before|After|
|---|---|
|*Hylaeus annularis*|*Hylaeus annularis*|
|*Hylaeus dilatatus*|*Hylaeus dilatatus*|

Despite this apparent - and code compliant - continuity, there has been a nomenclatural disjunction. What was called *Hylaeus annularis* is now called *Hylaeus dilatatus*, and vice-versa.

|Before|After|
|---|---|
|*Hylaeus annularis*|*Hylaeus dilatatus*|
|*Hylaeus dilatatus*|*Hylaeus annularis*|

This leads to all sorts of interesting results, such as the above mentioned occurrence pattern. The reason is that although the *unique identifier* - in this case the name - has not been changed, the *idea* that the unique identifier represents *has* been changed. To any system architect, this is an immediate **red flag** - and it leads to exactly the situation we see here where the identifier diverges from the meaning.

The solution therefore is as simple as 'don't make beginner-level mistakes in your data system'. Nomenclatural Divergence is the first, and greatest, mistake made - and the easiest to fix. The solution is to add additional information to the name so that each individual version is distinguishable.

|Before|After|
|---|---|
|*Hylaeus annularis v1*|*Hylaeus dilatatus v2*|
|*Hylaeus dilatatus v1*|*Hylaeus annularis v2*|

## We don't stop there
The above example happened at the taxonomic level. The types themselves had their names swapped, changing their accepted names for everyone at the same time. But what about when a problem occurs in a more limited scope? What do we do then?

To examine this, we will pick the bumblebee *Bombus lucorum*, specifically in the range of the United Kingdom and Ireland. *Bombus lucorum* within this range - and surrounding regions - has been the subject of longstanding uncertainty as to whether there is only *Bombus lucorum*, or whether there are other species present in a cryptic complex. In 2008, a paper was published that laid the matter to rest - *B. lucorum* in the United Kingdom and Ireland was indeed a complex of multiple species.

|Before|After|
|---|---|
|*Bombus lucorum*|*Bombus lucorum*|
||*Bombus cryptarum*|
||*Bombus magnus*|


However, this could not be considered a *taxonomic* change as other regions had already resolved this situation - with differing results per region. This leaves us with a very large problem - there exists data as *Bombus lucorum* which does not correspond to the current interpretation of the type of *Bombus lucorum*. Once again, we have a *nomenclatural divergence* that needs solving. This time around, we already know the cause of divergence - the meaning of the item has changed whilst the name has remained the same. This means that we can copy the solution from before:

|Before|After|
|---|---|
|*Bombus lucorum v1*|*Bombus lucorum v2*|
||*Bombus cryptarum v1*|
||*Bombus magnus v1*|

Now we know that if we encounter *Bombus lucorum v1* that it represents the aggregate of:

- *Bombus lucorum v2*
- *Bombus cryptarum v1*
- *Bombus magnus v1*

This version of nomenclatural divergence is at the root of why *every single one* of the 'global taxonomic list' projects have failed. Such projects will continue to fail until this is addressed - and this *includes* genetic libraries that attempt to use Linnaean nomenclature in any shape, way, or form.

## Not quite the end
An added complication arises with the second instance of nomenclatural divergence: where does the version number go? If the type of *Bombus lucorum* starts at *v3*, does that make the regional version *v4*?

|Before|After|
|---|---|
|*Bombus lucorum v3*|*Bombus lucorum v4*|
||*Bombus cryptarum v1*|
||*Bombus magnus v1*|

Who maintains the unique list of regional variations in that case, to prevent re-use? 

|Before|After (UK)|After (Sweden)
|---|---|---|
|*Bombus lucorum v3*|***Bombus lucorum v4***|***Bombus lucorum v4***|
||*Bombus cryptarum v1*|*Bombus cryptarum v2*|
||*Bombus magnus v1*|*Bombus magnus v2*|

What about when a taxonomic change needs to happen? What version does that change stem from if all the options are regional variations? Clearly there is a little more work to do yet.

## Conclusion
We have examined two instances of the same critical failure within the Linnaean system where changes to objects within the system do not have their changes reflected in their identifiers. These failures can be rectified very easily, but there is a lingering problem in the design space of where the solutions should be placed.
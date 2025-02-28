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

The solution therefore is as simple as 'don't make beginner-level mistakes in your data system'. Nomenclatural Divergence is the result first, and greatest, mistake made, and the easiest to fix.

> Fix it by adding a bit more information to make it unique again
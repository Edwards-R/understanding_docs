# Separation of concerns: Types and Interpretation
The last section demonstrated the use of human-centric labels for the type version and interpretation, as well as an object relational model for their use. However, the largest problem remaining is the sheer amount of information present in each label. To fully communicate itself, each label must have the type, type version, and interpretation within in. This will never change, as it is the bare minimum required for from-zero communication. Using most standard design templates, it is possible to separate the stack of labels so that users can reference only the information that they need, allowing the background systems to fill in the remainder. However, the use of this separation will 'lock' the user to a particular system, due to the regionality of the interpretation layer.

## A refresher on non-global nomenclature
An original flaw in the type-controlled-only taxonomic/nomenclatural system is that it is only possible to make controlled changes to the entire scope of a population. For example, taxon *T* is present in areas *1*, *2*, and *3*. It is found that, in only area *3*, the taxon *T* has been misidentified. What is understood to be *T* is actually a mixture of *T* and *U*. Under a type-controlled system, there is no way for people in zone *3* to incorporate this knowledge into any nomenclature or taxonomy. *T* as a type has not changed - it is the understanding of *T* within *3* that has. As a result, there will exist uses of *T* from within *3* that do not match the type and are known to not match the type. This state is *nomenclatural divergence*.

## Separating Concerns
The first step is to separate the concerns of the various areas of taxonomy and nomenclature. Concerns belong to the type must remain globally applicable, whilst concerns belong to interpretation become regional. The areas to separate are the three pieces of information which compose a full interpretation:

- Type
- Type Version
- Interpretation

Of these three, the Type and Type Version are concerned with the creation of a globally applicable list of types, their versions, and the names by which they should be referred to with. The Interpretations are concerned with maintaining a region's adherence to the globally applicable list. Using this information, along with our object relationship diagram, it is possible to split these three components into these two concerns:

- Type controlled
    - Type
    - Type Version
- Interpretation controlled
    -Interpretation

At this point, the general design of the type controlled responsibility is completed: there exist types, which have versions made of them. All types apply globally, and are the ultimate point of reference and agreement. However, interpretation responsibility still needs the regionality aspect of its design explaining.

## Interpretations and regionality
 The critical aspects of interpretation regionality are:

- How does this design not fracture taxonomy?
- What is the correct size for a region?
- How do users communicate across regions?

## Conclusion
We have separated the concerns of the type and the concerns of the interpretation. Baring the exact system design implementation, the area of responsibility for types is now completed. Implementations, on the other hand, require more explanation and detail on their mechanics, especially in ensuring their adherence to existing conventions.
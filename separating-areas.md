# Separating areas
So far, we have identified two instances of a fundamental flaw in Linnaean nomenclature which are leading to divergences between a type and its name. We then proceeded to use standard design methods to provide a standard solution, then used scientific standard practices to turn the engineering solution into a more human-friendly version. However, using the same solution to both problems means that there are two sets of the same versioning attributes. One set applies to the type, the other to the interpretation. What is now required is to provide an easy to use method of distinguishing between uses of the taxonomic and interpretation layers.

## Separating the layers in writing
To reach the finest level of detail, and solve both instance of nomenclatural divergence, we need to know three things:
- The name of the taxon in question (binomials are a special case and should be treated as species-level)
- The version of that taxon's concept
- The interpretation of that taxon's concept's version

### Defining an example case
In order to progress, we need to define an full example to work with. This example will be entirely imaginary to avoid getting into any complex, or potentially outdated - real world scenarios.

|Type Name|Type Author|Type Year|
|:-:|:-:|:-:|
|Krekorus|Nigole|1837|

This example type has had its type concept changed multiple times. We start with the default, which is then changed by *Amand* in 1911, who then changed it again in quick succession. Finally, *Hollan* changed the type concept in 2017, where it currently rests.

|Type Name|Type Author|Type Year|Type Version Author|Type Version Year|Type Version Number|
|:-:|:-:|:-:|:-:|:-:|:-:|
|Krekorus|Nigole|1837|Nigole|1837|*1*|
|Krekorus|Nigole|1837|Amand|1911|*1*|
|Krekorus|Nigole|1837|Amand|1911|*2*|
|Krekorus|Nigole|1837|Hollan|2017|*1*|

Over time there have been multiple interpretations of these type versions. Each new version of the type necessitates a new interpretation. This can be seen as the interpretation version follows the type version, up to the point where Hollan gets involved in 1990. Here, Hollan decides to create a new interpretation of the type version. This interpretation is then found to be globally applicable, and becomes a type version in 2017. Since there is a new type version, a new interpretation must be created.

|Type Name|Type Author|Type Year|Type Version Author|Type Version Year|Type Version Number|Interpretation Author|Interpretation Year|Interpretation Number|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|Krekorus|Nigole|1837|Nigole|1837|*1*|Nigole|1837|*1*|
|Krekorus|Nigole|1837|Amand|1911|*1*|Amand|1911|*1*|
|Krekorus|Nigole|1837|Amand|1911|*2*|Amand|1911|*2*|
|Krekorus|Nigole|1837|Amand|1911|*2*|Hollan|1990|*1*|
|Krekorus|Nigole|1837|Hollan|2017|*1*|Hollan|2017|*1*|

### Separating out information
The layout of this information immediately provides a number of standard template solutions to the challenge of clearly laying out information. Our information naturally breaks down to three components:
- Type
- Type version
- Interpretation

These can be broken down further into the exact information that they each require:

- Type
    - Name
    - Author
    - Year
- Type Version
    - Author
    - Year
    - Number
- Interpretation
    - Author
    - Year
    - Number

The organisation of these three aspects can also be laid out using standard design templates. An interpretation belongs to a type version, which belongs to a type. One type may have one-to-many type versions. One type version may have one-to-many interpretations. This relationship may be documented with an object relationship diagram.

![](./image/ord.drawio.svg)

With this organisation of data, anything from a type to an interpretation may be condensed into any object communication patterns, such as XML, YAML, TOML, JSON etc.

### Full stack or short stack
With the advent of a relational model, it becomes possible to shortcut longer processes in certain situations. For example, if the type, type version, and interpretation are all linked in the manner prescribed, it is possible to identify the full stack from the interpretation alone. However, this 'short stack' will only work *within an individual instance*. To follow more, we need to understand the limitations of the interpretation area. We previously stated that *interpretations are also potential results of non-global modification*. These non-global modifications mean that there is a need for multiple collections of entries in the interpretation area, one to service each 'non-global' area. Such a revelation raises a number of questions. What size should each 'non-global' area be? Why are separate areas needed? What are the mechanisms for sharing data across these areas?

## Conclusion
We started off with a desire to simplify the way in which we can write out a full set of nomenclature, from type to type version to interpretation. Whilst ee have identified standard template patterns that allow us to do so, additional areas of optimisation and query still exist. The impact of the interpretation layer being formed of multiple collections of entries raises a number of questions which still need answers.

[Next](./separation-of-concerns.md)
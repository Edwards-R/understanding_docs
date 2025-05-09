# Layers in taxonomy
Previously, we identified and started the process of solving the issue of nomenclatural divergence. However, the solution encountered a series of design problems which need to be overcome. Specifically, the solution identified two distinct varieties of nomenclatural divergence, and it was not at all clear how to implement the version control that the solution demands. Thankfully, we can once again use well-established system design patterns to solve this almost instantly.

## Separation of Concerns
In software parlance, a 'concern' refers to a specific area of responsibility for a given part of a design. For example, a sending a letter via post can be considered to have four concerns:

- A postbox to hold mail for pickup
- A person to collect the mail from the postbox
- A place to sort the mail and decide where to send it
- A person to deliver the mail

Using the idea of concerns, we can solve our problem of versioning in a very neat manner: changes to the *type concept* belong in the *taxonomic* realm of concern, where as changes to regional nomenclature to better match the taxonomic concept exist in a (relatively) novel realm of concern. This more novel concern will henceforth be referred to as the *interpretation* layer, as it is concerned with managing the various regional interpretations of the type concept.

## How does this fix our problem?
Now that the two areas of taxonomy and interpretation have separated, the versioning follows the same procedure. First, apply the version to the type, e.g.

> *Bombus lucorum v4*

Next, apply the interpretation version to the versioned type, e.g.

> *Bombus lucorum v4* **v3**

This gives us the 3rd interpretation of the 4th version of the type. When a taxonomist wishes to review the type, they act on the 4th version of the type. The '3rd interpretation' of that type is irrelevant to them, and is simply ignored. The resulting type would be version 5:

> *Bombus lucorum v5*

As this is a new version of the type, this also spawns the first interpretation of that version of the type:

> *Bombus lucorum v5* **v1**

The taxonomists may now operate safely and securely on the type, and the interpreters of the type may now create as many versions of their interpretation as they desire, without interfering with taxonomy.

### Version numbers are very hard to follow
Whilst the versioning system *works*, version numbers are very hard to follow along with for many people. Easy comprehension is especially critical for systems designed for human consumption, as this redesign of the Linnaean taxonomic system is. What is needed is a clear, familiar, system of identification that is easily human comprehensible.

## Conclusion
We have used the principle of the separation of concerns to divide the proposed system into the taxonomic and interpretation areas. Using these areas, we applied taxonomic versioning and interpretation versioning independently, solving the issue of managing different versions across different interpretations. However, the end result uses an abstract number as the version identifier, with very little to aid in human comprehension.

[Next page](./human-centric-labels.md)
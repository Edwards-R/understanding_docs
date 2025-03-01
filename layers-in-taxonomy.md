# Layers in taxonomy
Previously, we identified the issue of nomenclatural divergence. However, this solution ended with a conondrum: there are two distinct nomenclatural divergences, and it was not at all clear how to implement the version control solutions. Thankfully, we can once again use well-established system design patterns to solve this almost instantly. Indeed, it will take far longer to explain *why* the pattern works than it took to identify the problem and arrive at the solution.

## Separation of Concerns
In software parlance, a 'concern' refers to a specific area of responsibility for a given part of a design. Traditionally, the teaching method for the separation of concerns tends to take the form of a pedal-powered bicycle. The handlebars steer, the pedals provide power, the wheels enable the bike to move, the brakes allow stopping etc. These systems interact, but they each have their own defined role. These roles can be deconstructed further if required. For example, the pedals have a place to put feet, a bearing that allows pedals to rotate, a crankshaft that allows power to be transferred etc. We can also go in the opposite direction and use our bicycle as part of a larger whole - in this case, a bicycle can form part of a transportation network. The exact definition of concerns and their place in various layers is part of the 'art' of system design, without hard rules. Luckily in our nomenclatural scenario, the lines of definition are very clear.

### Taxonomy vs Interpretation of taxonomy
The first area of concern in our taxonomic system is the declaration and management of the types themselves. This area covers what has traditionally been more controlled and regimented within the taxonomic system. Anything that impacts the global interpretation of the type occurs within this area.

The second area of concern in our taxonomic system is more novel, though not unprecedented by any stretch of the imagination. This area, known as the *interpretation* layer, handles the various complexities that are neccesary to apply the idealised taxonomic area to reality.

The distinction of these two areas can be very clearly seen in the examples in the section on nomenclatural divergence. Situations where the modification is performed on the type, such as with *Hylaeus annularis* and *Hylaeus dilatatus*, belong in the **taxonomic** area. Situations where the modifications are made to regional names in order to better match the types belong in the **interpretation** area.

Put another way, one area is concerned with *what the types are*, the other is concerned with *making sure that the names people use accurately correspond to the types*.

## How does this fix our problem?
Now that the two areas have separated, the solution follows the same procedure. First, apply the version to the type, e.g.

> *Bombus lucorum v4*

Next, apply the interpretation version to the versioned type, e.g.

> *Bombus lucorum v4* **v3**

This gives us the 3rd interpretation of the 4th version of the type. When a taxonomist wishes to review the type, they act on the 4th version of the type. The 3rd interpretation of that type is irrelevant to them. The resulting type would be version 5:

> *Bombus lucorum v5*

As this is a new version of the type, this also spawns the first interpretation of that version of the type:

> *Bombus lucorum v5* **v1**

The taxonomists may now operate safely and securely on the type, and the interpreters of the type may now create as many versions of their interpretation as they desire, without interfering with taxonomy.

### Version numbers are very hard to follow
Whilst the versioning system *works*, version numbers are very hard to follow along with for many people. Easy comprehension is especially critical for systems designed for human consumption, as this taxonomic/interpretation system is. What is needed is a clear, familiar, system of identification that is easily human comprehensible.

## Conclusion
We have used the principle of the separation of concerns to divide the proposed system into the taxonomic and interpretation areas. Using these areas, we applied taxonomic versioning and interpretation versioning independently, solving the issues that the idea of versioning started with. However, the end result is an abstract number with very little to aid in comprehension. A more human-centric label is required.

[Next page](./human-centric-labels.md)
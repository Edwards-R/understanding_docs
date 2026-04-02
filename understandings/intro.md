# The Understandings System
The Understandings System is a practical implementation of interpretation layer. It is designed to be widely deployable, and does not require the full taxonomic layer to be developed before it can be used. The current, as of 2026, Linnaean taxonomic system will work as the backbone, though some functionality will inevitably be lost. This loss in functionality is entirely related to the lack of taxonomic versioning. Should a versioned taxonomic system be developed later, any implementation of the Understandings System will be able to upgrade to it with very minor effort.

## Something about what an Understanding is
The Understandings System is built out of components, known as Understandings, and the rules on how to manage these components. Each Understanding is a direct implementation of an interpretation, as defined by the system design documentation. Understandings are modified by the Understandings System by using procedures known as Operations. However, before we can talk and demonstrate Operations, we need to discuss how Understandings are written.

## Writing an Understanding
The Understandings System does not specify any single way in which an Understanding must be written. Instead, the Understandings System specifies the minimum information that any method of writing an Understanding must contain. This minimum information is:

- Taxon name
- Interpretation author
- Interpretation year of declaration

This approach has been taken in order to separate the concerns of *managing* Understandings from *writing* Understandings. Both concerns are, to some degree, novel and experimental. By separating these concerns, changes to one aspect will have minimal impact on the other.

### The Default option
The Understandings System has been developed alongside a writing system, known as the [**iso System**](iso-system.md).

---
---



> End it here, that's enough in one page
>
> Next page goes into the Understandings system
>
> We can now write an Interpretation in one, albeit fairly long, line. This line, according to the principles of Interpretations, carries the entire taxonomic and nomenclatural status in it. The next step is to examine the Understandings System to see how this information is created and maintained.
---


## Regional bounds
> - UK & Ireland
> - Ireland because the Irish taxa for this group is a subset of the UK by geography

## Temporal bounds
> - Utterly impractical to go back to the start
> - Lots of lost data
> - Some recoverable, some not
> - Standard practices hide a *lot* of changes to maintain the illusion of conformity
> - Pick the point where most of the region's data starts to comes from
> - Get as close to that date as possible
> - Modern systems are creating orders of magnitude more data than old
> - Modern nomenclature is the focus (~1960 for BWARS)

## Defined epithet meanings
> - Did not use 's.s.' & 's.l.'
>   - Latin (people don't tend to know Latin)
> - 'agg' for nomenclatural aggregates
> - 'cpx' for human-defined complexes (**not** governed by Understandings System)

## Type vs Interpretation
> - Types need the ICZN to agree to do something
> - Not going to happen quickly, if at all
> - Interpretation-only systems do not have the backing that would make cross-system communication easy
> - They do however allow people to solve nomenclatural disjunctions
> - Cross-system comparison is doable, just slower and manual
> - Have to respond to taxonomic alterations manually

## Next section
> - How does the Understandings System manage these Understandings?

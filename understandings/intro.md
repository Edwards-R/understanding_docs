---
parent: Understandings
title: 1. The Understandings System
---

# The Understandings System
The Understandings System is a practical implementation of interpretation layer. It is designed to be widely deployable, and does not require the full taxonomic layer to be developed before it can be used. The current, as of 2026, Linnaean taxonomic system will work as the backbone, though some functionality will inevitably be lost. This loss in functionality is entirely related to the lack of taxonomic versioning. Should a versioned taxonomic system be developed later, any implementation of the Understandings System will be able to upgrade to it with very minor effort.

## Writing an Understanding
The Understandings System does not specify any single way in which an Understanding must be written. Instead, the Understandings System specifies the minimum information that any method of writing an Understanding must contain. This minimum information is:

- Taxon name
- Interpretation author
- Interpretation year of declaration

This approach has been taken in order to separate the concerns of *managing* Understandings from *writing* Understandings. Both concerns are, to some degree, novel and experimental. By separating these concerns, changes to one aspect will have minimal impact on the other.

## The Default option for writing
The Understandings System has been developed alongside a writing system, known as the [**iso System**](iso-system.md).
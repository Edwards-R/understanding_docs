# A Technical Explanation

## 2NF to 3NF
The current way of handling nomenclature is second normal form. It focuses on the structuring of the reference objects and completely misses the fact that references to those objects are just that - *references* - and not the objects themselves. In true textbook manner, the result is a many to many relationship: many names refer to many types. The solution is, again, textbook, and involves the creation of the missing component to turn a many to many into two one to many relationships.

## Composite keys to avoid serials or hashes
Primary keys are designed as a composite of the information presented (parent/name/author/year/count), with count existing as a deadlock-breaker. Composite keys are specifically selected here as the target audience tends to be fragmented and disparate, with a generally low awareness and interest in managing data systems. The information in the composite key, other than 'count', are all (to some degree) familiar to the target audience, increasing the probability of correct usage.

## Reading Understandings
Understandings are designed to be machine readable via regex.

### Space-agnostic regex
`^([^:]+): {0,1}iso. {0,1}([^:]+): {0,1}(.+)`

|Capture group|Contents|
|:---:|:---:|
|1|Name|
|2|Author|
|3|Year|
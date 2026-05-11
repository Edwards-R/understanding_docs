---
parent: Operations
title: Split
nav_order: 2
---
# Split
A split takes a single Understanding and returns multiple Understandings, plus an aggregate Understanding.

## Complexity
A split is the most complex of operations, as it produces the greatest number of additional currently valid Understandings.

In some situations, it is preferable to use create rather than split. These situations are governed by the rule of 'significant, widespread confusion'. This rule is designed to protect the integrity of data at the cost of a very slight penality to nomenclatural purity. Split operations can cause dramatic losses of data as a result of the split. Most of the time, this loss in data is unavoidable and necessary to maintain taxonomic precision. Sometimes, this loss in data can be avoided by using create instead of split. The rule of 'significant widespread confusion' guides users as to which path to follow.

## Significant Widespread Confusion
The rule of significant widespread confusion is to ask a taxon expert the question: 'is there significant widespread confusion surrounding the interpretation of this Understanding?'. Start by examining whether the confusion is *significant*. If the answer is 'no', consider using a create operation rather than a split. If the answer is yes, ask whether the confusion is widespread. If the answer is no, consider using a create rather than a split. If the answer is yes, use a split.

It is entirely valid to disregard the rule of significant widespread confusion and perform a split. It is not valid to disregard the rule and perform a create. The penalty to over-using splits will be a reduction in the amount of data which can be maintained across a split.

### Significant confusion
The amount of data that is in doubt due to the presence of multiple Understandings is significant.

For example, if only ~1% of 212 records are estimated to be affected, this would not be significant. The determiner error in those 212 records is probably higher. If 30% of those 212 records were estimated to be affect, that would certainly be significant.

### Widespread
The geographic spread of the confusion covers a significant portion of the taxon's range, there is widespread confusion. If the spread of any confusion is extremely localised, consider using a create rather than a split. An example of a localised confusion would be a taxon arriving on the south coast of England from France. Whilst there may be significant levels of confusion locally, that confusion is just that - local. A change to the Understandings, which would encompass the entire Understandings region, may well be excessive as a solution.
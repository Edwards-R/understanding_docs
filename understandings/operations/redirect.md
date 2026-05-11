---
parent: Operations
title: Redirect
nav_order: 4
---
# Redirect Operation
A redirect is a corrective measure taken to rescue data. A redirect involves changing the resolved Understanding of a non-current Understanding.

## Complexity
Medium. Whilst the initial complexity is low, there are a number of edge cases that can cause concern. Take care to strictly follow the restrictions.

## Restrictions
> **Definitions**:
>
> *Current Understanding*: An Understanding that resolves to itself
>
> *Non-current Understanding*: An Understanding that resolves to a different Understanding

A redirect may only be used to change a non-current, non-aggregate Understanding. The end point must be a current Understanding.

## Example
The simplest example of using a redirect is a merge which is then reverted through the use of a split. Remember that operations may not be rolled back, only move forward.

Given a start point of

|Taxon|Resolved|
|:-:|:-:|
| A | A |
| B | B |

The merge produces

|Taxon|Resolved|
|:-:|:-:|
| A | C |
| B | C |
| C | C |

The split of C then produces

|Taxon|Resolved|
|:-:|:-:|
| A |D (agg)|
| B |D (agg)|
| C |D (agg)|
| D | D |
| E | E |
|D (agg)|D (agg)|

We trust that all data of A is D, and all data of B is E, since the decision was that the merge was in error. However, all data of these Understandings currently routes to D(agg) due to the rules of a split. We want to recover that data, so we redirect A to D and B to E

|Taxon|Resolved|
|:-:|:-:|
| A | D |
| B | E |
| C |D (agg)|
| D | D |
| E | E |
|D (agg)|D (agg)|
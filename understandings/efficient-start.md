# Starting an Understandings System efficiently

- Introduce the idea of a false temporal origin
- Why
- How


When creating a new instance of the Understandings System, the majority of the work involved is in sourcing the various nomenclatural and taxonomic changes across history. Changes in Interpretations have historically been performed in a rather roundabout manner, which frequently leaves little or no accountability for that change. When attempting to document such changes for use in the Understandings System, a frequent result is that no-one knows where or when a change came from. To handle such situations, there are a couple of helpful methods that can be used.

## Using a key as a point of reference
Keys are, quite often, the main points of reference for historic changes to the Interpretations of taxa. Whilst keys may not meet the full criteria for being the basis of an Interpretation, they do provide a generally accessible method for identifying taxa in a traceable manner. Keys also have the added benefit of providing a large swathe of Interpretations at once, which greatly speeds up the process of creating a new Understandings System.

Over-use of keys may lead users to believe that the Understandings System *only* uses keys, and that they should write the author and year of publication of a key rather than use an Understanding. As the system incorporates more changes that are linked to sources other than keys, the confusion will decrease. As Interpretations become more mainstream, the confusion will also decrease.

## False origin
Attempting to uncover the origins of historic changes in Interpretations can be a very time consuming and expensive task. This time and literal cost tends to increase the further back in time the change happened. To cap costs, it is worth considering a false temporal origin for an Understandings System implementation. Changes older than a certain point are simply ignored, as the cost-benefit of including them is below the implementer's threshold.

When considering a false origin, the most important things to consider are the following:

### Data to cover
The primary driver of the 'benefit' of the cost/benefit analysis is derived from the presence of data that the Understandings System needs to cover. If there is no data to benefit from being covered by the system, then there is little benefit to spending the time researching the changes in Interpretations. When picking a false origin, consider when there stops being sufficient data to be worth covering. This point will change from region to region, and group to group. Consult with experts in appropriate taxonomic groups within the area that the Understanding System implementation is to cover and decide from there.

Different sub-groups of taxa within the same implementation may have different false origins, if deemed appropriate.

### Availability of documentation
One of the primary drivers of the cost of retrospectively identifying changes to Interpretations is the availability of documentation covering the change. The main tipping point for this aspect is digitisation. Once the time period crosses outside of the period of digitisation, availability can plummet. Keys are often the only remaining accessible record of changes, and even keys tend to become harder to find when looking far enough back in time. At a certain point, documentation ceases to exist or skips multiple steps. If considering a false origin, this is where to start.

## Picking the false origin start point
Identify both the data to cover and the availability of documentation. Next, pick the earliest point where there is data to be covered, and a continuous lineage of documentation.

```
                          Time
Documentation ||---xxxxx-----------------||
Data          ||           ==============||
                           ^
                      Start here
```

### Dealing with data prior to the false origin start point
Occasionally, data will arrive that was created prior to a false origin start point. There are two options to use:

- use the false origin
- research and declare an earlier Interpretation

The option chosen will depend on many factors, the main ones being:

- the volume of data involved
- taxon expert opinion
- value of the data
- potential for confusion

If there is minimal volume of data, minimal value of data, low potential for confusion, and no hidden aspects or importance that taxon experts can assign, it is simplest to simply use the oldest Understanding in the system. Otherwise, consider making a new Understanding.
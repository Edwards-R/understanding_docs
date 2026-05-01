# A Case Study in Understandings - BWARS
This section covers the non-software creation and implementation of the Understandings System using the UK's Bees Wasps and Ants Recording Society (BWARS). It is hoped that having an example will provide a reasonable reference point for other people making their own Understandings System implementations.

The Understandings System was developed on BWARS data. *Many* mistakes were made during this process, and multiple approaches that eventually didn't work were trialled. This document will not cover everything that didn't work - provided the solution has been found.

## Setup
### Geographic Remit
The geographic remit (the area which the system will cover) is quite simple for BWARS. BWARS covers England, Scotland, Wales, Northern Ireland (with some Ireland data too), the Isle of Man, and the Channel Islands. The Understanding System implementation geographic scope will therefore be the same.

### Temporal Remit
To find an appropriate temporal remit 'starting point', the BWARS dataset was examined. The BWARS dataset extends back to 1800, though data remains extremely lower on a per-year basis until 1890. No year prior to this point possesses over 200 records. From 1890 to 1970, records remain relatively steadily below 1,000 records/year. There is a slight 'bump' from 1938 to 1947, almost certainly from a museum project that digitised old notebooks. From 1970, the volume of data in the BWARS dataset drastically increases. By 1991 there are ~ 9,000 records, and by 1998 ~ 24,000 records.

These brackets allow us to split time into zones of priority.

|Zone       |Priority|
|-----------|--------|
|     - 1970|Low     |
|1970 - 1991|Medium  |
|1991 +     |High    |

The second aspect to consider for the temporal remit is the availability of data to support Understandings. This data primarily came from two sources:

- Taxon expert knowledge
- Keys available in said taxon expert's library

Once alterations became more modern, papers started to become available. This was practically not until the advent of digitally available publishing, around ~ 2000.

The taxon expert's knowledge is predominantly the past 60 years (i.e. back to ~ 1960), but there is an amount of *their* teacher's knowledge that creeps in, extending that timeframe slightly.

The keys available dated back to 1896 (*The Hymenoptera Aculeata of the British Islands* - Edward Saunders (1896)), the next being the 1919 Perkins key. For ants, Bolton & Collingwood was used as the basis, which is a 1975 publication. Various other keys were used to provide reference points for changes, for which the taxon expert's knowledge was essential. All keys were heavily used and featured frequent notes on what the 'new' name was - not all of which were still correct. The notes *were* extremely useful in deciphering what had happened between various keys.

Combined, these two factors provided enough knowledge to cover the medium (1970 - 1991) and high (1991 +) timespans in adequate resolution. Our temporal remit therefore starts at 1970, as this is where there is sufficient knowledge from.

### Ranks
BWARS uses:

- Superfamily
- Family
- Subfamily
- Genus
- Species

These are all, thankfully, relatively well documented and usable. There is also the capstone rank, with the sole entry of 'BWARS'.

### Creation
All that remained was the incredibly tedious task of creating the various Understandings. This was handled by the taxon expert, who was provided with an Excel sheet of everything to fill in. All currently valid nomenclature was mandatory. Any non-current nomenclature could be left blank (see later section for how this was handled).

Once this Excel sheet was filled out, a script was used to load the data into postgres. There was no Understandings System with cleanly defined operations at this point. Everything was done manually, with great trepidation. Making a single mistake could cause significant cascading errors, requiring a restoration from backup.

## Maintenance
The largest barrier to maintenance was the conversion of taxonomy to Interpretations. Authors tend to still write papers proclaiming 'the absolute truth' of a taxon, only for people of a specific region to say 'that's not how *we* do it'. Thankfully, BWARS maintains a small journal that provided a place to start creating Interpretations. The journal is not open access, and therefore imperfect, but it is a far better resource than simply allowing changes to magically 'happen'. BWARS is thankfully in a position where there will be *someone* who knows the author of a paper, or knows someone who knows someone etc. This linkage allows BWARS to query any leftover edges in various papers in order to create any relevant Interpretations (or ignore papers if they do not cover the BWARS spatial remit).

The second largest barrier (ignoring the fact that I created an entire structured and documented system to handle the rapidly rising complexity of what has become the Understandings System) was, and continues to be, the lack of comprehension as to *why* such a system is even necessary. By far the best way for someone to realise that *something* needs to change is for them to stumble over a problem that Interpretations solve. It might still take some time, but stumbling face-first into the problem of 'what version of this name are you talking about' seems to be the most universally reliable of introducing Interpretations. Education is an ongoing task - of which this entire project is a large part. The scenario is truly one where, once the problem is identified, it starts to crop up *everywhere*.

## Limitations

### Older data
Very occasionally, data from outside of the BWARS Understanding System's temporal remit will occur. The largest source of this tends to occur when an experienced recorded retires. Upon retiring, people typically hand over 'all the data I have'. There are now very very few people living who started, or maintain data from, outside of the temporal limit. However, data *can* still arrive from outside. These names can cause a brief uptick in maintenance as new non-current Understandings have to be added, but the disruption is very minor.

### Poor nomenclatural wider understanding
There are a number of projects which claim that they contain 'all known synonymy' of various taxa. These project are, when used outside of their intended geographic scope, absolute landmines of odd nomenclature. More than once I have had a well-meaning recipient of the BWARS data make outlandish claims as to what specific names mean, based on a random 'checklist' that they have found on the internet. When someone makes a claim that a name needs to change, double check that said person truly knows what they are doing!

### The Pollinator Problem
During recent times, there has been an explosion of interest in 'pollinators'. This interest has attracted funding, which in turn has resulted in a large number of changes to our interpretation of taxa - as well as the discovery of new taxa within the area. BWARS has tracked nearly 100 total 'changed or new' Understandings over 10 years. These changes will typically occur in batches as various papers are published or retracted. Keeping up with the latest changes is a substantial task, especially when the source documentation does not meet the criteria for use as the basis of an Interpretation and someone has to write a supplementary article.

### Non-UK Keys
Some of the best available keys were not UK based, or even written in English. Aculeate Hymenoptera are, compared to mammals and birds, very sparse on keys. As such it was (and to some degree still is) fairly common to need to utilise keys in languages other than English. Non-English keys are a poor source, as per the rules of Interpretations. However, they are often taxonomically the best source, which means concessions must be made. In an ideal world there would be an article written to bridge this gap, but that is extra work on top of everything else BWARS is doing - and none of it funded.

### Understandings without a source
All current nomenclature must have a fully scope source with author and year of declaration. However, there exist a great number of non-current names where the origin is entirely lost to time. Since all Interpretations *must* have an author and year of declaration, one must be found. The solution is to use the capstone details as the Interpretation - in this case giving '*X* iso. BWARS: 2024'

### Vanity taxonomy
One of the great destroyers of data is vanity taxonomy. There are *constantly* projects that attempt to 'standardise' nomenclature by applying 'Latin' grammar to it. These projects are, and this will make me rather unpopular in some circles, complete and total vanity. They serve no purpose other than self-congratulation and 'academic' frippery. All that comes out of such projects is confusion and destruction of data. BWARS has allowed me to put a complete and total stop to such projects influencing the Understandings implementation, for which I am extremely grateful.

### Applying Understandings to Keys
Most people use keys to determine and keys do not, at least as of 2026, come with Understandings. Members of BWARS have solved this problem by creating lists of the Understandings used in various publications. These lists are then published by BWARS, though they are far from a complete set. Future keys will have the Understandings either written in, or provide space for readers to write them in should there be sufficient applicability outside of BWARS's remit.
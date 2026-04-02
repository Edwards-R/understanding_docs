# The iso System
Short for 'In the Sense Of', the iso system is a method of writing Understandings. The method has been specifically designed to be both human and machine readable, regardless of language. An iso format Understanding is written as follows:

    Taxon: iso. Author: Year

In the event that a numerical identifier is required, the number is appended as follows:

    Taxon: iso. Author: Year: Number

The taxon can be a single identifier e.g. Genus, or multi-part e.g. Binomial.

    lucorum: iso. Murray et al: 2008

    Bombus lucorum: iso. Murray et al: 2008

## Speaking an iso format Understanding out loud
When speaking an iso-formatted Understanding, it is recommended to use the full 'in the sense of' rather than the abbreviated 'eye-so' or 'i.s.o', as it will help people unfamiliar with the Understandings System follow what is happening. As with all abbreviations, only use them as abbreviations if all participants are clear on their meaning.

## The construction of the iso format
This section breaks down why each part of the iso format exists

### Separators
Regions of the Understanding are separated by colons `:` so that automated systems can read the format. This character is prohibited from use by the various nomenclatural conventions, easily readable and writeable by humans, and is therefore the perfect separator.

### The 'iso.' block
The 'iso.' block has two purposes. The first is to denote that this is an 'iso'-formatted Understanding. The second is to provide an extremely clear end to the taxonomic name. The nomenclatural codes do not apply retroactively, which means that older names can have characters that are forbidden under current practice. By placing a known block at the end of a name, the potential oddity of any name is encapsulated.

The only additional restriction that this block places upon nomenclature is the the phrase 'iso.' may not form part of any name. Current nomenclatural codes prevent the use of `.` in modern nomenclature, so the potential for exclusion is only from names prior to the nomenclatural code.

## Regex
Regular Expressions (regex) are the de facto tool for string matching in most computing. An iso format Understanding may be identified and read with the following needle:

`^(.+)\: iso\. (.+)\: (\d{4})(?:\: (\d*))?`

This will produce capture groups as follows:

|Capture group|Meaning|
|-------------|-------|
|1            |Taxon  |
|2            |Author |
|3            |Year   |
|4 (optional) |Number |

## Writing iso formats in text
> This section is experimental and does not reflect a finished suggestion.

A significant drawback of Understandings is the amount of attention they require to read. A full Understanding can be a very long piece of text, akin to an in-text reference (which is what it is). Experimentation has shown that placing the 'iso. Author: Year: Number' in subscript can improve readability.

> Our work found that there were 24 nests of <i>Bombus lucorum</i>: iso. Murray et al: 2008 in the survey area

> Our work found that there were 24 nests of <i>Bombus lucorum</i>: <sub>iso. Murray et al: 2008</sub> in the survey area

Alternatively, placing the entire Understanding in italics can help - though it does nothing to separate out the taxon name.

> Our work found that there were 24 nests of <i>Bombus lucorum: iso. Murray et al: 2008</i> in the survey area

## Conclusion
Now that there is a way to write Understandings, we can move on to how to the Understandings System manages Understandings.
---
layout: post
title: Writing a Spell Parser
author: Cameron
# if you don't have a github account or you do not wish to share it
#  leave the next line out
github: aosdict
# change to true to publish
published: true
# first line followed by a ...
excerpt: Up until now, Table Tome had only about a dozen spells...
---

# {{ page.title }}

{{ page.date | date_to_string }}
{: .meta}

Up until now, Table Tome had only about a dozen spells, and they were all hand-entered. Not a good way to do the rest, since there are about 400 total in the Player's Handbook and the Elemental Evil companion. So I set out to make a parsing script to extract them all from a data source and convert them into a Tome-friendly format.

The issue, as I found out, was that there really isn't a complete data source for the spells. Trying to convert the rulebook PDFs directly results in text with a lot of random spaces dropped into the middle of words. Since I didn't want to make a separate program to reconstruct them, I set out looking for other sources. [This repository](https://github.com/tadzik/5e-spells) has _most_ of the ones from the Player's Handbook, but not all, and it doesn't include any Elemental Evil spells.

The best source I found was [donjon.bin.sh](http://donjon.bin.sh), which provides a bunch of random generators and other tools in addition to a complete 5e spell list that includes Elemental Evil. It still isn't perfect, because a few dozen descriptions don't exist for some reason, and no materials lists exist at all, and those will have to be manually entered. But it's the most complete source, and after a little digging around on the site I found a per-spell JSON API.

So I set to work making a shell script to download first the initial list of spells, and then loop over those spells and make an API request for each of them. As that progressed, though, I felt more like doing it all in BASH was very clunky and it would be quite difficult to parse through the Donjon JSON and generate our own. I decided to switch the main logic into a Node script, which would give me a lot more leeway in crunching the data. This script is still called by a parent shell script, but it deals with all the actual API requests and parsing.

I struggled a bit with asynchronicity and making HTTP requests from Node, since I'm still fairly new to it, but I got it all working. The main parsing code only has to deal with a few things, such as renaming and lowercasing keys and values to make them Tome compatible, and parsing through a couple of the fields that are represented as different or more complex types in Tome. 

Currently, it generates a file called 'tome_spells.json' which contains an array of all the objects ready to be inserted into the database. The script doesn't actually insert them automatically yet, but it does everything else. The mongoimport command needed to pull the file into the database is documented in the getSpells.sh script.

With this, I was able to successfully bring all the spells from both sources into my local database.

-- _{{ page.author }}_ {% if page.github %}_([github@{{ page.github }}](https://github.com/{{ page.github }}))_{% endif %}
{: .meta}

---
layout: post
title: Playing Catch Up
author: Dan Lowe
# if you don't have a github account or you do not wish to share it
#  leave the next line out
github: Danlowe95
# change to true to publish
published: true
# first line followed by a ...
excerpt: I've been a side contributor to Table Tome off and on for awhile...
---

# {{ page.title }}

{{ page.date | date_to_string }}
{: .meta}

I've been a side contributor to Table Tome off and on for awhile, this time because Jon wanted to revive Table Tome as part of our Intro to Open Source final project.  Our project was essentially a re-write of the site using new methods that Jon implemented to make the site cleaner and more secure.  By the time I got started on the project Jon had already done a giant portion of the necessary work, porting over the old site's functionality in new code and implementing Auth0, Semantic UI and Showdown.  My contribution to the project was to make the base implementation of User Profiles (which Jon then took and made beautiful and fully functional), and to help implementing the ability to edit and delete user spell lists.  My job was made much less complicated due to the fact that Jon had already implemented a lot of the backend and behind-the-scenes functionality to make everything work cleanly.

I will most likely not be contributing much to Table Tome in the future, but hope that its development will continue and gain a userbase.




-- _{{ page.author }}_ {% if page.github %}_([github@{{ page.github }}](https://github.com/{{ page.github }}))_{% endif %}
{: .meta}

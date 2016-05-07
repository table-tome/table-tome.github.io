---
layout: post
title: Learning is Slow, but Necessary
author: Jon Wrona
# if you don't have a github account or you do not wish to share it
#  leave the next line out
github: jonwrona
# change to true to publish
published: true
# first line followed by a ...
excerpt: I'm going to start by saying that there has been a lot of progress on the new Table Tome in just a few months...
---

# {{ page.title }}

{{ page.date | date_to_string }}
{: .meta}

I'm going to start by saying that there has been a lot of progress on the new Table Tome in just a few months. A couple of weeks ago I was telling myself that there wasn't too much of a chance that myself and a few others would have completed all of the features that had previously existed (in their messy state) plus more. In fact I didn't think that we'd have it to the previous state at all.

I was very wrong. I underestimated how much time I had spent learning instead of implementing while developing the first iteration of Table Tome. Learning is a slow process, but it is necessary. This time around I was able to focus less on figuring out how to use Node and Angular and more on writing clean and concise code.

On top of that, there are **TONS** of services out there that only make a developer's job easier. Right now I'm thinking of [*Auth0*](https://auth0.com/). The last iteration used a user authentication system that I created myself. This included everything from sending emails regarding registration and email confirmation to user settings. *Auth0* made implementing all of that incredibly fast and (in my opinion) very easy to do well.

I'm proud to say that Table Tome is not only in the state function wise that it was before, but that it is much more extensible and the code is better documented (it can and will improve though).

The next step for me once a few more features are in place is to go back and learn once again how to test javascript code, both on the front-end and the back-end. This will most likely slow down my development effort over the summer (as well as starting a full-time job), but this project isn't going anywhere if I'm still around to contribute.

Maybe I'll manage to get some help from a couple of students from the [Rensselaer Center for Open Source](https://rcos.io) during the next school year too...

-- _{{ page.author }}_ {% if page.github %}_([github@{{ page.github }}](https://github.com/{{ page.github }}))_{% endif %}
{: .meta}

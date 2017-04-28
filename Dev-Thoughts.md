# Web Developers are young
Interesting thought I just had: I can't think of a single web developer I follow that is over the age of 40.

Older developers have likely settled on platforms that change less often. They have a family to spend time with, and they can't waste their weekends on staying in the know.

# You'll know that you are senior in a team when you answer more questions than you ask

# I think one of the most impactful things you could do is to write. Write and share.
Videos, audio, etc all count, too.

Thought about while considering the impact of Google's Material design docs.

# Tech Debt snowballing
Problem with hacked code and tech debt is that it snowballs. When a dev is rushed to implement something, it is left in a hacky state. When another dev goes to modify/ maintain/add to that section of code, s/he sees that it is in a hacky state, doesn't want to be the one to clean it up, then hacks on top of it. hacky code on hacky code.

Easy enough for short-term projects to just barely get by before imploding, but long-term is not sustainable. You have to dilligently avoid and remove hacky code, ASAP!

Is this why offshoring didn't work out?

# Almost anything in isolation is easy
this is why time predicting is so difficult

tasks only promote thinking about isolated issues

Any actionable items for this regard chronstruct? A feature to help account for our isolation bias?

"Small, isolated problems
are much easier to deal with
than big intertwined problems"

# Easy vs Hard for web
Its easy to get a Carousel. Its hard to get a carousel that is performant and meets all the criteria we'll want.

Its easy to animate on desktop. Its hard to animate on mobile, must not change geometry.

Thought about while reading https://twitter.com/Vjeux/status/849679214756352000

also " it's hard to justify that amount of time spent on getting from 90% to 100%" - https://twitter.com/Vjeux/status/849680617713188864

# Text editors are not magic
Really loved skimming this "How to Build an Editor" article: http://viewsourcecode.org/snaptoken/kilo/04.aTextViewer.html

Made a magically thing more real. Every little feature that users just expect, like cursor being bound by screen dimensions, scrolling, syntax highlighting, overriding default terminal keys, etc must be coded!

# "Game Loop" technique
The "Heart Beat" of your site/app. Relates to raf and 60fps.

Interesting that the browser employs the same strategy of game engines: a function that runs as many times as possible that update()s the state of the world, then draw()s the state of the world.

React brought the Game Loop to front-end dev with the virtual dom?

Thought about while reading https://www.sitepoint.com/quick-tip-game-loop-in-javascript/

# Dev-celeb burnout
I believe I am good at solving pain points and friction. It is really tempting to solve my own friction and go down the rabbit hole of developer experience, but I don't think that'll lead to long-term happiness. Long-term happiness comes from affecting myself AND others. Also, long-term happiness comes from building, often from building REAL things.

This is a problem I think some dev celebreties face. They continue down the dev experience/tooling route because they are caught up in their fame. This is short-term happiness. They need to continue working in this area to stay relevant. They burn out eventually because they are stuck in a loop of only impacting themselves and other devs.

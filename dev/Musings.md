# Web Developers are young
Interesting thought I just had: I can't think of a single web developer I follow that is over the age of 40.

Older developers have likely settled on platforms that change less often. They have a family to spend time with, and they can't waste their weekends on staying in the know.

# You'll know that you are senior in a team when you answer more questions than you ask

# Easier in isolation
Much easier to attack something in isolation.

Made me think that senior devs are for thinking about more things: perf, whole apps, accessibility, etc. Other devs _should_ be more productive, or have a higher speed, because they can remain focused on closing tickets (isolated pieces of work)... less concerns when working on isolated things. Senior devs should be slower, but focused on velocity and moving in the right direction.

Maybe this is what management is for? Allowing people to stay on isolated tasks?

# I think one of the most impactful things you could do is to write. Write and share.
Videos, audio, etc all count, too.

Thought about while considering the impact of Google's Material design docs.

# Tech Debt snowballing
Problem with hacked code and tech debt is that it snowballs. When a dev is rushed to implement something, it is left in a hacky state. When another dev goes to modify/ maintain/add to that section of code, s/he sees that it is in a hacky state, doesn't want to be the one to clean it up, then hacks on top of it. hacky code on hacky code.

Easy enough for short-term projects to just barely get by before imploding, but long-term is not sustainable. You have to dilligently avoid and remove hacky code, ASAP!

Is this why offshoring didn't work out?

Below's image perfectly matches this:

![https://twitter.com/chopeh/status/926074073767206912](https://pbs.twimg.com/media/DNoTdMMWsAEL_GR.jpg)

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

- [Sunil Pai on Twitter: "At the risk of alienating some peeps... can't wait to write closed source code for real products again. Less noise, more prod."](https://twitter.com/threepointone/status/865709610623053824)
- [Eric Clemmons on Twitter: "@threepointone You get more successes this way, too. I've stepped back from OSS because it's the ROI isn't there."](https://twitter.com/ericclemmons/status/865723597997867009)
- [TJ Holowaychuk's answer to Has TJ Holowaychuk been as prolific in the Golang community as he was in the Node.js community? - Quora](https://www.quora.com/Has-TJ-Holowaychuk-been-as-prolific-in-the-Golang-community-as-he-was-in-the-Node-js-community/answer/TJ-Holowaychuk)
  - "my new goal is to live a better life. In the end open-source doesn’t pay the bills so it’s best to focus on other things if you can"
  - "I write code 2–3 hours a day unless I’m really into something. Time is your real currency!"
- "And this is why many open source developers join large companies and disappear. Because open source sucks." "I don't think I can do open source ever again. We built @yarnpkg in private and then open sourced. Quickly after I lost all motivation." - [Sebastian McKenzie](https://twitter.com/sebmck/status/879283865902346244)
- "Step #1 of making a living as a solo dev, don't cater to people who won't pay you, because they'll never pay you." "Open source only works if you're paid by a company or VC, if you have skills don't waste them for free." - [TJ Holowaychuk](https://twitter.com/tjholowaychuk/status/879880358916837376)
- [Why I (mostly) dropped off twitter – @getify](https://medium.com/@getify/why-i-mostly-dropped-off-twitter-6fe5cf5c5e2f)
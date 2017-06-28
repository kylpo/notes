Handles states first, then build transitions
- e.g. Supply w/ starting route

---
Conventions are crucial
- initialProps
- no _functionName
- file structure
- __er is a manipulator/injector
- thing is a wrapper and introduces something to dom
- use ListView instead of ScrollView for cases that Thomas brought up

----------------------
Two very different phases of a project

Exploration: highly volatile. Everything will need to be bundled together and monolithic to enable quickly changing things. Not iterating as much as ripping out and starting down a new path.

Stable-ish: In iterating mode. Much more of a pleasure to break things out into separate concerns. Micro-services do well here. Get to focus on one aspect of your bugfix/feature at a time, able to more easily think about and create automated tests.

Figuring out when the right time to switch phases will likely present itself. Make sure you account for that when you estimate timing of a project though.


-----------------------


Prototyping
- Highly susceptible to change
  - Use <Animate_> instead <FadeIn_>
  - Better example is probably to use <Event_> instead of <Click_> because you’ll likely add a hover or drag event to it
- Think of the <Event_>, <Style_>, <Animate_> components as a @decorators to the <View /> components
- Tools and techniques should be focussed entirely on the developer experience.
- code should be easily copy/pasted
- have powerful abstraction layers, starting with strong foundational, single-purpose ones
- [Write code that is easy to delete, not easy to... — programming is terrible](http://programmingisterrible.com/post/139222674273/write-code-that-is-easy-to-delete-not-easy-to?utm_source=hackernewsletter&utm_medium=email&utm_term=fav)

“When I'm building features in React I sometimes can't type as fast as I'm thinking and it's frustrating. Never has WPM been my constraint.”
https://twitter.com/ryanflorence/status/783758188445257728



"When I first started, I obsessed over file organization. Now I put everything into one giant file until I'm absolutely forced to split it."
https://twitter.com/acdlite/status/780841390494187521

"As a programmer you read more code than you write. Keep it readable, commented, consistent & explicit."
- https://twitter.com/gotboompah/status/740286839907581952


but this isn't true for prototypers. We write a LOT of code.


Most likely, you'll want to build out the UI and features as quickly as possible. Because the data's shape is likely to change in the process, prefer using good ole' React Router, component State, and Context for data management. Or maybe just straight up Redux for its tooling advantage? Once you're happy with the UI and features, progressively introduce graphql and relay, with the end result yielding components without state or context.

This approach really helps you single-task. Otherwise, it is a bit overwhelming how much work you have to do and keep in your head.

My Starter should account for this.



-----------
Deciding on rules makes simple things easy. When you have a collection of tools and idioms of easy things, you're  better able to tackle the hard things.

-----------

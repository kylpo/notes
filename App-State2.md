_WIP_

---

Live Data vs Persistent Data

---

[How to choose the right database for your microservices \- SD Times](http://sdtimes.com/choose-right-database-microservices/)

- Ephemeral Data (client cache)
- Transient Data (logs, messages, signals (high volume))
- Operation Data (user session, shopping cart)
- Transactional Data (permanent records requiring ACID)

---

[React.js: The Hard Parts](https://www.aomran.com/react-the-hard-parts/)

Program state has a long history in computer science, but essentially it’s just the “condition” that our program is in. If we’re rendering a tweet, then its state will be things like contents, the number of likes, the number of retweets, whether it’s expanded or collapsed, etc.

In traditional server-rendered apps we don’t have to worry about state changes. If a user interacts with your application or refreshes the page, then we’ll look up state at that moment and rebuild the page.

In dynamic apps, like ones built using React, state change has to be dealt with immediately. If a user clicks “retweet” then the rendered tweet needs to change instantaneously.

If your app is very dynamic (hence React) then you’ll be juggling a lot of states. To complicate things even further, what if someone from a different computer clicks “retweet” – how do we update state for everyone looking at that tweet? Moreover, some states are user-specific and possibly not saved at all, for example, whether navigation on the page is fully open or collapsed.

- Read the "Single Source of Truth" parts, too.

---

[URLs are UI - Scott Hanselman](https://www.hanselman.com/blog/URLsAreUI.aspx)

# App State and App Data
For the purpose of this post, let's define `Data` as being data from a persistent source. It may be from a server, a client cache, a static json/xml file, a database. Either way, it is persistent and static.

What then is App State? The oposite of Data?

Sometimes App Data is all you need. Or maybe it is that they are the same (both exist in URL). No, because URL isn't temporal. It is idempodent even.

Data is updated as a transaction

Something that muddies this is optomistic updates. It is state until server comes back as success, then it is data. Or is it just state for the lifetime of your app, then becomes data on refreshes?

Data is still used to hydrate state.



# Sources of truth in your app
How many sources of truth do you have in your app/site?



# Data and State
Lets talk about Data. Data and State. Persistent data, and temporal state.

[Shape your redux store like your database – Hacker Noon](https://hackernoon.com/shape-your-redux-store-like-your-database-98faa4754fd5)



# UI State
- [How To Manage UI State With Redux – codeburst](https://codeburst.io/how-to-manage-ui-state-with-redux-24deb6cf0d57)



"Uhhh, obviously things that your app keeps in its state?"

But really, what is it?

Is it data that comes from you server or client's cache? No.

Is it state stored in your React component's `this.state`? It could be, but not always.

Is it anything that lives in your Redux stores? Not necessarily - there are really useful Redux libs for forms, which only exist on a single page.

So, what is it?

*I'll be thinking through this as a React developer using components to build apps, but the concepts should apply broadly.*

# What it isn't (or, Data vs State)
Let's start with what it isn't. It isn't _Data_. Data is usually fetched from a data fetcher like Relay, Firebase client, a Service Worker, a client cache, or your own home-rolled solution using `fetch()` or `ajax`. It is static, unchanging.

It isn't `passProps`

Had a hard time answering this when I asked it to myself.


Data vs State

# Characteristics of App State

![](https://lh3.googleusercontent.com/UKjfxNJys6e1lUIJMng-j8UncBKFYivKSaMB_MxN1Cug1FOhMiiIqrvWYS00EC2jpgk6Y-amXeMROVUT2MwR8zVMPTOBNdFYmUg5awIqdYjF_dTWc5Up1fOSCc5rm1opJNlW9xqOTyL6Q6-6rUScjPrtZC8YKVOZJOzapG2R8ilLx43Ki1zCHwlea9cWvGtNIhpOSNto-Nlazlz03DWkstM8mTGl-BneLh9LoIiVIY2qvyF2aWivwB8KB1EebciiRLVdga0DW6RqgcKfyE3zs4qENDu7vsk6G2okv1bsCbfQsmqbvTcC6wKN1vrf40IBQlbTgkvlgckG3cK4Aur1w01YLFns6ry8kT-pW1rxG7a5_jiov9FNbSXoMVeuCtld5tevWw8Y-e97p2eUU3TbhFvscVlkaZaJ5ERpK2Lm13TR3coiIeQ9r-P8eQXbZZaAL9rm8xoETIM1WYsjjBKhDK4H9rRv1huYb-20AvAmMheEwTEBJLknf266BA6RSKgl7K1Ji10ChakL6k1r3Gnfcf2bB1c_MXB-u3esoxUmwb3qz3ma8xCG_1eT90oGWiw37-W0cn3QaawL4jF4xVdRvwKt1_Su1FpYifl7-Ba5F-3tayvmjNycQhnN724RPdQ2IZn18gLvHCUY36qnxV5y7DufhPYjLjdOl1Na=w1710-h1283-no)

Breadth and Depth
Temporal and Persistent
Can have multiple sources of truth
- url, global.appState, redux/mobx store
Is different from data

[FormidableLabs/freactal: Clean and robust state management for React and React-like libs.](https://github.com/FormidableLabs/freactal)

[When Does a Project Need React? | CSS-Tricks](https://css-tricks.com/project-need-react/#article-header-id-0)

[Michel Weststrate on Twitter: "State management is not about eliminating mutability or side effects, but about controlling them. Usually by applying FP in some areas"](https://twitter.com/mweststrate/status/870552901613002753)

- [Redux is the Pivotal Frontend Innovation – Max Lynch – Medium](https://medium.com/@maxlynch/redux-is-the-pivotal-frontend-innovation-a406736552cb)
  - [Kristofer Baxter on Twitter: "Great state management makes everyone on your team more productive. Investment here is important. https://t.co/MxQmqhXmsN"](https://twitter.com/kristoferbaxter/status/872507897137078272)
  - [(1) Dion Almaer on Twitter: "State and data. Offline and syncing. Real-time and not. Massive knowledge graphs and small personal sets. Let's do this. https://t.co/uDdjxKaiee"](https://twitter.com/dalmaer/status/872503383554260993)

[React State vs. Redux State: When and Why?](https://spin.atomicobject.com/2017/06/07/react-state-vs-redux-state/)
- short, medium, and long term
- breadth and depth
- breadth -> global
- depth -> passprops
- one reason for redux's confusion is that we use it for two separate use cases
  - a Store is not necessarily app state
  - e.g. redux-forms

Maybe it should be rephrased to: Global (not app) vs Local state. I like this better because I don't like calling sites "apps"

Started with a question: "Types of App “state”: `data` (that you usually render), `routes` (url and history), `UI` (controls like open panes). Can anyone think of a missing category in that list?"

App State
- data
  - models
  - collections
- routes
- UI
  - controls

Maybe it would be better to think of app state scope in terms of "how long it should last". When thinking about a form, for example, your first inclination is to keep that as the form's local state. onSubmit it'll be sent somewhere and become data. But what about the scenario where a user goes Back, then Forward in history? If you want to retain the fields s/he has filled out, that state would need to live outside of the form's local state (since it'd be unmounted on the Back).

So maybe it isn't so much about data > global > local, it is more about persisted > session > temporal?

App state is temporal?
- not always. temporal wouldn't exist in URL.

Relay to manage __DATA__. Redux to manage __App state__.

When user is entering form data, it is app/local state. As soon as submit, that state is cleared and replaced by Data.

# Scene vs Stage
Scene is an individual page. a sequence of continuous action in a play

Stage is the entire app shell.  platform on which actors, entertainers, or speakers perform.

Scene will use the Stage. E.g. using its scrollbar.

---

data is essentially the models and collections that are rendered in a simple todo app, for example.

What about auth state and feature flags?

“current tab” made me think about renaming `routes` to `browser state`

Is the url just a serialized form of UI state? Plenty of sites preserve everything in the url, even form input. Like the Babel repl.

In that sense, App state is actually UI state. Data is just stuff from the server (and likely cached locally maybe in mobx/redux, but shouldn't be considered app state). Maybe there’s an advantage in treating them separately, not “just in MobX”, or “just in /stores”.

Should `Controls` of an app be denoted with a naming convention? Controls like Modals, Stage Left, Stage Right, etc

Sometimes URLs are enough. url is often the serialized form of app state:
- http://caniuse.com/#search=pointer%20events
- Babel repl

URL -> App State -> Views
- uni-directional, from `yester`

What about scene-specific state?
- nested mobX providers do work, so just add `Provider`s at scene level, then components can `@inject`
  - [Nested Providers? · Issue #114 · mobxjs/mobx-react](https://github.com/mobxjs/mobx-react/issues/114)

State
- App
  - `this.props.AppOverlay`
- Scene
  - `this.props.SceneSidebar`
- Component (local)
  - `this.state`

[Building Skype on ReactXP - ReactXP Blog](https://microsoft.github.io/reactxp/blog/2017/04/27/building-skype-on-reactxp.html)
- "Some stores within the app are singleton objects and are allocated — and perhaps even populated — at startup time. Others are allocated on demand and have a well-defined lifetime that corresponds to a user interaction or mode."
- "Stores are responsible for maintaining in-memory data representations."

# Router
- only needed for SPAs
- otherwise, it'd be at Express level
- all must provide `<Link />`
- https://github.com/basarat/yester
- https://github.com/elefanty/offramp
- [A different approach to routing in Single-Page Applications — Vincent Prouillet](https://vincent.is/testing-a-different-spa-routing/)

State boils down to __sources of truth__


Data: [Rearchitecting Airbnb’s Frontend – Airbnb Engineering & Data Science – Medium](https://medium.com/airbnb-engineering/rearchitecting-airbnbs-frontend-5e213efc24d2)

# Domain State
- Stores: responsible for a _subdomain_ in the app: users, todos, view
- Models: data model + actions for a _concept_ in the app: user, address, todo
- from https://twitter.com/DavidBaldie/status/864418823881068544

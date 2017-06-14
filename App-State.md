_WIP_

# What is "App State"?
"Uhhh, obviously things that your app keeps in its state?" But really, what is it?

Is it data that comes from you server or client's cache? No.

Is it state stored in your React component's `this.state`? It could be, but not always.

Is it anything that lives in your Redux stores? Not necessarily - there are really useful Redux libs for forms, which only exist on a single page.

So, what is it?

# What it isn't
Let's start with what it isn't. It isn't _Data_. Data is fetched from something like Relay, Firebase client, a Service Worker, a client cache, or your own home-rolled solution using `fetch()` or `ajax`.

Had a hard time answering this when I asked it to myself.


Data vs State

# Characteristics of App State

Breadth and Depth
Temporal and Persistent
Can have multiple sources of truth
- url, global.appState, redux/mobx store
Is different from data


I'll be thinking through this as a React developer using components to build apps, but the concepts should apply broadly.

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

Great questions, @tdreyno. Is the url just a serialized form of UI state? Plenty of sites preserve everything in the url, even form input. Like the Babel repl.

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

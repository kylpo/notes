_WIP_

[FormidableLabs/freactal: Clean and robust state management for React and React-like libs.](https://github.com/FormidableLabs/freactal)

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

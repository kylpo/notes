_WIP_

Started with a question: "Types of App “state”: `data` (that you usually render), `routes` (url and history), `UI` (controls like open panes). Can anyone think of a missing category in that list?"

data is essentially the models and collections that are rendered in a simple todo app, for example.

What about auth state and feature flags?

“current tab” made me think about renaming `routes` to `browser state`

Great questions, @tdreyno. Is the url just a serialized form of UI state? Plenty of sites preserve everything in the url, even form input. Like the Babel repl.

In that sense, App state is actually UI state. Data is just stuff from the server (and likely cached locally maybe in mobx/redux, but shouldn't be considered app state). Maybe there’s an advantage in treating them separately, not “just in MobX”, or “just in /stores”.

Should `Controls` of an app be denoted with a naming convention? Controls like Modals, Stage Left, Stage Right, etc

url is often the serialized form of app state:
- http://caniuse.com/#search=pointer%20events
- Babel repl

What about scene-specific state?
- nested mobX providers do work, so just add `Provider`s at scene level, then components can `@inject`
  - [Nested Providers? · Issue #114 · mobxjs/mobx-react](https://github.com/mobxjs/mobx-react/issues/114)

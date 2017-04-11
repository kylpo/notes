_WIP_

Might be easier to digest as a Friction Series of posts. That way I won't need to tie everything to eachother, either.

- for the past year, I have obsessed about reducing coding friction.
  - started with React Native
    - forced into flexbox
    - separation of concerns: View vs Touchable*

- define friction
  - some friction is necessary for maintainable code
  - anything that causes pause while coding, whether these are short moments like scrolling down a page to see see the render, or bigger moments that make you say "ugh" every time

- first target "coding without friction", then evolve to "coding with joy", or something like that
  - thought about this from title of https://pavelfatin.com/typing-with-pleasure/
  - [Christoph Pojer on Twitter: "Have never been able to get into such deep focus as now, thanks to these tools: * @flowtype * Prettier * Fish shell * Nuclide * @fbjest"](https://twitter.com/cpojer/status/842531353136525313)

- imports
  - started with webpack's `providePlugin`
  ```js
  // Automatically loaded modules - means these imports are not needed in each file
  new webpack.ProvidePlugin({
    React: 'react',
    Col: 'constelation-Col',
    Button: 'constelation-Button',
    BackgroundImage: 'constelation-BackgroundImage',
    Row: 'constelation-Row',
    Flex: 'constelation-Flex',
    Text: 'constelation-Text',
    View: 'constelation-View',
    Style_: 'constelation-Style_',
    Event_: 'constelation-Event_',
    Animate_: 'constelation-Animate_',
  }),
  ```
    - doesn't work in RN
    - Use `globals.Col = require('constelation-Col')`? Issues using these globals outside of classes. Scoping issues
  - importjs to the rescue
  - note: ts has something like this in the works
    - what landed is just a popup suggestion though, not a full `import all` solution
    - [feature request: Auto import dependencies · Issue #2635 · Microsoft/vscode](https://github.com/Microsoft/vscode/issues/2635)
  - code folding the imports
    - [That feeling when you press page down three times to get past all the imports...](https://twitter.com/BrandonBloom/status/839336948049195009)
  - [JetBrains WebStorm on Twitter: "WebStorm adds import for your React component automatically as you type it. Forgot to import React? Hit Alt-Enter on a warning to fix it. https://t.co/uBFqSQL0C1"](https://twitter.com/WebStormIDE/status/849243315417624576)

- autoformatting
  - [prettier](https://github.com/prettier/prettier) (someday)
    - "Prettier could enable two things:
      1. Lens-- let code match the eye of the beholder
      2. Law-- enforce the format of checked-in code"
      https://twitter.com/shaunlebron/status/820363199665029121
    - [recently started using Prettier across all my projects, no stress over code styles anymore](https://twitter.com/markacola/status/839396401595310080)
  - semicolons used to be a point of friction, so I stopped. Now prettier brings them back, but I don't have to type it

- defensive coding
  - types enable me to not null-check everything

- navigating code
  - why I'm stuck in vim
    - I keep trying more modern editors like vscode and atom, but always fall back to vim for its buffers/splits and vinegar.vim approach to opening and traversing files.

- declarative code as much as possible
  - able to go from a Sketch file to real apps by just "describing" what I'm looking at
  - [Imperative vs Declarative Programming](https://tylermcginnis.com/imperative-vs-declarative-programming/)

- less abstractions, more copy/pasting
  - anti-DRY
    - find that you are repeating code 3+ times before considering creating an abstraction

- two modes: speed and quality
  - friction changes between these modes
  - Speed. not velocity, because it is going fast in multiple directions, often going in reverse. Finally ending in a "right" direction.
  - Quality _after_ direction found and feature built. For cleaning up code, documenting, enabling future maintenance.

- testing
  - relieves friction by showing breaking changes as they happen if you have good coverage
  - adds to friction when testing too early. Speed mode means you'll write whole suites of tests that may no longer apply when changing direction

- "unnecessary" boilerplate
  - a reason I prefer mobx over redux

- colocation
  - why Relay is amazing

- Seeing results immediately
  - HMR
  - Tools to visualize your breakpoints, like [Emmet Re:view - Chrome Web Store](https://chrome.google.com/webstore/detail/emmet-review/epejoicbhllgiimigokgjdoijnpaphdp?hl=en) and [💀🐆 on Twitter: "Working on an electron app that allows you to preview scaled versions of multiple screen sizes simultaneously. Works on local urls too. https://t.co/tewfRuGqjh"](https://twitter.com/mrmrs_/status/833449786640625664)

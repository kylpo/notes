_WIP_

---

**friction** reduces **speed** and therefore **velocity**

friction slows progress

context switching is a form of friction

---

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
  - TS
    - not in tsserver yet. Set for milestone 2.3 currently.
    - https://github.com/Microsoft/TypeScript/issues/7849
    - https://github.com/Microsoft/vscode/issues/2635
    - https://github.com/Microsoft/TypeScript/blob/master/lib/protocol.d.ts#L5
    - https://github.com/Microsoft/TypeScript/wiki/Standalone-Server-(tsserver)
  - importjs to the rescue
  - note: ts has something like this in the works
    - what landed is just a popup suggestion though, not a full `import all` solution
    - [feature request: Auto import dependencies · Issue #2635 · Microsoft/vscode](https://github.com/Microsoft/vscode/issues/2635)
  - code folding the imports
    - [That feeling when you press page down three times to get past all the imports...](https://twitter.com/BrandonBloom/status/839336948049195009)
    - vscode: [folding language-aware folding · Issue #3422 · Microsoft/vscode](https://github.com/Microsoft/vscode/issues/3422)
  - [JetBrains WebStorm on Twitter: "WebStorm adds import for your React component automatically as you type it. Forgot to import React? Hit Alt-Enter on a warning to fix it. https://t.co/uBFqSQL0C1"](https://twitter.com/WebStormIDE/status/849243315417624576)
  - [A Reason to Code](https://dev.to/kayis/a-reason-to-code)
  - [Webstorm: Auto Imports on paste](https://blog.jetbrains.com/webstorm/2017/09/webstorm-2017-3-eap/#import-on-paste)
    - ![](https://d3nmt5vlzunoa1.cloudfront.net/webstorm/files/2017/09/import-on-paste.gif)
  - [Wes Bos 🔥 on Twitter: "🔥 The next version of VS code will automatically add your import statements as you use functions from your project https://t\.co/hk2vwcaoOy"](https://twitter.com/wesbos/status/925056339398848512)

- autoformatting
  - [prettier](https://github.com/prettier/prettier) (someday)
    - "Prettier could enable two things:
      1. Lens-- let code match the eye of the beholder
      2. Law-- enforce the format of checked-in code"
      https://twitter.com/shaunlebron/status/820363199665029121
    - [recently started using Prettier across all my projects, no stress over code styles anymore](https://twitter.com/markacola/status/839396401595310080)
  - semicolons used to be a point of friction, so I stopped. Now prettier brings them back, but I don't have to type it
  - [Ben Teese on Twitter: "Using Prettier to format JS is like killing an unnecessary background process in your brain. It frees up cycles to think about other things."](https://twitter.com/benteese/status/849079655592325121)
  - [Ben Frain on Twitter: "New post ⭐️: “Use linters for errors, formatters to fix style” https://t.co/6vg3OIvSoF"](https://twitter.com/benfrain/status/862309847072743426)
  - [support eslint --fix · Issue #51 · sbdchd/neoformat](https://github.com/sbdchd/neoformat/issues/51)
  - [How to become a more productive React Developer – Jakob Lind](http://blog.jakoblind.no/2017/06/15/how-to-become-a-more-productive-react-developer/?utm_campaign=React%2BNewsletter&utm_medium=email&utm_source=React_Newsletter_75)
  - [Guillermo Rauch on Twitter: "As far as I'm concerned, prettier could style my code like this and I'd still use it. It saves us so much time! https://t.co/jjvMNoohh2 https://t.co/pR5FyAiFJl"](https://twitter.com/rauchg/status/876888344621338624)
  - [Nicholas C. Zakas on Twitter: "Ok, this needs to be said: Prettier is not a replacement for ESLint. Prettier is a source code formatter. ESLint is a code quality tool."](https://twitter.com/slicknet/status/877194938508656641)

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
  - "Code is read many more times than it is written. Writing code costs something, but over time the cost of reading is often higher. Anyone who ever looks at a piece of code has to invest brain-power into figuring out what it does."
    [The Half-Life of Code — Sandi Metz](https://www.sandimetz.com/blog/2017/6/1/the-half-life-of-code)

- Seeing results immediately
  - HMR
  - Tools to visualize your breakpoints, like [Emmet Re:view - Chrome Web Store](https://chrome.google.com/webstore/detail/emmet-review/epejoicbhllgiimigokgjdoijnpaphdp?hl=en) and [💀🐆 on Twitter: "Working on an electron app that allows you to preview scaled versions of multiple screen sizes simultaneously. Works on local urls too. https://t.co/tewfRuGqjh"](https://twitter.com/mrmrs_/status/833449786640625664)
    - http://sizzy.co/ and https://github.com/kitze/sizzy

- Not naming things until it is absolutely necessary
  - BEM, for sure is friction. Just look at the code at https://css-tricks.com/build-custom-serverless-cms-part-2/

- Function should do one thing
  - [ryanmcdermott/clean-code-javascript: Clean Code concepts adapted for JavaScript](https://github.com/ryanmcdermott/clean-code-javascript#functions-should-do-one-thing) does a good job of explaining this
  - 2 or fewer function arguments

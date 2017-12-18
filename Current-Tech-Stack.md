Code style

"Good line of sight" functions. Happy path on left side (means return early) and avoid else returns. [Line of sight in code – Mat Ryer – Medium](https://medium.com/@matryer/line-of-sight-in-code-186dd7cdea88)

---

CSS Style

[David K\. 🎹 on Twitter: "IMO this is the best way to use the style attribute\. And it works in React for all your dynamic styling needs\! 🎨💯 https://t\.co/sxm9eB3SuR"](https://twitter.com/DavidKPiano/status/938387555032227841)

---

Yarn, not npm

Prettier on save

Linaria for static css-in-js
- [How is Linaria different from Emotion – Callstack Engineers](https://blog.callstack.io/how-is-linaria-different-from-emotion-42e420a3984f)
- Use the webpack loader: https://github.com/callstack/linaria/pull/186/files

Testing
- jest
- [Jest In Case \- @thejameskyle](http://thejameskyle.com/jest-in-case.html)

Data Fetching
- Relay
- or consider [wiretie: A Higher Order Component for Preact that resolves (async) values from a model and passes them down as props.](https://github.com/synacor/wiretie)
  - [Jason Miller 🦊⚛ on Twitter: "📣 Introducing Wiretie ⚡️ A 1.3kb solution for working with async data in Preact. https://t.co/qPDvv6RArb https://t.co/QNgEMTVhOH"](https://twitter.com/_developit/status/872230700610715648)
- What about Firebase?

Smitty (for small state solution)
- https://github.com/tkh44/smitty
- and connect it to router http://codepen.io/seveves/pen/ryyNYz

or maybe Redux Zero? [Introducing Redux Zero – Matheus Lima – Medium](https://medium.com/@matheusml/introducing-redux-zero-bea42214c7ee)

or [developit/unistore: 🌶 650b state container with component actions for Preact & React](https://github.com/developit/unistore)

Look in to [luisvinicius167/dutier: A small (1kb) and simple state management solution for Javascript applications.](https://github.com/luisvinicius167/dutier?utm_source=mobilewebweekly&utm_medium=email)

Tools that create components
- [joshwcomeau/new\-component: ⚛ ⚡ CLI utility for quickly creating new React components\. ⚡ ⚛](https://github.com/joshwcomeau/new-component?utm_source=reactnl&utm_medium=email)
- [diegohaz/generact: Tool for generating React components by replicating your own components](https://github.com/diegohaz/generact)
  - ![](https://user-images.githubusercontent.com/3068563/27687316-bb5bd832-5cac-11e7-9761-c489e5a3a9f0.gif)
- [CVarisco/create\-component\-app: Tool to generate different types of React components from the terminal\.](https://github.com/CVarisco/create-component-app)
  - ![](https://user-images.githubusercontent.com/7335613/27760854-9ff86b54-5e51-11e7-8ad0-3289d9b3ebc3.gif)

Preact
- [developit/preact-cli: 😺 Your next Preact PWA starts in 30 seconds.](https://github.com/developit/preact-cli)

Small bundles, all the way down
- [Eric Clemmons on Twitter: "Been optimizing scripts like crazy. Guess which library we’re removing next? (Sucks, s-c may be the only one that supports runtime values) https://t.co/R5y5W6h5K9"](https://twitter.com/ericclemmons/status/860592297666334723)
- [Eric Clemmons on Twitter: "We’ve just crossed our “performance budget” threshold to warrant spending more effort on the server-side than bundle optimization. https://t.co/w0z4CZh67G"](https://twitter.com/ericclemmons/status/860607860241313792)

css-in-js
- [Sebastien Lorber on Twitter: "@kentcdodds @thejameskyle can't we use glamor without naming anything? like <div {...css({border: "solid"})/> ? cc @threepointone"](https://twitter.com/sebastienlorber/status/864124126763646978)
- [Christopher Biscardi on Twitter: "@thejameskyle @threepointone @sebastienlorber @kentcdodds I believe that's why babel-plugin-glamor exists, which hoists: https://t.co/QdPafezE2S"](https://twitter.com/chrisbiscardi/status/864125734675075072)
- Glam and Emotion
  - ["emotion - ~2kb including glam - styled components api - css prop on all elements - css files gen during build https://t.co/AzyfJVjwCx https://t.co/o2WO6PsUxS"](https://twitter.com/tkh44/status/870516183325327364)
  - [Kye Hohenberger on Twitter: "Another great feature, the css prop can be used on any element. emotion takes care of attaching the className for you. https://t.co/yZ4W0snRx0"](https://twitter.com/tkh44/status/873731354575372288)
  - ![](https://pbs.twimg.com/media/DCAdkGAUIAE-LO2.jpg)

NOT Node
- [Aditya Mukerjee on Twitter: "Ryan Dahl, creator of @nodejs, talking about Go and Node\. \#golang \#js https://t\.co/G8RE0q56ru"](https://twitter.com/chimeracoder/status/903444020218736645)

Fast
- [Luke Edwards on Twitter: "Tiny (124B) replacement for `Array.proto.map` It's 30X faster than native & can modify proto if feeling rebellious 😎 https://t.co/FoaO63R4l9"](https://twitter.com/lukeed05/status/882797698608357376)


---

# Figure out my perfect coding workflow
custom prettier
custom babel transforms
code folding

reasonml?
etc

flow linter: https://twitter.com/flowtype/status/893538968993542144

https://twitter.com/holtbt/status/893932312269791232
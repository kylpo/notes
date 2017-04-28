_WIP_

Consider showing these docs with https://github.com/egoist/anydoc

evolution of constelation. Web div > RN > inline style > nice PR review experience > perf issues >

See Sketch file, know exactly how to break it down to code.

Dream would be to have a wysiwyg editor for scaffolding/setup. Like CRA for starting project, then "eject" to code for more complicated tasks. Works well if wysiwyg builds on constelation primitives and elements.

scene/stage/etc

Think about wysiwyg parts

Tools that help you stay in your specific context (hacking, designing, etc). eslint errors, prettierjs, inline labels to expensive operations, div depth warnings, security violations (https://github.com/nodesecurity/eslint-plugin-security)

But where does this all end? Do I need to build my own text editor!? I certainly shouldn't...

What's next? Now that I've gone to the far end of DX, I need to swing back around to the UX. Perf, perf, perf. Where must UX (perf) trump DX?


Do read through [CSS in JS: The Argument Refined – Medium](https://medium.com/@steida/css-in-js-the-argument-refined-471c7eb83955#.dwrvgfn6d), as he has gone down a similar journey.

Writing style
- Structure similar to [junctions.js](https://junctions.js.org/?utm_campaign=Fullstack%2BReact&utm_medium=email&utm_source=Fullstack_React_49) with starting "Why use Constelation?"
  - Extreme separation of concerns
  - Powerful base primitives
  - Copy-pastability
  - Skimability
- Motivations similar to [Motivation - junctions.js](https://junctions.js.org/guide/introduction/motivation)
- [How do you write such amazing documentations? · Issue #21 · staltz/ama](https://github.com/staltz/ama/issues/21)
- [Kent C. Dodds on Twitter: "This is a great example of where glamorous really helps https://t.co/MKUE1CTP3p 👋 goodbye indirection, hello explicit sharing of components! https://t.co/s6gwoG9Gnj"](https://twitter.com/kentcdodds/status/857616944039682048)
  - even better with Constelation with style as props. There is no inderection at all.

Mindset of cranking widgets enables creativity. Don't need to "solve" trivial problems over and over.
- Inspired by [GTD Newsletter: How to make your job easier](http://us8.campaign-archive2.com/?u=4fdf2cadb358acc7c1c1ca8bd&id=a0680a8e72&e=3d3d97c32e)

Think of components in a GUI tool
- Elements/Primitives on left to grab are View, Text, Image, ...
- Property editing on right:
  - Style_, Animate_, Event_ would be tabs
  - props would be editable fields in tabs

Would love for this to one day fold in to a WYSIWYG editor. It'd use all of constelation-primitive, so it is really easy for devs to drop down into code. Use the prototype tool for quick layouts and explorations, then code for the polish.
- [Andy Matuschak on Twitter: "New prototyping app! It has a combo I’ve missed since leaving Apple: design via UI; easy to add code when needed. https://t.co/8UCTYkPTRn"](https://twitter.com/andy_matuschak/status/839311949363978240)
  - [Kite Compositor](https://kiteapp.co/)
  - ![](https://kiteapp.co/assets/HeroImage0.png)
- Start with a flow like [Karri Saarinen on Twitter: "What is it like to compose a Airbnb listing page in Sketch in ~1min by using our design system (DLS) https://t.co/xsadtU8gkP"](https://twitter.com/karrisaarinen/status/849733176150773761). Then open up editor and continue it.
- [reactide/reactide: Reactide is the first dedicated IDE for React web application development. http://reactide.io](https://github.com/reactide/reactide)
![](https://camo.githubusercontent.com/ee9fc228ccb85a549f3b80b939cea810a20b0770/687474703a2f2f72656163746964652e696f2e73332d776562736974652d75732d776573742d312e616d617a6f6e6177732e636f6d2f696d616765732f72656163746964652d73637265656e73686f74322e706e67)

Flexbox everywhere
- [Nicolas on Twitter: "One of Safari's worst bugs (flexbox performance) now fixed in WebKit. A small step forward for web apps on iPhone https://t.co/lfeUgZllfi"](https://twitter.com/necolas/status/843527768356806656)

Others working on this
- [Leland Richardson on Twitter: "@mjackson i'm interested in working on getting react-primitives or react-native-web in use at airbnb, but nothing in production at the momen"](https://twitter.com/intelligibabble/status/844983578056257536)
- [@jongold stories on Twitter: "created a lil app with `react-primitives`; rendering real data + maps from the Foursquare API to Sketch + Browser at the same time https://t.co/0VXpK5WWU7"](https://twitter.com/jongold/status/848331554317316096)
- [ReactXP](https://microsoft.github.io/reactxp/docs/getting-started.html)
- [Dan Abramov on Twitter: ".@reactiflux @acdlite “Does Fiber change anything for styling?” https://t.co/S5B7OyqbWO"](https://twitter.com/dan_abramov/status/852507690840592384)
  - looking in to components for Layout
- [idibidiart/react-native-responsive-grid: Responsive Grid Layout for React Native](https://github.com/idibidiart/react-native-responsive-grid)

No More "alphabetize vs logical" css ordering arguments
- [Alphabetize your CSS properties, for crying out loud](https://medium.com/@jerrylowm/alphabetize-your-css-properties-for-crying-out-loud-780eb1852153)
- [Organize your CSS properties however you dang like – Michael.blog](http://michael.blog/2017/03/30/organize-your-css-properties-however-you-dang-like/)
- [The Different Logical Ways to Group CSS Properties - The Media Temple Blog](http://mediatemple.net/blog/tips/different-logical-ways-group-css-properties/)

Lazy - less naming
- no naming css class, just inline
- [Mark Dalgleish on Twitter: "👶: Remember when we didn't prefix classes? 🤓: Remember when we had to manually prefix classes? 💅: Remember classes?"](https://twitter.com/markdalgleish/status/851381503078522881)

I tried to think of everything you'd need in a WYSIWYG to build an app/site today. These are the declarative components I focussed on.
- Layout
- Style
- Interaction
- Animation
- Layers (z-index)
- Timeline

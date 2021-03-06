_WIP_

# Explaining Constelation
Start with perfect web code: html with classnames of semantic elements with external css (could have inlined critical
css, too). Now identify the pain points for the developer. Copy/paste re-use of styles, elements, interactivity, etc. 

```jsx
<div class="container">
  <header>HEADER</header>
    <aside>MENU</aside>
      <main>CONTENT</main>
        <footer>FOOTER</footer>
        </div>
        
        Now move external  css next to components, not just 1 css file. Easier to find what to edit, but still
        complicated when using util classes and shared styles.
        
        Now move to css-in-js to define styles in the file. OK, doesn't help all that much. Shared styles are imported.
        Clearer what style dependencies you have.
        
        Still need to name things, that sucks. Still need to copy/paste multiple things, that sucks.
        
        Constelation: no naming, easy copy/paste, no jumping to look up what an element really is. Clear separation of
        concerns.</footer></main></aside></header>
</div>
```

# Developing at prototype speed

# Future: Developing at speed of imagination (and beyond)
Imagination is like l2 cache for a cpu. You can "build" things and change them really quickly. Sketch could be thought
of as RAM. Prototypes thought of as SSD. Products thought of as Hard Disk. Each thing further and further away from
imagination takes more and more time to change.

The goal is to get building apps/sites as close to imagination speed as possible. Machine learning could take us beyond
imagination by essentially bringing in others' imaginations.

# Constelation API
https://github.com/constelation/monorepo/issues/73

https://blog.buildo.io/flexview-the-easiest-way-to-use-flex-with-react-c698db55926a

https://github.com/mitchellhamilton/grid-emotion

https://github.com/jxnblk/styled-system#configuration

https://github.com/morajabi/styled-media-query

just like the old days of `<table>`, we should have a `<flex>`, and `<grid>`

---

When in developer-mode, what piece of information here, matters?

`<div className='...' />`

Certainly isn't the div. This distinction isn't really useful to the dev unless in accessibility-mode:

`<nav className='...' />`

The className is what matters. More specifically, the layout within that classname is what matters.

Sometimes the style also matters. THis is why we separate the two.

---

[Kye Hohenberger on Twitter: "The future of css\-in\-js is going to look something like styled\-system with its responsive values\. Source for Box 👇 https://t\.co/MuxsdZayDF https://t\.co/fK35Phv5Jt"](https://twitter.com/tkh44/status/905474043729416192)

![](https://pbs.twimg.com/media/DJDibtVUMAQOl-a.jpg)

[Kye Hohenberger on Twitter: "@rofrischmann @mxstbr @oleg008 @\_philpl @glenmaddern @rtsao @markdalgleish @threepointone @kentcdodds The best part is the new patterns that are emerging for styling\. My favorite is styled\-system by @jxnblk\. The responsive styles are 🔥 https://t\.co/r2whBmFjKj"](https://twitter.com/tkh44/status/902933964670697472)

![](https://pbs.twimg.com/media/DIfcF5GXoAA6M64.jpg)

# Problems with an abstraction like View
- Not able to benefit from something like [eslint-plugin-jsx-a11y/CHANGELOG.md at master · evcohen/eslint-plugin-jsx-a11y](https://github.com/evcohen/eslint-plugin-jsx-a11y/blob/master/CHANGELOG.md)
- Not able to benefit from some of the babel hoisting and such

---

Almost like React opened the flood gates for DX. We can have a good DX and not sacrifice performance!? React Native opened it even more with its default View styles and Animated. We took it to the extremes, like reduxing all the things, Radium for styling, etc. Now we are popping our heads up and analyzing what is realistic. Preact's creator is helping us strip down our bundle sizes and get back to putting UX first.

Consider showing these docs with https://github.com/egoist/anydoc

Position the reveal as a prototyping framework, focussed on speed and DX.

# History
evolution of constelation. Web div > RN > inline style > nice PR review experience > perf issues >

See Sketch file, know exactly how to break it down to code.

Dream would be to have a wysiwyg editor for scaffolding/setup. Like CRA for starting project, then "eject" to code for more complicated tasks. Works well if wysiwyg builds on constelation primitives and elements.
- [Mark Dalgleish on Twitter: "Prediction: WYSIWYG got a bad name in the document era, but we'll see it come back in the component era where it makes way more sense."](https://twitter.com/markdalgleish/status/867950728626585600)

Big update that brings design closer to code. Draw & create layouts in Framer, then switch to code to add interaction.

Design with GUI, then drop in to code, like: [Framer on Twitter: "Meet Framer Design. Draw & create layouts in Framer, then switch to Code to add interaction. A complete workflow at https://t.co/0QuedjsrmR https://t.co/pds5PawUsv"](https://twitter.com/framer/status/869933736313278464)

scene/stage/etc

Think about wysiwyg parts

Tools that help you stay in your specific context (hacking, designing, etc). eslint errors, prettierjs, inline labels to expensive operations, div depth warnings, security violations (https://github.com/nodesecurity/eslint-plugin-security)

But where does this all end? Do I need to build my own text editor!? I certainly shouldn't...

What's next? Now that I've gone to the far end of DX, I need to swing back around to the UX. Perf, perf, perf. Where must UX (perf) trump DX?

---

iteratively solve problems

start with positioning elements and how they are just so many options. Consolidate to RN's flexbox defaults with a style object.

ugh, annoying for copy/pasting and truly learning what the view is for, so inline the style as an inline object.

ugh, now we re-create objects on every re-render and mess with garbage collector. Move to Style object.

ugh, what should Style object be in charge of? Well, Views are affecting the layout, so lets have Style be the catchall for non-layout styles.

Cool, lets add interactivity. I'll just add onClick to my View... Wait a minute, we just said that View only cares about layout, so lets make a new component that only cares about interactivity.

---

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
  - [Leland Richardson on Twitter: "@jlongster long story short, i put everything into two categories:"](https://twitter.com/intelligibabble/status/864183238222168064)
- [@jongold stories on Twitter: "created a lil app with `react-primitives`; rendering real data + maps from the Foursquare API to Sketch + Browser at the same time https://t.co/0VXpK5WWU7"](https://twitter.com/jongold/status/848331554317316096)
- [ReactXP](https://microsoft.github.io/reactxp/docs/getting-started.html)
- [Dan Abramov on Twitter: ".@reactiflux @acdlite “Does Fiber change anything for styling?” https://t.co/S5B7OyqbWO"](https://twitter.com/dan_abramov/status/852507690840592384)
  - looking in to components for Layout
- [idibidiart/react-native-responsive-grid: Responsive Grid Layout for React Native](https://github.com/idibidiart/react-native-responsive-grid)
- [Rethinking Style - Google Slides](https://docs.google.com/presentation/d/1s7VPbvuv6m9-S7ePm0R5loqRnHsZEHHVbZALJpWAARo/edit#slide=id.g1f5f3b47d0_0_684)
  - [mdgriffith/style-elements: Create styles that don't mysteriously break!](https://github.com/mdgriffith/style-elements)
- [Travis Arnold on Twitter: "🍰 once you have strong primitives https://t.co/RuXap4maur"](https://twitter.com/souporserious/status/876578753769488385)
- [Kent C. Dodds on Twitter: "@rauchg And the built-in components so you don't have to give things names like "Container" or "Wrapper" but just inline it. <Div margin={20} />"](https://twitter.com/kentcdodds/status/875824332735483905)
- [Robin Frischmann on Twitter: "@kentcdodds @glenmaddern @markdalgleish @threepointone @mxstbr @oleg008 @\_philpl @rtsao @jongold In general we always have primitives \(View, Text, \.\.\.\) which are used to create styleguide components \(Heading1\-6, Button, \.\.\.\)"](https://twitter.com/rofrischmann/status/896234973384118273)

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
  - See Revealer doc
  - like [jondot/react-flight: The best way to build animation compositions for React.](https://github.com/jondot/react-flight)?
  - [madou/yubaba: ✨ Orchestrated page transitions made easy](https://github.com/madou/yubaba)
  - [react\-inview\-monitor Example](https://snipsco.github.io/react-inview-monitor/) - interesting idea to just apply the className, like `ReactCSSTransitionGroup`.
```jsx
return (
  <InViewMonitor
    intoViewRatioShownThreshold={0}
    classNameInitial='tabs'
    classNameScrolledPastView='tabs tabs--fixed'
  >
    <TabsHere />
  </InViewMonitor>
)
```

# Still semantic
- `tag` prop
- Just like ios's accessibilityTraits. It is only for accessibility today, not really for a "semantic web". See https://facebook.github.io/react-native/docs/view.html#accessibilitytraits

# DX
We have focused entirely on DX. Along the way, found some surprising wins.

DX means:
- scannable
- easy to copy/paste or abstract
- lazy (don't think about things like naming, use conventions/rules)
- code reviews easier. Adding a style prop is easier than adding to style object and figuring out which div it goes to
- decisions already made. Being bored leads to creativity.
-- imagine if you had to read all talents in HOTS before picking one. You would need to context switch out of the action. Even better is to have a build made ahead of time and just alt-# it as soon as it becomes available. Even better is knowing when to break the build and choose something else given a different event.

Surprising wins:
- base absraction shielded us from css-in-js churn


[The Half-Life of Code — Sandi Metz](https://www.sandimetz.com/blog/2017/6/1/the-half-life-of-code)
> "Code is read many more times than it is written. Writing code costs something, but over time the cost of reading is often higher. Anyone who ever looks at a piece of code has to invest brain-power into figuring out what it does."


# The case for Row
Row tells the developer to go against the usual skim flow and read left to right, not top-down.

<View horizontal > works OK for the top tag, but fails with the bottom tag </View>

Similarly, a Flex was nice to tell the developer that they need to look at the logic to figure out how it should be read.

# Random notes
Address pain points, focus on DX. Strive for no friction.

Programming is a craft, like writing is a craft. Ther is good writing style, and bad writiing style.

RN Event_ wraps with TouchableWithoutFeedback. This means the _ convention doesn't necessarily mean it adss nothing to the DOM. Instead, it is just incomplete without a child. A child is required, and _ will enhance it.

Why not Box?
- boxes have borders
- also, ScrollBox doesn't make sense

ScrollRow
ScrollCol
ScrollFlex
ScrollView
- doesn't actually care about align/justify. It is just the view containing some other viw that might care.

Within Conventions
- structure
- rules
- style

# Single Responsibility Components
consider the Category component. It could just be a single div with a background-image, onClick, onHover, and a child text, but that is complicated and completely not reusable.

A better way to think of it would be Text wrapped in Col wrapped in BackgroundImage wrapped in Clickable. The only weirdness is the onHover, which would need to be done at the BackgroundImage level for the insetShadow.

---

range of component concerns (completely isolated, app-aware, route-aware)

saying we can have all modular components is like saying the best security is turning off your computer and burying it 100 feet deep. They're just impractical.

---

Layout components' attribute are basically all the things that wouldn't change with themes.

# Two approaches to separating concerns
Two approaches I can take with separating concerns. Either complete seperation, or some separation.

Lets build a green box that does something on click.

Complete Separation:
Put down a drop of green paint. Now, expand that paint to desired size by putting a box in it. Now, wrap that whole
thing with an interact to make it interactive.

Or you could think of things as always filling space, and flex just being a container to stop it at certain points.

Some Separation:
Place a box down with desired size. All elements in dom have styles, and all elements in dom have interactability, so
add you style and event objects to this box.

Something I really liked when learning and using React Native was the lack of a button component. Instead, you had a
Touchable wrapping a Text component. Want a border and padding? Add it to the touchable. Same goes for a link: it is .a
Touchable wrapping a Text component without a border, and without padding. Simple.

# In prep for conf talk
Building quickly for web and native gives me rare insights. Something I should leverage.

Prototyping fast and loving it. Describe with jsx what I'm seeing from design. Declarative ftw. Constelation constraints enable me to do it without jumping around code.

Constelation coding reduces friction. Less activation energy, get to be lazy and think less. Means I enjoy coding more.

Prototyping is about moving as fast as possible. This means having a set of powerful primitives, and fewer abstractions. DRY is mostly avoided.

<Style_> allows for easier copy/pasting.

Constelation components allow me to dev a design from top to bottom, like describing one complete thought. Afterward, I can play the role of an editor and break it up into subcomponents or reusable shared components.


Non-Constelation way would have me assigning classnames or style objects to divs and jumping back/forth to css file or bottom of page to edit style object. OR, you'd fill in all divs of design first, then have to run back through it, adding style and such. Not nearly as seamless as the writing style of Constelation.

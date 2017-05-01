_WIP_

# Cons
- [Alex Russell on Twitter: "PSA: embedding/applying CSS in JS is the surefire way to be on every slow path. Bloats memory, slows parsing & use, hurts caching. Avoid."](https://twitter.com/slightlylate/status/845435543647248384)
- [Mark Dalgleish on Twitter: "Exactly why I still use CSS Modules, despite all the great work with CSS-in-JS. https://t.co/aOVXecnLi0"](https://twitter.com/markdalgleish/status/851210247880323072)
- [Sunil Pai on Twitter: "If you spot a site that's slow *because* of css-in-js, lemme know. //@slightlylate"](https://twitter.com/threepointone/status/851289628195737600)
  - Alex Russell on the issues
    - [Sunil Pai on Twitter: "action items for css-in-js lib authors/consumers- - prerender/ssr - aggressively code split - measure everything - thank @slightlylate https://t.co/n6gYaipQAr"](https://twitter.com/threepointone/status/851460590333820928)
      - ![](https://pbs.twimg.com/media/C9D-4dOXcAEz49p.jpg:large)
    - [Alex Russell on Twitter: "@threepointone @kentcdodds First, you double memory cost. The string is parsed in JS, interned in the V8/DOM shared string area, then *parsed again* when applied"](https://twitter.com/slightlylate/status/851446700728135680)
    - [Alex Russell on Twitter: "@arkanciscan @markdalgleish The bytes you embed as strings in your JS but use as CSS are double the cost (at least) in memory, parse, and runtime."](https://twitter.com/slightlylate/status/851215870441406464)
- [Sunil Pai on Twitter: "I’m also going to investigate exterminating css() objects from bundles altogether, replacing with just classnames. excelsior!"](https://twitter.com/threepointone/status/851460820018057216)
- [Kyle Poole on Twitter: "Think I'll start explaining this as "double taxation" https://t.co/Ydtn0baUVL"](https://twitter.com/kylpo/status/851449345299718145)


# Inline styles
- [inline styles are worse on updates](https://twitter.com/intelligibabble/status/850808821865889792)

# Atomic CSS
- comments of [Let’s Define Exactly What Atomic CSS is | CSS-Tricks](https://css-tricks.com/lets-define-exactly-atomic-css/)
  - "Correct. You’ll find no semantic class names here (unless you’ve setup some helper classes)." Helper classes would just be React components.
- [How is tachyons different from inline styles? · Issue #12 · tachyons-css/tachyons](https://github.com/tachyons-css/tachyons/issues/12#issuecomment-59828967)

# Static styles
- static vs. dynamic styles. How best to denote each?
- Love `gloss`'s idea thinking about `style` defined as a `static`. See [example](https://github.com/motion/gloss#examples):
```jsx
import gloss from 'gloss'

const style = gloss()

@style class extends Component {
  render() {
    return <h1 $black $bg="#fff">Test</h1>
  }

  static style = {
    h1: {
      fontSize: 22,
      color: [255, 255, 255],
      '&:hover': { color: 'red', },
      borderBottom: [2, 'solid yellow']
    },
    black: {
      color: 'black',
    },
    bg: color => ({
      background: color,
      borderBottom: [2, 'solid', color]
    })
  }
}
```

# Babel transforms to help
- [spredfast/babel-plugin-transform-hoist-jsx-style: Hoist pure objects passed to 'style' prop](https://github.com/spredfast/babel-plugin-transform-hoist-jsx-style)
- [styled-components/babel-plugin-polished: Compile polished helper functions at build time](https://github.com/styled-components/babel-plugin-polished)
- [soluml/pre-style: Pre-Style is a tool that lets you author CSS-in-JS (or CSS-in-Markup) while outputting highly efficient CSS.](https://github.com/soluml/pre-style)

# Proposed solution
- This is a tooling problem. Perf and UX must be the top priority. DX can be done with better tooling.
- see VS Code's [Atomizer](https://marketplace.visualstudio.com/items?itemName=pankaj-parashar.atomizer) and [css peak](https://marketplace.visualstudio.com/items?itemName=pranaygp.vscode-css-peek)
  - ![](http://res.cloudinary.com/dw9fem4ki/image/upload/c_mfit,q_100,w_1000/v1459669769/installation_iscrel.gif)
  - ![](https://github.com/pranaygp/vscode-css-peek/raw/master/images/working.gif)
- inline css peek?
  - write component with `cssStyle=` prop, which auto-generates css className and the external stylesheet

[Mark Dalgleish on Twitter: "In case you're wondering—I really love Styled Components, Glamorous, JSS, Styletron, etc. but I still ship CSS Modules to production 👌"](https://twitter.com/markdalgleish/status/856794232421470208)

[Mark Dalgleish on Twitter: "@_zouhir I've experimented with CSS-in-JS, and I've particularly enjoyed Styled Components, but I'm trying not to ship a runtime if I can avoid it"](https://twitter.com/markdalgleish/status/856805714508914688)


"dynamic bits with css vars -> awesome"

[Guillermo Rauch on Twitter: "@threepointone yep but very very interesting approach. Makes for a small codebase and you solve the perf problem telling the browser about dynamic parts"](https://twitter.com/rauchg/status/857135883346202625)


# vs functional css
https://github.com/necolas/react-native-web/blob/master/performance/README.md

https://twitter.com/necolas/status/847844187131101184

Atomic CSS with atomizer

https://acss.io/

https://github.com/acss-io/atomizer

My CSS in JS gdoc

https://marketplace.visualstudio.com/items?itemName=pankaj-parashar.atomizer

https://marketplace.visualstudio.com/items?itemName=pranaygp.vscode-css-peek

https://acss.io/

http://tachyons.io/docs/layout/spacing/

http://jxnblk.com/gravitons/

http://basscss.com/

https://github.com/basscss/ace

https://github.com/basscss/basscss/issues/165

http://notebook.hongkonggong.com/2016/04/21/is-tachyons-the-right-css-framework-for-me/

https://github.com/martinandert/babel-plugin-css-in-js

https://www.npmjs.com/package/babel-plugin-oxygen-css

https://www.smashingmagazine.com/2016/04/finally-css-javascript-meet-cssx/

https://www.sitepoint.com/atomic-oobemitscss/

babel plugin to avoid perf impact of css-in-js https://twitter.com/mxstbr/status/846826184956661760

https://github.com/zeit/styled-jsx

https://twitter.com/markdalgleish/status/846884862816530435

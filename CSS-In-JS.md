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

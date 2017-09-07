_WIP_

Should it be re-titled as Compile-vs-Run-Time?

---

[Compilers are the New Frameworks \- tomdale\.net](https://tomdale.net/2017/09/compilers-are-the-new-frameworks/?utm_source=ponyfoo+weekly&utm_medium=email&utm_campaign=79)

---

[Kristofer Baxter on Twitter: "@cpojer Build time optimizations. So much left to explore here."](https://twitter.com/kristoferbaxter/status/892189558971838464)

---
from [babel-handbook/plugin-handbook.md at master · thejameskyle/babel-handbook](https://github.com/thejameskyle/babel-handbook/blob/master/translations/en/plugin-handbook.md#toc-pre-and-post-in-plugins)

Babel is a generic multi-purpose compiler for JavaScript. More than that it is a collection of modules that can be used for many different forms of static analysis.

> Static analysis is the process of analyzing code without executing it. (Analysis of code while executing it is known as dynamic analysis). The purpose of static analysis varies greatly. It can be used for linting, compiling, code highlighting, code transformation, optimization, minification, and much more.

---

# Templates (vs jsx components)
- [Jason Miller 🦊⚛ on Twitter: "who likes templates"](https://twitter.com/_developit/status/890729645750046721)
  - [Ben Lesh 🛋️👑🔥 on Twitter: "@_developit I do. Contextually. I like static analysis and build-time optimizations."](https://twitter.com/BenLesh/status/890781512580202496)
  - ^ ftw
- [Kye Hohenberger on Twitter: "@TheLarkInn @\_developit @ken\_wheeler @samccone @vuejs All of https://t\.co/AzyfJVjwCx is built on this premise\. We are able to do some neat things because you can't touch tagged tmpl at runtime"](https://twitter.com/tkh44/status/899493636240416768)
- [Jason Miller 🦊⚛ on Twitter: "@preactjs @TheLarkInn @lukeed05 @rob\_dodson That is to say \- they are memoized and chunked by default\. It's done via static analysis of the view so no effort required\."](https://twitter.com/_developit/status/898965893266292736)
- [Jason Miller 🦊⚛ on Twitter: "Is this JSX, or an HTML template? \.\.\.\. or both? 🙃 https://t\.co/4ZijKTKpOg"](https://twitter.com/_developit/status/898967071274422272)

# Dynamic vs Static styles
- really interesting thing going on with css-in-js solutions. We love their APIs, but are finding that shipping a css runtime that evaluates JS strings/objects is essentially double taxation (double parse, to be exact) for the user. This was not a problem with traditional css, where all styles are statically defined. The dynamism was done by changing classes, and reaching to js to set styles for anything truly dynamic and measured/discovered at runtime.

# React Native's Animated
- Interpolations defined once, then sent to native over bridge. When it runs, it can remain in Native, and not need to send increments back and forth over wire to JS.
- Not exactly static, but similar idea of computing work up front, not at runtime

# Relay
- Relay has found that an AOT (Ahead of Time) step to use its graphql queries has been a huge gain in perf.
- [Building Relay Modern · wincent.com](https://wincent.com/blog/relay-modern)

# Frameworks
- Svelte is attempting to compile away itself. I need to learn more about the benefits to this.

# CSS
- what's old is new again. Declare styles ahead of time, apply at runtime via `class`, not using css-in-js.
- or use css-in-js with babel transform
- [Robin Frischmann on Twitter: "Currently working on babel\-plugin\-fela\. Fela will get even faster \(up to 50% 😱\) Prerendering static styles during compile\-time = 🚀 \#cssinjs https://t\.co/xaIzuhbr2C"](https://twitter.com/rofrischmann/status/895918362299125760)
- [Paweł Trysła on Twitter: "Sneak peek of what I'm working on with @satya164 and @thymikee\. Full compile\-time css evaluation and extraction with @babeljs plugin\. https://t\.co/O2LGvcI8br"](https://twitter.com/_zamotany/status/901408316169048064)

# CDN
- is essentially a way of serving static files

# Static Sites
- what's old is new again

# Testing
- Static Analysis via eslint, flow, ts
  - https://youtu.be/tRNL-WAPb98?t=7m21s

[La nouvelle vague - Sunil Pai aka @threepointone at @ReactEurope](https://www.youtube.com/watch?v=yjVhjmM1FPc)

[Kent C. Dodds on Twitter: "I want to see more libraries disguised as babel plugins. Put more at compile-time and less at runtime FTW!"](https://twitter.com/kentcdodds/status/881211867057737728)

[kentcdodds/babel-plugin-preval: Pre-evaluate code at build-time](https://github.com/kentcdodds/babel-plugin-preval)

Prepack, like Svelte, compiles away

css-in-js needs static queries and ahead-of-time optimization, too. Just like the recent Relay release.

https://code.facebook.com/posts/1362748677097871/relay-modern-simpler-faster-more-extensible/

Litho removes containers to reduce memory consumption using  ahead-of-time optimization. See https://developers.facebook.com/videos/f8-2017/litho-a-declarative-framework-for-efficient-uis/ at around the 30:00 mark. "View Flattening"

React Web would also benefit from View Flattening.


## Inline text strings DX

Inline text strings are like the css problem for UX vs DX. We need a tool to extract them, because inline is better DX. Does the runtime already do this?


[Code is Fashion – Eric Florenzano – Medium](https://medium.com/@ericflo/code-is-fashion-3d5583e8a6f8)

[Statuscode on Twitter: "Gixy is a static analyzer for your @nginx config files: https://t.co/jVkazOdriv .. detects flaws, potential security tweaks, etc."](https://twitter.com/statuscode/status/862680882276118529)

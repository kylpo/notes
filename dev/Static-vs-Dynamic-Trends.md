_WIP_

Should it be re-titled as Compile-vs-Run-Time?

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

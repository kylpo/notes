_WIP_

# Micro-Perf
## Explicit comparisons
```js
if (obj !== undefined) { return obj.x; }
```
15% faster than
```js
if (obj) { return obj.x; }
```
### Ref
- [TurboFan: A new code generation architecture for V8 - Google Slides](https://docs.google.com/presentation/d/1_eLlVzcj94_G4r9j9d_Lj5HRKFnq6jgpuPJtnmIBs88/edit#slide=id.g2134da681e_0_596)

## Only use `||` and `&&` in a boolean context. Else use a ternary.
- From [@bmeurer](https://github.com/developit/preact/pull/610#issuecomment-289981990)
> In general using && or || in a non-boolean context - especially with numbers - is not ideal, because of the semantics of && and || in JavaScript. For example: `let len = o && o.length;` Here `len` can have either the value of o if `ToBoolean(o)` yields `false`, or the value of length property of o. If len is used as a number, then this will prevent the compiler from picking an ideal representation for len, and requires another (expensive) check later to figure out that len is actually a number.

- From [@developit](https://github.com/developit/preact/pull/610#issuecomment-290081189)
> using a ternary seems to avoid an unintentionally different type for falsey conditions - seems like that's the kicker here? (the goal being to have the expression produce a uniform type)

- Current question: what if the default value of a ternary is `undefined` or `null`? Does it suffer from the same perf issue as `something && something.somethingElse`?
  - e.g. Would an `undefined` default (e.g.`vlen = vchildren ? vchildren.length : undefined`) be less optimal for the compiler than the default of `0`? Same question for `null`.
  - "`undefined` or `null` are less ideal than 0 here, as the compiler needs to choose a tagged representation that can represents both `undefined`/`null` as well as numbers. If you use only (small integer) numbers, then the optimizing compilers in VMs can usually pick the ideal unboxed Word/Word32 representation." - [@bmeurer](https://github.com/developit/preact/pull/610#discussion_r108732513)

# Trivia
## Is `something == null` as performant as `something === null || something === undefined`?
Yes, actually. See https://jsperf.com/null-null-vs-null-null/1.

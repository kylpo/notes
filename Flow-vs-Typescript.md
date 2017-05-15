_WIP_

[James Kyle on Twitter: "Major difference between adopting Flow vs TypeScript. Both are fairly easy, but Flow will give you higher type coverage much faster"](https://twitter.com/thejameskyle/status/863195583191728129)

Note: this isn't just Flow vs TS, this is comparing the whole systems. e.g. Flow means we have Babel, which gives us a powerful tool in the way of plugins. TS doesn't have this.

Prettier: [Kent C. Dodds on Twitter: "You know, prettier has given me another reason to choose @flowtype over @typescriptlang."](https://twitter.com/kentcdodds/status/853263564248944640)

# Flow over TS
Flow seems friendlier to React. e.g. Don't need to do React.Component<void, void> from the get go. Can just do React.Component, then add in Props when they become necessary. Also can define it as a class field type, not just the class generic type.

My fear is that I'll choose ts, despite it not working 100% well with react native (sourcemaps, additional compile step), and then flow will hero-out like Jest did and completely fix its broken ways to become incredibly fast and useful. Ts seems more difficult to rip out of a system than something like Flow.

I like Babel more than ts's transpiler

Does ts have an import type option? How else to type props coming in using Provider pattern?

runtime checking option for Flow: https://codemix.github.io/flow-runtime/#/
- but is this _really_ needed?

# flow frustrations
http://artsy.github.io/blog/2017/02/05/Front-end-JavaScript-at-Artsy-2017/

http://djcordhose.github.io/flow-vs-typescript/2017_jfocus_elm.html#/5

tsserver has more features:
- quickfix completions: https://github.com/Microsoft/TypeScript/issues/6943
- soon auto-imports

Even some of the big time flow users are switching, like @gcanti: https://twitter.com/GiulioCanti/status/827194879075876865 and https://github.com/gcanti/fp-ts

labels itself a "A STATIC TYPE CHECKER FOR JAVASCRIPT" on its website.

no description comments
no autocomplete of union types. e.g. alignV_ completes, but not alignVertical='_
versioning and module that check in @flow code in react-native
documentation with little relevant examples - I had to look through definitely-typed to find out how to do things, just clicking on random things
no refactoring tools
platform-specific modules

https://docs.google.com/document/d/1aM5QJQlzxKkj_ZmNxTE1nAlr9vU4mDzv6MO4i0mCOHI/edit

if something here is incorrect at the time of your reading, please correct me! I'd like to keep this current and accurate.

every month or so for the past year, I check in on Flow to see if it is ready-enough for me to go all in on it. Previous frustrations: broken "go to definition" in Nuclide, containers wrapping component types not enforcing.

Seems like flow is treated as a build tool. Evidence in video showing of tree-shaking and such. Really bad dev tooling: auto-gen .flow.js still in early stages, error messages have been confusing, no refactoring tools.
vs Typescript absolutely being a developer tool. Evidence in tooling, vscode, not going in to the webpack space (yet) because it is a lower priority. Focus on docs, examples, dev outreach.

ts outreach is amazing. most questions that I had have already been answered in github issues. Not the case for flow.

totally understand that it is a smaller team, and they're working really hard and building impressive things

I like that flow is opt-in, and seems easy to bail on by just stripping types. Is ts this easy to get away from?

ts has impressive dynamic capabilities like https://github.com/aksonov/react-native-router-flux/issues/1361

I would pick flow for being more on the bleeding edge with babel, but issues like https://github.com/facebook/flow/issues/2968#issuecomment-273623240 slow me down.

considerations:
- js-codeshift - does it work in ts. Is a tool like it even needed when you have types and refactoring?

no enums, and won't have enums: https://github.com/facebook/flow/issues/627

https://www.reaktor.com/blog/refactoring-30000-lines-js-types/ is relevant

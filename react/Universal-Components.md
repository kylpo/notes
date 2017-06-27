_WIP_


Talk about sharing code in one npm package via .native.js and .js, with an index file requiring them.

Also talk about the current .flow.js issue and how file_ext could be fixed in the future to not need the current `declar module` workaround

---

- `files` whitelist to keep down on the size
  - [Mateusz Zatorski on Twitter: "If you're a maintainer of an OSS library please make sure you ship to npm only what's needed. No docs, no dev files, no unneeded files."](https://twitter.com/matzatorski/status/832926885277532160)

# Universal Modules
package.json fields:
"main" -> default
"browser" -> minified
"module" -> es6
(https://github.com/codemix/flow-runtime/blob/master/packages/flow-runtime/package.json#L8)
"react-native" -> obviously

src folder, then compile everything to root

import something from 'something' -> something/index.js and something/index.d.ts
import something from 'something/naitve' -> something/native.js and something/native.d.ts

I'll want an index.js, index.d.ts, index.flow.js to point to generic types and map to correct platform.
Also: index.native.js, native.js (points to index.native.js), etc.
see https://github.com/mobxjs/mobx-react/blob/master/package.json#L19

native.js seems less sustainable (you'd need to clone .d.ts) and what about /ios and /android?

I was thinking it'd be great to rename index.native.js to native.js and just point to it in the "react-native" package.json field, but how would ios and android work?

Here's the code for native.js though:
export * from './index.native.js'

See sticky note.

.d.ts -> .flow using https://github.com/joarwilk/flowgen

# Universal Modules cont'd
"browser" and "react-native" field works with webpack and rn-packager
https://github.com/defunctzombie/package-browser-field-spec
https://webpack.github.io/docs/configuration.html#resolve-packagealias
https://github.com/facebook/react-native/issues/3463
https://github.com/facebook/react-native/pull/2208
https://github.com/facebook/react-native/commit/b86f14738ee8bcb925ad447e0daf58d7ee95f5bb
https://github.com/rtfeldman/seamless-immutable/pull/181/files
https://github.com/scottjehl/picturefill/pull/556#issuecomment-184186115
https://www.bountysource.com/issues/1362028-sanctioned-way-to-mark-packages-as-browser-in-compatible

https://nolanlawson.com/2015/10/19/the-struggles-of-publishing-a-javascript-library/


Doesn't work with Typescript
https://github.com/Microsoft/TypeScript/issues/7753
https://github.com/devCrossNet/universal-cli/issues/9


module alias for native
- package.json doesnt' work for typescript
- https://github.com/tleunen/babel-plugin-module-resolver/issues/29

npm
No way to conditionally depend on peers from platform. Consider optionalDependencies?
https://docs.npmjs.com/files/package.json#optionaldependencies


# Universal Modules (flow)
tried many things like
[lib]
node_modules/constelation-*/index.native.js.flow

but found out the * isn't supported in lib - only direct paths

tried
module.name_mapper='^constelation[-]\(.*\)$' -> 'constelation-\1\/index.native'

also
module.name_mapper='^constelation\(.*\)$' -> 'constelation\1/index.native'

with no luck. Surprised there is no --traceResoltuion option. I need to find some ocaml regex checker. see https://caml.inria.fr/pub/docs/manual-ocaml/libref/Str.html. also see this open issue https://github.com/facebook/flow/issues/1068

tried
traces=1

with no luck

# Universal modules (typescript)
used `./node_modules/.bin/tsc --traceResolution | grep Text` to discover what `paths` did.

http://marcobotto.com/compiling-and-bundling-typescript-libraries-with-webpack/

https://www.typescriptlang.org/docs/handbook/module-resolution.html#node helped a lot!

https://github.com/Microsoft/TypeScript/issues/8328#issuecomment-219583889 was the starting point

        "paths": {
            "stores/*": [
                "app/stores/*"
            ],
            "shared/*": [
                "app/shared/*"
            ],
            // "constelation-Text": [
            //     "node_modules/constelation-Text/index.native"
            // ]
            "*": [
                "node_modules/*/index.native",
                "node_modules/*/index.ios",
                "node_modules/*/index.android",
                "*"
            ]
        },

tried without success:
https://www.typescriptlang.org/docs/handbook/tsconfig-json.html

    // "typeRoots": [
    //     "./node_modules"
    // ],
    "filesGlob": [
        // "node_modules/**/native.d.ts",
        "app/**/*.ts",
        "app/**/*.tsx"
        // "node_modues/constelation-Text/index.native.d.ts",
    ],
    // "typeAcquisition": {
    //     // "enable": true,
    //     "include": [
    //         "node_modues/constelation-Text/index.native.d.ts"
    //     ]
    // },
    // "files": [
    //     "node_modues/constelation-Text/native.d.ts"
    // ],
    // "include": [
    //     "node_modues/constelation-Text/index.native.d.ts"
    // ],

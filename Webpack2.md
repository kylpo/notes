_WIP_

- [Webpack 2: The Complete Developer's Guide | Udemy](https://www.udemy.com/webpack-2-the-complete-developers-guide/?couponCode=4TWIT10)
- [Deploying Applications](https://survivejs.com/webpack/appendices/deploying/)
- [Splitting Bundles](https://survivejs.com/webpack/building/splitting-bundles/)

If you’re a lazy developer, like me, you’re webpack.config.js is likely a hodgpodge of copy/pasted sections form articles and boilerplates. But now that Webpack2 is out and STABLE(!), let’s clean it up and better understand how the magic works.

OK, so you want a site or app that has SSR, tree-shaking, lazy-loaded pages, …. First of all, please marvel at how cool it is that we can actually build this! We don’t need a whole engineering team behind supporting these features, we get to just use Webpack2. Having said that, boy is it quite a bit of work to set up. While working through it, I’d enable one feature, and immediately find a problem with another. Took a while to get the pins lined up.

Resources that helped me:
https://channel9.msdn.com/Blogs/msedgedev/nolanlaw-web-perf-crisis
Video: why care? What to care about? Options today and tomorrow.
Tree-shaking
Use es-native-module libs like react-router/es, OR import modules directly, like:
import Link from 'react-router/lib/Link'
import Route from 'react-router/lib/Route'
import Router from 'react-router/lib/Router'
https://github.com/ReactTraining/react-router/blob/master/docs/guides/MinimizingBundleSize.md
Lodash has this, too
Analyze your bundle size
Chrome networks tab
danvk/source-map-explorer: Analyze and debug space usage through source maps
A React + Webpack Optimization Case – Medium
Profiling, react-router code splitting
How to Make Your React Apps 15x Faster – ReactJS News
Building for Production
Webpack official guide is pretty great now
SurviveJS - Splitting Bundles


Dynamic imports
https://twitter.com/addyosmani/status/811957986268590080




Webpack dev server learnings. Particularly for how it does with static sites.

static generator barfs
- thought i needed to do something like https://github.com/ampedandwired/html-webpack-plugin, but then you'd still have 2 diff templates for webpack vs static-generator.
- then thought I'd need something like clean public/, build public/index.html, webpack-dev-server, but it would still watch and update the bundle... needed `serve` for npm run serve-build

webpack.config.js vs webpack.config.babel.js

https://webpack.github.io/docs/webpack-dev-server.html
https://webpack.github.io/docs/tutorials/getting-started/
https://github.com/petehunt/webpack-howto
https://github.com/webpack/docs/wiki/cli
https://github.com/webpack/docs/wiki/configuration
https://github.com/webpack/docs/wiki/webpack-dev-server



https://medium.com/webpack/webpack-performance-budgets-13d4880fbf6d#.dwoo25g1h

https://github.com/blacksonic/babel-webpack-tree-shaking
https://github.com/ModusCreateOrg/budgeting-sample-app-webpack2

https://github.com/webpack/webpack/issues/2899
https://github.com/mishoo/UglifyJS2/issues/1261

loose:
https://github.com/babel/babel/tree/master/packages/babel-preset-es2015
http://www.2ality.com/2015/12/babel6-loose-mode.html

Babili - fixes uglifier IIFE issue (but may be unstable?)
[Adam Rackis on Twitter: "The new, ES6-compatible uglify-js https://t.co/SocuJH6ABf"](https://twitter.com/AdamRackis/status/862027473374109698)
modules: false - able to tree-shake
loose: true - smaller output, but won’t use modern es6 - what .ts does, too?

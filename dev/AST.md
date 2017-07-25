# Learning
- [Writing custom Babel and ESLint plugins with ASTs (Open West 2017) - YouTube](https://www.youtube.com/watch?v=VBscbcm2Mok)
  - Watch this, first. It is a great intro!
  - [A beginner's guide to ASTs by Kent C. Dodds](http://slides.com/kentcdodds/a-beginners-guide-to-asts#/5/1)
- [Introducing Babel and AST | Learn Code Transformation and Linting with Abstract Syntax Trees (ASTs)](https://frontendmasters.com/courses/linting-asts/introducing-babel-and-ast/) for if you want more
- [How Writing a Babel Plugin is like Wiring JQuery](http://henryzoo.com/babel-plugin-slides/assets/player/KeynoteDHTMLPlayer.html#0)
- skim through [babel-handbook/plugin-handbook](https://github.com/thejameskyle/babel-handbook/blob/master/translations/en/plugin-handbook.md)

# Creating your own
https://astexplorer.net/ is your main tool

use [Babel types](https://babeljs.io/docs/core-packages/babel-types/)

## Testing
I found [babel-plugin-tester](https://github.com/babel-utils/babel-plugin-tester) to not be very helpful. I prefer just using Jest's `expect` for inputs and `toMatch` for output.

# Others getting psyched on this
- "Writing custom babel plugins considered "approachable" and "teach you ... about the language" 🎉 #tryit 😃 https://t.co/FsRQTHjTSI" - [Kent C. Dodds](https://twitter.com/kentcdodds/status/887878863325245440)
- "If you're a JS dev and you haven't tried writing a Babel plugin yet, try it! Didn't realize learning about ASTs and Babel would be so fun" - [Matt Hamil ᕕ( ᐛ )ᕗ](https://twitter.com/_matthamil/status/888145499680886784)
- "Published my first @babeljs plugin last night 🎉! Check it out https://t.co/wie5JEOWfX. Thanks @kentcdodds for your talk on ASTs 👏 https://t.co/ZbbzwcIfCx" - [Matt Phillips](https://twitter.com/mattphillipsio/status/887684639158140928)
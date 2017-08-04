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

# Transforms
- https://github.com/gaearon/babel-plugin-react-transform#transforms
-  `["react-remove-properties", {"properties": ["data-test"]}], ` to remove test data props!


# Others getting psyched on this
- [AST’s and JavaScript: Write Code that Writes Code – Super Development](https://superdevelopment.com/2017/07/24/asts-and-javascript-write-code-that-writes-code/)
  - I like describing writing transforms as "write code that writes code"
- "Writing custom babel plugins considered "approachable" and "teach you ... about the language" 🎉 #tryit 😃 https://t.co/FsRQTHjTSI" - [Kent C. Dodds](https://twitter.com/kentcdodds/status/887878863325245440)
- "If you're a JS dev and you haven't tried writing a Babel plugin yet, try it! Didn't realize learning about ASTs and Babel would be so fun" - [Matt Hamil ᕕ( ᐛ )ᕗ](https://twitter.com/_matthamil/status/888145499680886784)
- "Published my first @babeljs plugin last night 🎉! Check it out https://t.co/wie5JEOWfX. Thanks @kentcdodds for your talk on ASTs 👏 https://t.co/ZbbzwcIfCx" - [Matt Phillips](https://twitter.com/mattphillipsio/status/887684639158140928)

"We should always ask ourselves 'Can I do this at compile time?' while reading or writing code. With new solutions like preval and babel-macros it has become easier and more accessible to do this. And knowledge of ASTs and babel plugins is more important than ever before." - [Ives van Hoorne on Twitter](https://twitter.com/CompuIves/status/890069509050073088) of codesandbox.io fame

# Problems
- [Christoph Nakazawa on Twitter: "@kentcdodds @threepointone It's one of the plugins that potentially significantly increase compile time which many will blame babel for. Plugin architectures worry me."](https://twitter.com/cpojer/status/893122067595505665)
  - "This is a plugin architecture within a plugin architecture of sorts, therefore losing complete control over compile times, I worry."

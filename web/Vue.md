_WIP_

Vue is nice for its 'single file components'

[10 things I love about Vue – Duncan Grant – Medium](https://medium.com/@dalaidunc/10-things-i-love-about-vue-505886ddaff2)

---

Vue vs React

Vue: do you want to write document in what is essentially html, with 3 key sections (template, script, style). I imagine I'd need to jump around the single-file components quite a bit. From template tag/classname to style. From template data to script data. Also need to parse template dsl if going the way of string templates. Also think about a decomposition refactor, and how much code would need to be cut/pasted.

React: or as js (via jsx) and not really need to jump around at all (with style props).

One pro of Vue is making templates a first-class concern for perf though. I wouldn't need to write shouldComponentUpdate()s.

I would also think that a WYSIWYG editor might have an easier job of thinking about components in this way: template, style, script. Thought about this when reading through Android's docs on XML layout. They're able to make a designer view because it is made up of XML.

https://vuejs.org/v2/guide/comparison.html<Paste>

---

[vuetifyjs/vuetify: Material Component Framework for Vue\.js 2](https://github.com/vuetifyjs/vuetify)

---




- [Learning JavaScript? Try Vue.js – Thinking in Code](https://blog.madewithenvy.com/learning-javascript-try-vue-js-ad27c7b6687f)
- [Comparison with Other Frameworks — Vue.js](https://vuejs.org/v2/guide/comparison.html#React)
- [Switching From React To Vue.js](http://vuejsdevelopers.com/2017/05/28/switch-from-react-to-vue-js/)
- [How To (Safely) Use A jQuery Plugin With Vue.js](http://vuejsdevelopers.com/2017/05/20/vue-js-safely-jquery-plugin/)
- [Nuxt.js on Twitter: "A little schema to explain how Nuxt.js works https://t.co/MQDLtRJPHV"](https://twitter.com/nuxt_js/status/869134582901342208)
- [Between the Wires: An interview with Vue.js creator Evan You](https://medium.freecodecamp.com/between-the-wires-an-interview-with-vue-js-creator-evan-you-e383cbf57cc4)

# Dev Tools
[What’s new in Vue Devtools 4\.0 – The Vue Point – Medium](https://medium.com/the-vue-point/whats-new-in-vue-devtools-4-0-9361e75e05d0)

# Against it
- Template strings
  - ["UI string templates are regaining traction (iknowrite?). We should meme them back into Best Practices just so we can Rethink them again."](https://twitter.com/jordwalke/status/869312543562452993)
  - ["Right - each framework shipping a proprietary DSL for smearing JS into html attributes is something I hope to never deal with again."](https://twitter.com/AdamRackis/status/869389964605362180)
  - ["Having to use re-invented scope and syntax instead of JavaScript, having to futz around to get stuff into scope and all scope-related magic"](https://twitter.com/jbscript/status/869397829407526912)
  - ["The output isn't the issue, it's the extra stuff that needs to be in your head to successfully write, debug and understand the template"](https://twitter.com/jbscript/status/869405002711785472)
  - [Daniel Steigerwald on Twitter: "@ryanflorence The point of components over templates isn't the state but composable debuggable code, not HTML string black boxy tag soup."](https://twitter.com/steida/status/746464098527944705)
  - [Ryan Florence on Twitter: "If you're really into everything being stateless "Dumb Components", you might have a look at templating libs instead of React."](https://twitter.com/ryanflorence/status/746399922723819520)

# Examples
- [lookstudios/vue-loop: 🌀 Infinite content loop for Vue](https://github.com/lookstudios/vue-loop)
- [tmm/notational: Real-time notes app built with Vue.js (inspired by, but not affiliated with Notational Velocity)](https://github.com/tmm/notational)

"React Native has made me a better Web Developer"

Flexbox, relative, apis

# Make your own rendering environment
You likely already do this today by setting box-sizing: border-box instead of content-box

when on the web, you have so many primitives: div, span, ul, li, button, sematic divs like nav, section, forms

moving to react-native had a different set of primitives, far fewer primitives: View, ScrollView

Then, with web, is it inline or block? how does it flow? Native made the decision for us so we didn't have to.

These primitives are the lego bricks. We can't change the actual primitives, like the standard lego brick, but we can replace them with the standard brick + the thin piece that goes on top of it, like an adapter.

---

Flexbox and position: relative defaults

Back to a world of Text, Images, and Views
- Powerful primitives
- Purpose of component first, then use "tag" or accessiblityType for specific things like <nav>, <content>, <header>, etc

Not everything should be top-down.
- Animated

Web really does have its issues. Animations, touch points (not being stuck in browser allows full-bleed carousels, for example)

css-in-js

---

"RN made me a better web dev"

"RN showed this web dev the value in native"

---

# Opposite: React Web made me a better RN dev

ReactTransitionGroup
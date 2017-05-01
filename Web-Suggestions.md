_WIP_

Things to consider before writing any code

# Feature Flags
- Build in a feature flag capability from the start. You'll eventually want it for A/B testing, staged releases, and potentially even a beta program.
- [Feature flags in React](http://blog.rstankov.com/feature-flags-in-react/)
- [react-bits/29.feature-flags-using-redux.md](https://github.com/vasanthk/react-bits/blob/master/patterns/29.feature-flags-using-redux.md)
- [ember-cli/babel-plugin-feature-flags: A babel transform for managing feature flags](https://github.com/ember-cli/babel-plugin-feature-flags) seems like a great approach. Features flags statically, and dynamically.

```js
import isEnabled from 'my-features';

if (isEnabled('new-feature')) {
  // code
}
```
becomes
```js
import isEnabled from 'my-features';

if (false) {
  // code
}
```

# Internationalization
- Important for reach, and difficult to bolt on after the fact. Build in Internationalization from the start.
- [Internationalizing React Apps – Smashing Magazine](https://www.smashingmagazine.com/2017/01/internationalizing-react-apps/)
- [globalizejs/globalize: A JavaScript library for internationalization and localization that leverages the official Unicode CLDR JSON data](https://github.com/globalizejs/globalize)
  - used by twitter lite
- `Strings` files so that they can all be translated. No inline text, not even the text of an "OK" button.
- [Jason Miller 🦊⚛ on Twitter: "@threepointone @nekrtemplar we use it a lot for internationalization: <Text id="HELLO">hello world</Text>"](https://twitter.com/_developit/status/856196870179258368)

# Accessibility (a11y)
- [A11Y Style Guide](http://a11y-style-guide.com/style-guide/)

# Use an 8-point grid system
- (spacial) Consistency is important to the overall feel of a product
- [Intro to the 8-Point Grid System – Built to Adapt – Medium](https://medium.com/built-to-adapt/intro-to-the-8-point-grid-system-d2573cde8632#.5wpma8ukx)
- [8pt Material Design GUI Templates – Medium](https://medium.com/@_bklmn/8pt-gui-templates-ed8798badab3#.3dtnmoq8h)
- [Metrics & keylines - Layout - Material design guidelines](https://material.io/guidelines/layout/metrics-keylines.html#)

# Typography
- [Bricolage | Typefaces: The easiest way to self-host open-source fonts](https://www.bricolage.io/typefaces-easiest-way-to-self-host-fonts/)
- [Typography for Developers – CSS Wizardry – CSS Architecture, Web Performance Optimisation, and more, by Harry Roberts](https://csswizardry.com/2017/02/typography-for-developers/)
- [Typography](https://robots.thoughtbot.com/typography)
- Use `line-height` for text wrapping only

# Target browsers
- polyfill.io
  - [Andrew Betts on Twitter: "The marvellous people at the Guardian just went live with @polyfillio - now used by multiple major news sites! https://t.co/sFWGd9pJ1T"](https://twitter.com/triblondon/status/846707701220622336)

# Theming
- use css variables. They're now supported in all major browsers (Edge just landed support).
  - [Serg Hospodarets on Twitter: "Huge news! After Microsoft EDGE 15 release today, CSS Custom Properties (aka CSS Variables) work cross-browser!!! 🔥 https://t.co/UzL2IsxdEV https://t.co/Aku2rFlgxY"](https://twitter.com/malyw/status/851913674021371904)
- [How we made our product more personalized with CSS Variables and React](https://medium.com/geckoboard-under-the-hood/how-we-made-our-product-more-personalized-with-css-variables-and-react-b29298fde608)

# SEO
SEO is related to "location, location, location".

thought about while reading https://css-tricks.com/seo-and-location/

# App Components
- Stage Left, Stage Right, Modal, etc

# Layers system
- Interesting idea to formalize z-index and layers: https://github.com/fckt/react-layer-stack#rationale. This is the Layers tab of your WYSIWYG.

# Analytics

# Polyfills
If it’s new syntax, you can probably transpile it
If it’s a new object or method, you can probably polyfill it
If it’s something clever that the browser does outside of your code, you’re probably SOL

https://hackernoon.com/polyfills-everything-you-ever-wanted-to-know-or-maybe-a-bit-less-7c8de164e423#.jfpsi4auo

Polyfill fewer things by targeting only newer browsers
Only send polyfills to browsers that need them
Only polyfill things used in your code

http://babeljs.io/docs/plugins/preset-env/ will reduce the amount of features that are polyfilled based on the browsers you are targeting.
- doesn't actually shave off much: 6kb
- polyfill.io instead to load polyfills iff the browser needs it

# Events

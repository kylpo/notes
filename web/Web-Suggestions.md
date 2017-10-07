_WIP_


[Building m.uber: Engineering a High-Performance Web App for the Global Market - Uber Engineering Blog](https://eng.uber.com/m-uber/)

# App considerations
See Rules: Design

App Controls (widgets/components? - can’t think of a good name)
- Store constants like AppBar height in /shared/APP.js
- Dialog/Modal (overlay),
- Stage Left, Stage Right
- or Left Sheet, Right Sheet, Bottom Sheet: [Bottom Sheets - Material Components for Android](https://material.io/components/android/catalog/bottom-sheet-behavior/)
UIControls.showModal(<Content />)

Media Queries
- [Breakpoints are for reflow, the rest is fluid – UX Planet](https://uxplanet.org/breakpoints-are-for-reflow-the-rest-is-fluid-58ab641f03c3)

>  A page reflow rearranges objects within the web browser to present the user with an optimal interactive experience, based on their device type and orientation. A reflow updates interaction models to better reflect the ergonomics of the use case, as well as the visual presentation. A reflow is about more than just the amount of real-estate available within the viewport, it’s about matching user behaviors and affordances to our on-page presentation.

Mobile Navigation Experiences
- nav stacks + tabs (twitter)
- accordion (google inbox)
- hamburger "drawer"
- swipe left/right "paging"
- shared element transitions
- Safari (iOS) shows tabs as a 3D stack, grid in landscape mode.
- modal navigation: Show modal, navigate like regular, remove modal
- https://twitter.com/ryanflorence/status/803665049826906112


---

Things to consider before writing any code

Fork this doc into Web Considerations and Web Suggestions. Suggestion style is like `DO: ___`, `WHY: ___`, like a style guide

# Feature Flags
![https://css-tricks.com/ios-11-safari-feature-flags/](https://res.cloudinary.com/css-tricks/image/upload/c_scale,w_1000,f_auto,q_auto/v1506483761/Artboard-2_lldtij.jpg)

- Build in a feature flag capability from the start. You'll eventually want it for A/B testing, staged releases, and potentially even a beta program.
- [Feature flags in React](http://blog.rstankov.com/feature-flags-in-react/)
- [react-bits/29.feature-flags-using-redux.md](https://github.com/vasanthk/react-bits/blob/master/patterns/29.feature-flags-using-redux.md)
- [ember-cli/babel-plugin-feature-flags: A babel transform for managing feature flags](https://github.com/ember-cli/babel-plugin-feature-flags) seems like a great approach. Features flags statically, and dynamically.
- [Jason Miller 🦊⚛ on Twitter: "⚙️ Preconf: build configurable components. https://t.co/1hW0n37eFr https://t.co/icJPDyVtzN"](https://twitter.com/_developit/status/874675422608412676)
- [Embracing real\-time feature toggling in your React application](https://techblog.commercetools.com/embracing-real-time-feature-toggling-in-your-react-application-a5e6052716a9)
  - "Toggling features within a code base is a technique to influence the behaviour of software without having to redeploy. It is often used in conjunction with Continuous Delivery enabling alternative branches for different user groups within the interface a web application. These branches should optimally be triggered independently from the main code base."
- [Using React in Multiple Environments](https://daveceddia.com/multiple-environments-with-react/#configure-feature-flags-at-build-time)
  - and using `.env` files
- [React 16: A look inside an API\-compatible rewrite of our frontend UI library \| Engineering Blog \| Facebook Code \| Facebook](https://code.facebook.com/posts/1716776591680069/react-16-a-look-inside-an-api-compatible-rewrite-of-our-frontend-ui-library)
  - they've been rewritting the core via flags. This allowed them to remain working on a single branch (not forking the code).

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

## A/B Testing
- [The Tenets of A/B Testing from Duolingo’s Master Growth Hacker \| First Round Review](http://firstround.com/review/the-tenets-of-a-b-testing-from-duolingos-master-growth-hacker/)
- [How to quickly set up A/B testing for React websites](https://medium.com/@yilingchen/how-to-quickly-set-up-a-b-testing-for-react-websites-dcb321fcd1f)
- [dollarshaveclub/study: A simple, progressive, client/server AB testing library 📚](https://github.com/dollarshaveclub/study)
- [Split Testing | Netlify](https://www.netlify.com/docs/split-testing/)
- [A/B\-Test Calculator \- Power & Significance \- ABTestGuide\.com](https://abtestguide.com/calc/)

## Feature Flag vs A/B Testing
- Is the line a build-time vs runtime thing? A/B testing is pushed on to you. Feature flags are configurable.
- All depends if it is implemented server-side or client-side. So really, the question is: do you want this configurability at build-time? Or run-time?


# Internationalization
- First, do you need this? If it is a site, google's built in conversion tool may be desired. If it is an app, probably want to internationalize.
- [Add Internationalization (i18n) to a React app using React Intl - Course by @damon_bauer @eggheadio](https://egghead.io/courses/add-internationalization-i18n-to-a-react-app-using-react-intl)
- Important for reach, and difficult to bolt on after the fact. Build in Internationalization from the start.
- [Internationalizing React Apps – Smashing Magazine](https://www.smashingmagazine.com/2017/01/internationalizing-react-apps/)
- [globalizejs/globalize: A JavaScript library for internationalization and localization that leverages the official Unicode CLDR JSON data](https://github.com/globalizejs/globalize)
  - used by twitter lite
- `Strings` files so that they can all be translated. No inline text, not even the text of an "OK" button.
- [Jason Miller 🦊⚛ on Twitter: "@threepointone @nekrtemplar we use it a lot for internationalization: <Text id="HELLO">hello world</Text>"](https://twitter.com/_developit/status/856196870179258368)
- [Este strategy for i18n (multiple languages) – Daniel Steigerwald – Medium](https://medium.com/@steida/este-strategy-for-i18n-multiple-languages-8a0f0162f176)
- [React.JS Localization v0.2 – Dmitry Kudryavtsev – Medium](https://medium.com/@skwee357/react-js-localization-v0-2-4589bbd4a26a)
- When is Localization needed?
  - For sites like wrkflows, wouldn't it be better for people to activate Google Translate? Maybe Localization is only useful for apps and labeling controls within the app?
  - How is Accesibility affected?

# Accessibility (a11y)
- [A11Y Style Guide](http://a11y-style-guide.com/style-guide/)
- ![](https://pbs.twimg.com/media/DD4waUsXcAAHIwL.jpg:large)
  - [Manuel Matuzović on Twitter: "#a11y posters: Dos and don'ts on designing for accessibility https://t.co/QU8a2C0Iaf https://t.co/tUUSe6xMVN"](https://twitter.com/mmatuzo/status/882195808619286528) 
- [🎥 Does reordering content affect accessibility?](https://www.youtube.com/watch?v=8MAvH6vYbDo)
  - When changing position, like flexbox's `order`, you can mess up tab order. Try to keep position in your `html`.

# Use an 8-point grid system
- (spacial) Consistency is important to the overall feel of a product
- [Intro to the 8-Point Grid System – Built to Adapt – Medium](https://medium.com/built-to-adapt/intro-to-the-8-point-grid-system-d2573cde8632#.5wpma8ukx)
- [8pt Material Design GUI Templates – Medium](https://medium.com/@_bklmn/8pt-gui-templates-ed8798badab3#.3dtnmoq8h)
- [Metrics & keylines - Layout - Material design guidelines](https://material.io/guidelines/layout/metrics-keylines.html#)
- [Sketch Workflow — 8 point Soft Grids](https://medium.com/sketch-app-sources/8-point-soft-grids-in-sketch-e8f1d5ca2cd4)

# Typography
- [Bricolage | Typefaces: The easiest way to self-host open-source fonts](https://www.bricolage.io/typefaces-easiest-way-to-self-host-fonts/)
- [Typography for Developers – CSS Wizardry – CSS Architecture, Web Performance Optimisation, and more, by Harry Roberts](https://csswizardry.com/2017/02/typography-for-developers/)
- [Typography](https://robots.thoughtbot.com/typography)
- Use `line-height` for text wrapping only
- [Optimizing Web Fonts for Performance: the State of the Art — SitePoint](https://www.sitepoint.com/optimizing-web-fonts-for-performance-the-state-of-the-art/)
- [Your Body Text Is Too Small - Marvel Blog](https://blog.marvelapp.com/body-text-small/?utm_source=frontendfocus&utm_medium=email)

# Target browsers
- polyfill.io
  - [Andrew Betts on Twitter: "The marvellous people at the Guardian just went live with @polyfillio - now used by multiple major news sites! https://t.co/sFWGd9pJ1T"](https://twitter.com/triblondon/status/846707701220622336)

## Polyfills
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

# Theming
- use css variables. They're now supported in all major browsers (Edge just landed support).
  - [Serg Hospodarets on Twitter: "Huge news! After Microsoft EDGE 15 release today, CSS Custom Properties (aka CSS Variables) work cross-browser!!! 🔥 https://t.co/UzL2IsxdEV https://t.co/Aku2rFlgxY"](https://twitter.com/malyw/status/851913674021371904)
- [How we made our product more personalized with CSS Variables and React](https://medium.com/geckoboard-under-the-hood/how-we-made-our-product-more-personalized-with-css-variables-and-react-b29298fde608)

# Onboarding
![](https://github.com/kylpo/notes/blob/master/assets/onboarding.png?raw=true)

# SEO
- [SEO best practices and requirements for modern sites | John Mueller - YouTube](https://www.youtube.com/watch?v=JlP5rBynK3E)
  - URL most important
  - 1 URL per content
    - languages have disctinct urls, too
  - make links w/ `<a>`, not onclick
    - so googlebot can navigate your site
  - hidden content is devalued, as it isn't primary content
    - does this mean page transitions that fade in are missing out on SEO?
      - I asked John, and it seems like it should be OK. See https://www.youtube.com/watch?v=5TsGXF4wNqM&feature=youtu.be&t=43m9s.
      - It did make me think that it should be done with css-animation (not js triggering a transition) for non-google SEO though
    - what about lazy loaded images
      - I’m thinking lazy loaded/revealed content is bad for SEO, as it isn't rendered until scroll, which I don't think googlebot does
    - [How Does Google Handle CSS + Javascript "Hidden" Text? - Whiteboard Friday - Moz](https://moz.com/blog/google-css-javascript-hidden-text)
  - page transition delays might snapshot old page
    - if route changes, and there is a transition out that takes a certain amount of time
  - Google Search Console to check your sites
- Fetch As Google tool to see how googlebot indexes your site
- Is above the fold content ranked higher?
  - no, googlebot sees all of the content. What matters is semantic markup to link related content. Otherwise, googlebot wouldn't know that a div on some part of the page is related to another div further down.
- [Hidden text and links - Search Console Help](https://support.google.com/webmasters/answer/66353?hl=en)
- SEO boosted by accessibility?
- [The Lazy Writer’s Guide to 30-Minute Keyword Research - Moz](https://moz.com/blog/30-minute-keyword-research)
- Blogging has helped me understand the importance of SEO and good titles. Most of my "Redux Best Practices" traffic came from google.

![](https://github.com/kylpo/notes/blob/master/assets/seo-hidden-text.png?raw=true)

SEO is related to "location, location, location".

thought about while reading https://css-tricks.com/seo-and-location/

# App Components
- Stage Left, Stage Right, Modal, etc

# Layers system
- Interesting idea to formalize z-index and layers: https://github.com/fckt/react-layer-stack#rationale. This is the Layers tab of your WYSIWYG.

# SSR
- [Sunil Pai on Twitter: "Based on responses... *any* SPA (react/wc/ember/whatever) is invisible to search engines except google ? SSR your pages, peeps. https://t.co/MtHr4MbJ2O"](https://twitter.com/threepointone/status/870638919695699969)
  - [Jordan Schroter on Twitter: "@threepointone Often forgot about but SSR is also beneficial for sharing urls on most social media sites. For reference: https://t.co/FS6bZIdfEl"](https://twitter.com/_jschr/status/870641437121097729)

# Analytics
- [The Browser Statistics That Matter](http://mediatemple.net/blog/tips/browser-statistics-matter/)

# Events

# Continuous Integration (CI)
- [ebidel/lighthouse-ci: Lighthouse CI](https://github.com/ebidel/lighthouse-ci)

# Content
https://www.usability.gov/how-to-and-tools/methods/writing-for-the-web.html

people don't read web pages, they scan. On average, people only read 20–28% of web page content. Reading from screens is much slower than reading from paper. People will give up and leave your site unless information is easy to access and understand.

https://developers.google.com/web/fundamentals/design-and-ui/responsive/content

Web users are often action oriented, "leaning forward" in the hunt for answers to their current question, rather than leaning back to absorb a good book.
https://www.nngroup.com/articles/concise-scannable-and-objective-how-to-write-for-the-web/

Users tend to read in F pattern:

# Favicon
- [Favicons, Touch Icons, Tile Icons, etc. Which Do You Need? | CSS-Tricks](https://css-tricks.com/favicon-quiz/)

# Time
- use https://date-fns.org/docs/I18n#supported-languages if you don't need much for lang support
- else use Moment

# animated images
- use <video> instead of animated GIFs
- Gifs are bigger


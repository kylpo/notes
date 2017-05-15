_WIP_

Let's standardize a Website's characteristics:
- Best thought of as a living or static document
- Annotation standard applies
  - [Perspectives on Annotation - YouTube](https://www.youtube.com/watch?v=m2cJNDs7y2Y)
  - "Robust Anchor Links" to link to more than just headers
- Clickable headers for anchor links required (like github's markdown, not like Medium)
  - I think I could feel complete with the purpose of my life if I was able to get all websites to anchor link their headers.
  - [example](https://developer.android.com/training/gestures/scale.html#pan) of frustrating experience where anchor links exist, but not discovered by clicking on the Header:
- `h1`, `h2`, etc make sense and are relevant
  - same with `main`, `section`, `article`, `aside`, etc

Let's standardize a Webapp's characteristics:
- Best thought of as scenes/screens instead of documents

- [Read web pages offline with Chrome on Android](https://blog.google/products/chrome/read-web-pages-offline-chrome-android/)
  - Wouldn't really be able to save an app offline ahead of time, would you? If so, would it be useful?

- [Sam Saccone on Twitter: "For every 1 sec increase in page speed, engagement score increased by 5%. This translated into millions in revenue💰 https://t.co/v4Mn0y0PlX"](https://twitter.com/samccone/status/862329675841810433)

Is it that you think of a scene, with independent "component" updates for an app, and a page with all dependent pieces for a site? Thought about from seeing image at https://medium.com/@l_e/prettyloader-a-pattern-for-wait-animations-in-react-3f7ec1451d40.

# Generalizations
- Care about SEO? Site. Else, app.
- Want an app bar? App. Else, site with tabs/links on top, probably.

# App vs Site
App has LHS "app-tabs" bar http://collectui.com/designers/pijusgraphics/monitoring-dashboard

Site has top tab bar

Kind of a joke, but also partly true.

Reading https://medium.com/code-life/frontend-applications-on-s3-df5134e320f0#.1opyi21va on hosting sites with s3 helped me identify the difference between sites and apps. Sites are anything that COULD be served statically: it does not have state. https://musefind.com/ is a site because each page can be served statically. The content may still be dynamic via apis, but the structure of the site itself is static. If someone chooses to LOGIN, then it will likely direct them to a web app that customizes its structure and content to that user -> it has state.

web APP vs web SITE
- global state
- from rauchg

Sites should strive for no global state?
- URL is the single source of truth for what is currently shown
- Makes sense when you think of a site as a set of documents
  - searchable documents (and good for SEO)

Divide seems to be more inline with if you care about SEO. Sites care deeply about SEO, and are built differently to handle it. Apps have affordances that do not care about SEO.

# Conclusions
Overall, this distinction likely isn't helpful. Because as soon as you add global state to a site, it becomes an app, even if it still feels more like a site (like an e-commerce site). The more useful distinction is web vs native. I suppose it could be helpful, if you think of your product as a site, to limit it from app state for as long as possible. For example, modals are url accessible, all "state" is serialized to the URL. LINK TO APP STATE DOC

Maybe it isn't about a website vs webapp. There are documents (blogs, news, collections like wikipedia, documentation (maybe this is just a collection, too?)) stores, e-commerce, forums, video stores. Where do apps, gmail, gmaps, etc fit in?

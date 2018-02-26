_WIP_


Really, the main distinction I could think of was whether the content is tailored to you specifically or not. Gmail is
ONLY your content. Versus some Forum, which I deem to be a site, that you can log in to, but the information is all
public. Pieces will change based on your logged in vs logged out status, but the site exists. The content exists,
independent of your existence.

<<link to guermo's definition>>
<<link to google.io panel where jake tries to answer>>

Why does this matter?
Mainly because how you build the two can be radically different. Sites may be best to have global css and templates to
be filled with a cms, for example. They also will care strongly about cache-ability and preserving state in the url.
They may even be fine to keep any internal state in document.window. No redux required. This is why jquery, backbone,
etc are still viable solutions. Also a reason for people to prefer Vue vs React. Vue aligns better with html, React
aligns better with JS.

Apps do cater much better to a component, re-usable model.

In choosing a framework and tech stack, you'll see arguments all over the board, and it isn't necessarily that that
strongly opinionated person is wrong, it is just that they may have different concerns and objectives for their web
service. They may fall more on the site side or the app side.

What gets really trick is when sites have app features, or apps have site features. Nike.com has a login with
personalized content, more than just a browser cookie with the user's shopping cart. It has personalized
recommendations, a shoe builder, etc.

It can be equally difficult to bolt on site-like features to apps. This is why SSR can be such a big deal, and
extracting css can be such a big deal.

---

A site is transient. You may come back to it, you may not. This is also what Android's Instant App is useful for. It is
used for handling shared links to in-app resources.

An app is built for returning users. "You will come back"

site is something you'd want links to, really. It is more of a document or file. Android's Instant Apps make sense here.
IMDB's native app is more like a site, because it is more of a repository of resources. These resources should be
Instant App capable.

an App, something that wouldn't really have a resource a user would like linked to, would not benefit from Instant Apps
modularization. IMDB can have app-like features, like logged-in user suggestions, special offers, etc, that you would
not really be able to benefit from Instant Apps.

---


---

Let's standardize a Website's (or Web Document's) characteristics:
- Best thought of as a living or static document
- Annotation standard applies
  - [Perspectives on Annotation - YouTube](https://www.youtube.com/watch?v=m2cJNDs7y2Y)
  - "Robust Anchor Links" to link to more than just headers
- Clickable headers for anchor links required (like github's markdown, not like Medium)
  - I think I could feel complete with the purpose of my life if I was able to get all websites to anchor link their headers.
  - [example](https://developer.android.com/training/gestures/scale.html#pan) of frustrating experience where anchor links exist, but not discovered by clicking on the Header:
  - and/or build this into browsers. Show header on hover, right click, w/e
    - [Display \#Anchors \- Chrome Web Store](https://chrome.google.com/webstore/detail/display-anchors/poahndpaaanbpbeafbkploiobpiiieko?utm_source=chrome-app-launcher-info-dialog)
  - I like that these docs modify the url based on scroll position: https://www.google.com/design/spec-wear/patterns/interactive-watch-faces.html#
- `h1`, `h2`, etc make sense and are relevant
  - same with `main`, `section`, `article`, `aside`, etc
- links to a homepage
  - [Best Practices for Homepage Links on websites](https://www.nngroup.com/articles/homepage-links/?utm_source=frontendfocus&utm_medium=email)
  - "Going back to the homepage is a **common task**. People often go to the homepage when they’re disoriented, they have gone too deep into a site, or they’re ready to start a new task. Because of their dependency on **search** engines, most users enter websites through an interior page and bypass the homepage entirely. Easy access to the homepage provides a new starting point for those who are on the wrong page or want to explore other parts of the site."
- **Updated on**
  - "Updated on" dates required

Let's standardize a Webapp's characteristics:
- Best thought of as scenes/screens instead of documents

- [Read web pages offline with Chrome on Android](https://blog.google/products/chrome/read-web-pages-offline-chrome-android/)
  - Wouldn't really be able to save an app offline ahead of time, would you? If so, would it be useful?
- [Ricky Mondello on Twitter: "Safari 11 and iOS 11 have something really special for Safari Reader users — setting it to activate automatically. https://t.co/PTth8ZtNfv"](https://twitter.com/rmondello/status/871830117240066049)
- always-on Reader mode in Safari for High Sierra

- [Sam Saccone on Twitter: "For every 1 sec increase in page speed, engagement score increased by 5%. This translated into millions in revenue💰 https://t.co/v4Mn0y0PlX"](https://twitter.com/samccone/status/862329675841810433)

Is it that you think of a scene, with independent "component" updates for an app, and a page with all dependent pieces for a site? Thought about from seeing image at https://medium.com/@l_e/prettyloader-a-pattern-for-wait-animations-in-react-3f7ec1451d40.

Sites are so amazing for research. Links, headers, cmd-click tabs, etc. We should embrace this!

# Generalizations
- Care about SEO? Site. Else, app.
- Want an app bar? App. Else, site with tabs/links on top, probably.

# App vs Site
App has LHS "app-tabs" bar http://collectui.com/designers/pijusgraphics/monitoring-dashboard

Site has top tab bar

Kind of a joke, but also partly true.

Reading https://medium.com/code-life/frontend-applications-on-s3-df5134e320f0#.1opyi21va on hosting sites with s3 helped me identify the difference between sites and apps. Sites are anything that COULD be served statically: it does not have state. https://musefind.com/ is a site because each page can be served statically. The content may still be dynamic via apis, but the structure of the site itself is static. If someone chooses to LOGIN, then it will likely direct them to a web app that customizes its structure and content to that user -> it has state.

"Native apps like Twitter, Facebook, & Instagram are swell, but appreciate for a moment that the web gives your posts universal addresses."
-https://twitter.com/stshank/status/806981502881759232


web APP vs web SITE
- global state
- from rauchg

Sites should strive for no global state?
- URL is the single source of truth for what is currently shown
- Makes sense when you think of a site as a set of documents
  - searchable documents (and good for SEO)

Divide seems to be more inline with if you care about SEO. Sites care deeply about SEO, and are built differently to handle it. Apps have affordances that do not care about SEO.

# Web linkability
I think just about everything should be linkable. For example, a specific comment to an article.

# Writing for the Web
https://www.usability.gov/how-to-and-tools/methods/writing-for-the-web.html

people don't read web pages, they scan. On average, people only read 20–28% of web page content. Reading from screens is much slower than reading from paper. People will give up and leave your site unless information is easy to access and understand.

https://developers.google.com/web/fundamentals/design-and-ui/responsive/content
 ^ good guidelines to show wrkflows users

Web users are often action oriented, "leaning forward" in the hunt for answers to their current question, rather than leaning back to absorb a good book.
https://www.nngroup.com/articles/concise-scannable-and-objective-how-to-write-for-the-web/

Users tend to read in F pattern: 


# Conclusions
Overall, this distinction likely isn't helpful. Because as soon as you add global state to a site, it becomes an app, even if it still feels more like a site (like an e-commerce site). The more useful distinction is web vs native. I suppose it could be helpful, if you think of your product as a site, to limit it from app state for as long as possible. For example, modals are url accessible, all "state" is serialized to the URL. LINK TO APP STATE DOC

Maybe it isn't about a website vs webapp. There are documents (blogs, news, collections like wikipedia, documentation (maybe this is just a collection, too?)) stores, e-commerce, forums, video stores. Where do apps, gmail, gmaps, etc fit in?

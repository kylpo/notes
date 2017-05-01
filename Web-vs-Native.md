
Start with story of always playing the hybrid class: druid. Burned by not ever being the best dmg dealer, tank, healer, etc.

# Web vs Native
- Web is for accessibility, especially PWA (offline)
web is good for _content_
- Maybe it is about leaf nodes? If you have many sub-sites (ecommerce, articles/news), then web is the best platform. You want the one-demand render with reach.
- If you only have a handful of routes, then maybe it is specific enough to warrant Native?
- Will you use this service daily? It should be native.
- Web is good for the "oh, I'm just browsing" user
- Mobile web is good for consumption. Not really good for interaction though.
function over form
- Native gives you immersion
- Think about games, Hangouts, etc. All would be better w/ native controls (like system-wide mic mute, full screen, etc)
- SSR (bummer, wish we could try Preact, but Bing doesn't crawl js)


Web for reach/exposure - Breadth
- web for anything that should/could be viewed anonymously
- does this support the AMP idea?

Native for experience - Depth
- native for anything that would normally require a login

examples to compare with: google plus, inbox, google fonts, mac store

https://medium.com/javascript-scene/native-apps-are-doomed-ac397148a2c0#.pfvxyzxl5

How does this compare to personal blog sites vs using a service like Medium or Twitter? I like being able to like posts now, and dislike when it is a personal site. Universal login is what matters here, I suppose.

---

The web is really good for reading and consumption. The tabs act like physical pages that you can flip through and stack.

An app, on the other hand, is good for experiences. A gameboy, a board game, a set of tools used for a purpose like calculators, journals, timers, etc.

---

https://cloudfour.com/thinks/progressive-web-apps-simply-make-sense/

Progressive Enhancement to consider:
Kind of cool that the browser works as well as it does with progressive enhancement.  Start with the least common denominator of features, then add attributes to your html and js. Amazing that it doesn't break the older browsers - they just ignore what they can't support. Really good model for plugin systems.

Interesting idea to think of web and native apps on opposite spectrums. Web is lowest common denominator and least featured/polish. Native is all about integration and experience. Goal is to move the needle of web as close to your native WITHOUT compromising. This is why perf budgets etc are so important.

Thought about this while reading https://justmarkup.com/log/2016/10/enhancing-a-comment-form/

---

"Native apps like Twitter, Facebook, & Instagram are swell, but appreciate for a moment that the web gives your posts universal addresses."
-https://twitter.com/stshank/status/806981502881759232

Web linkability

I think just about everything should be linkable. For example, a specific comment to an article.

---

"Web users are often action oriented, "leaning forward" in the hunt for answers to their current question, rather than leaning back to absorb a good book."
- https://www.nngroup.com/articles/concise-scannable-and-objective-how-to-write-for-the-web/
-- I wonder if users are more willing to "absorb a good book" when it is a native app?

AMP roadmap update: “You can now also use <amp-app-banner> to drive installs of native apps from AMPs, as well as deep-link directly to native app content for users who have already installed your app”
- https://amphtml.wordpress.com/2016/11/23/amp-roadmap-update-for-mid-q4-2016/


Primarily notes to myself:

https://daverupert.com/2016/10/desktop-is-lava/ had some good points:
🔑 Social networks, search engines, publications, and retailers have already hit the tipping point and are seeing majority mobile traffic. This is probably where your traffic comes from.
🔑 Native App market is tightening. Most people don’t download apps.
👍 Mobile Web traffic is 3x native app traffic.
👍 Mobile Web audiences are growing 2x as fast as app audiences.
👎 Mobile Web engagement (time on site) is 20x less than apps.
👎 Mobile Web engagement is steadily decreasing.
🔑 The Chrome Developers team has been single-mindedly focused on mobile performance lately. This is a huge foreshadowing signal.
👍 Desktop web browsing hasn’t been cannibalized by mobile…
👎 But it has stagnated. comScore reports a 16pt drop in Desktop usage over the last 3 years.

---


# Web
- all about scrolling
  - "scrolling has a special place on the web, and browsers have worked very hard to make sure that scrolling is snappy and responsive" (off-thread scrolling)
  - "The “scroll” event, somewhat counterintuitively, can’t block scrolling because it fires after the scroll event, and thus it isn’t cancelable."
  - [Scrolling on the web: A primer - Microsoft Edge Dev BlogMicrosoft Edge Dev Blog](https://blogs.windows.com/msedgedev/2017/03/08/scrolling-on-the-web/#LG0e2AFJ6auj2GLH.97)
- and about tapping
  - navigate your way by tapping through a journey
- Good for temporal services
- [Jason Miller 🦊⚛ on Twitter: "PWA's don't require new browser features, they leverage them. "Progressive" implies resilience, not dependence."](https://twitter.com/_developit/status/855427754619269124)
  - I think of this as similar to pc games that allow you to dial up/down graphic settings. The game should work with the lowest settings, then ramp up its experience when opted in.

## Cons
- [Think you know the top web browsers? – Samsung Internet Developers – Medium](https://medium.com/samsung-internet-dev/think-you-know-the-top-web-browsers-458a0a070175)
- [Ken Wheeler on Twitter: "Let me be clear: PWAs are awesome & worth doing: ✅ PWAs are as good as native apps: ❌"](https://twitter.com/ken_wheeler/status/854699025928531968) thread basically sums up how I feel
  - ["Wow thats wierd. Its almost like the web isnt that open and a couple large companies call the shots on what you can do."](https://twitter.com/ken_wheeler/status/854787849710862341)
  - ["No PWA ive ever used felt honestly native. Fast load and TTI, sure. But the difference is there."](https://twitter.com/ken_wheeler/status/854782090205908992)
  - ["Animation, interactions, gestures, access to device APIs"](https://twitter.com/ken_wheeler/status/854781562759634944)
  - ["Bring it. Show me your PWA. I'll out load and anim/interaction perf you on it in react native. Without even trying."](https://twitter.com/ken_wheeler/status/854783170406961152)
  - [Like flipboard. They had to reimplement the dom in canvas because it couldnt hit 60fps for a fancy listview"](https://twitter.com/ken_wheeler/status/854863496676343808)
  - [Ken Wheeler on Twitter: "Does PWA stand for Performant Websites for Android?"](https://twitter.com/ken_wheeler/status/854833429946527745)
- [Mark Dalgleish on Twitter: "*Clicks link to article* "Whoa, this site is so clean and easy to read! Loaded super quick too!" ... "Oh, it's a link to the mobile site""](https://twitter.com/markdalgleish/status/854875938932219904)
- [Dan Callahan on Twitter: "AMP requires Google-controlled and Google-hosted JS. Earth requires Chrome. I miss the Google that supported the Web, not subjugated it."](https://twitter.com/callahad/status/854370516353691648)
- [Das Surma on Twitter: "Take a look at https://t.co/Tf6DgrspF6 Do the touch interactions feel like a native app to you? If not: What is breaking the illusion?"](https://twitter.com/DasSurma/status/854820902386647040)
  - so many issues found. Works nicely on first interaction maybe, but then you find the warts quickly after.
- [Ken Wheeler on Twitter: "Gave a talk today about react native where i talked a bunch of shit on the mobile web, slides: https://t.co/pHIBQWr5A4"](https://twitter.com/ken_wheeler/status/854472950388596741)

## Pros
- ["Available anywhere, on-demand, low storage, low power use, etc. These are things both users and companies want from apps. Web nearly there"](https://twitter.com/necolas/status/850437592285708288)
- ["And once the web supports first-class apps, other wins emerge: low running costs (cheaper services, smaller teams) and fast iteration"](https://twitter.com/necolas/status/850439907726114816)
- ["The web seems to be the only app platform that is hyper-focused on making apps smaller and more performant. It's inherent to the platform."](https://twitter.com/polotek/status/850395053935570944)
  - "For any product that is growing and innovating, the apps tend to get more complicated, slower and buggier over time."
  - "That includes web apps. But the web is the only platform that also has counter-pressure, forcing apps to consider bloat a top level issue."
  - "That's a strategic advantage for the web. Twitter was actually incentivized to bring us a better mobile web experience."

# Native
- all about gestures and taps
- 60 fps animations and gestures
- platform features (notifications, OS level hooks)
- amazing for "daily-driver" services. Ones that are used often.
- [Beyond The Browser: From Web Apps To Desktop Apps – Smashing Magazine](https://www.smashingmagazine.com/2017/03/beyond-browser-web-desktop-apps/)
- Why did Universal Windows Apps fail? Because they sucked... They didn't enable enough functionality to warrant building them. Too restrictive, and wasn't compelling over an admittedly limited web platform, but basically the same functionality.
  - Though it may one day get enough bells and whistles to become compelling: [Microsoft is experimenting with tabs in File Explorer and other apps on Windows 10 | Windows Central](http://m.windowscentral.com/windows-10-tabbed-shell)

# Hybrid
- [james kyle on Twitter: "It makes no sense not to build 99% of desktop applications using @electronjs at this point"](https://twitter.com/thejameskyle/status/854530704071286784)
  - has issues (like web) with ram, lost frames, etc
- [Electron is flash for the desktop](https://josephg.com/blog/electron-is-flash-for-the-desktop/)
- [ptmt/react-native-macos: React Native for macOS](https://github.com/ptmt/react-native-macos)
- [jordanIsNotAFunction on Twitter: "Another cool project in conjunction is having a @reasonml native app stack on that WebKit shell, but no JS - native perf - instant startup."](https://twitter.com/jordwalke/status/828336937605828609)

# Current Conclusions
- When to use Web
  - sites (documents, ecommerce)
    - likely came from a google search
  - desktop apps that do not need platform hooks
    - I can't really think of any that fall into this category. Hangouts, for example, will always be inferior to Skype's native app for me because Skype has the picture-in-picture floating window. A tab in a web browser is not likely to get this functionality soon.
  - apps (desktop and web) that are temporal. A user will only occasionally use this service. Example: banking sites.
  - power tabs

- When to use Native
  - Any "daily-driver" service
  - A service that may not be a daily-driver, but is not compelling without the rich gestures and/or platform hooks
  - logged in
- With mobile Safari bringing down the web as a whole, see __this__ link, I currently advize going native on mobile.

# More
- For DEV: Seems like the real bang for your buck is standardizing paradigms like `components`, layouts like `flexbox` (via `yoga`), etc. See [Litho: Creating a custom Button component – Pavlos-Petros Tournaris – Medium](https://medium.com/@p.tournaris/litho-how-to-create-a-custom-button-b460b5a3b828).

# PWA Pros/Cons
Web
- Accessible w/o install -> open, no store
- No storage constraints
- Always up to date
- Already won on desktop
- url/linkable

PWA
- Discoverable by all
- Fast/smooth
- loads quickly
- works offline
- progressively installed

Problems
- integrations (android wear, macOS menu bar)


See also Apps are faltering. But progressive web apps seem pretty legit. – Medium

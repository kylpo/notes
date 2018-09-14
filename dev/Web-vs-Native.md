Web is good for __infrequent__ things. E-commerce, directories, info, etc. Google, gmail, and even Facebook/Twitter make sense as native.

---

The web, to me, is all about content and information.

Thought about Google search being critical. I wouldn't really use google to find an app. I do use it to search web for image and such though.

---

> One camp tells me the current/future is fast devices, crappy network. Build  offline first (bigger JS app).

> Another camp tells me network is fine, devices are slow. Ship less JS, don’t worry about the network, worry about parse/eval time.

> Mutually exclusive optimizations 😐
[Ryan Florence](https://twitter.com/ryanflorence/status/963282206079696896)

---

First of all, I LOVE the web.

I love stumbling on the random forum where total strangers are helping each other. Such an amazing thing.

I really enjoy going down the rabbit hole. I love starting with a question, and taking the journey of cmd-clicking links, and seeing where it goes.

---

Do you ever play a video game long enough to feel like you've completely it without actually getting to the ending? I never finished Final Fantasy 8 or 10. For whatever reason, I just got the point where I was happy with my journey, and emotionally done.

This is how I feel about my journey on the web (for apps).

---

Chrome really is its own OS. Shoved into other OSes. Almost like Flash. Ominously like Flash... *feels hot computer and looks at Activity Monitor*...

---

App ---------------------------------- Site
 |                                       |
Full window                           tab/page

Web advantage: links
- `ctrl click` allows not context switching
- able to queue and batch up work

---

Things I know I prefer as native:
- music player

Things I know I prefer as web:
- feed reader (something that produces more tabs/links (`cmd + click`))

---

Is it OK to live in a sandbox (*app*, whether web or native)? Or does it need hook into the platform it lives on (native *extensions*)?

begs the question: *app* vs *extension*

---

[LukeW | Mobile Web vs. Native Apps or Why You Want Both](https://www.lukew.com/ff/entry.asp?1954)

---

"For ten years now, we've been talking about web apps that "feel native". It has never been true even once, but we just keep repeating it." - [Gary Bernhardt on Twitter: ](https://twitter.com/garybernhardt/status/891434819493666817)
- "There's no reason to suspect that any of this is going to change. It's been like this for as long as I've been any good at computering. Probably because a mixture of (1) many programmers use small subsets of UI capabilities and (2) programmers become ideologically invested."
---

[Kitze on Twitter: "If you do a tl;dr of your workday, but through a user's perspective, you will see how wrong you are about the web progressing fast."](https://twitter.com/thekitze/status/890954201148379136)

---

[Apple’s refusal to support Progressive Web Apps is a detriment to future of the web](https://m.phillydevshop.com/apples-refusal-to-support-progressive-web-apps-is-a-serious-detriment-to-future-of-the-web-e81b2be29676)

---

started from [Lin Clark on Twitter: "Trying to learn more about web app vs. native app tradeoffs. What are your fave links? RTs appreciated"](https://twitter.com/linclark/status/887689585878237184)

[Why “Progressive Web Apps vs. native” is the wrong question to ask](https://medium.com/dev-channel/why-progressive-web-apps-vs-native-is-the-wrong-question-to-ask-fb8555addcbb)

PWAs lack:
- contacts, calendar and browser bookmarks access (though lack of access to these could be viewed as a feature by privacy-conscious users)
- alarms
- telephony features — intercept SMSes or calls, send SMS/MMS, get the user’s phone number, read voice mail, make phone calls without the Dialer dialog
- low-level access to some hardware features and sensors: flashlight, atmospheric pressure sensor
- system access: task management, modifying system settings, logs
- registering to handle custom URL schemes and protocol, or file types


[The surprising tradeoff at the center of the question whether to build a Native or Web App](https://medium.com/@owencm/the-surprising-tradeoff-at-the-center-of-question-whether-to-build-an-native-or-web-app-d2ad00c40fb2)

"@linclark In my experience (built many native and web apps) is: web is cheaper to get started, but native is cheaper to maintain & get to 98%." - [Rasmus Andersson](https://twitter.com/rsms/status/887913115433574400)

---

[What is the best platform: Web or Apps? – Phoomparin Mano – Medium](https://medium.com/@phoomparin/what-is-the-best-platform-web-or-apps-2017-1c6c5ff7cc16) nailed it.
- web for lite, native for full

[Rand Fishkin on Twitter: "REMINDER: Mobile didn't kill desktop; it just killed all our free time. (via https://t.co/LrVP58PU5M) https://t.co/9GRvbUHqF0"](https://twitter.com/randfish/status/870712507916197889)

[Sebastian Markbåge on Twitter: "I think most people don't consider the possibility that Android or UIKit could become a *standard*. #fireandclosethetwitterapp"](https://twitter.com/sebmarkbage/status/870842436494307330)

[Chrome won | Andreas Gal](https://andreasgal.com/2017/05/25/chrome-won/?utm_source=frontendfocus&utm_medium=email)
- basically just Chrome and Safari

Start with story of always playing the hybrid class: druid. Burned by not ever being the best dmg dealer, tank, healer, etc.

Desktop web and Mobile web should probably be in different categories. Salesforce, Google, etc embrace desktop web, but not mobile web.

The realization of web-lite kind of goes counter to Mobile First design. Almost feels like we were led to think that we should build mobile apps on the web because of this Mobile First mantra.

DOM has its issues, but it is an __extensible__ rendering platform. Extensions, user styling, etc.

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

Sites are so amazing for research. Links, headers, cmd-click tabs, etc. We should embrace this!

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
- [Mark Dalgleish on Twitter: "One thing that web apps are wayyy better at that nobody talks about—when you *know* you're looking at stale data, you can just hit refresh."](https://twitter.com/markdalgleish/status/874400896100089856)

"So, web folks, I'm trying to #usetheplatform. But the platform can't smoothly collapse variable length content. Help?"
- https://twitter.com/jamespearce/status/807398999049191425

and [Jed Watson on Twitter: "🤬 I hate it when browsers think they know better than I do, but they don't, and they
won't listen to me\. Safari COMPLETELY breaks react\-select in this example: https://t\.co/i7hEAvWt3f \(try to type
in a field\) Use The Platform they said\. How about don't fuck me,
Platform\."](https://twitter.com/JedWatson/status/954169298280374272)

See also: https://github.com/w3c/csswg-drafts/issues/626

And http://n12v.com/css-transition-to-from-auto/ with the current best practice

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
- [Ken Wheeler on Twitter: "Hey its friday night and the feelings right but dont forget the DOM is a piece of shit and we deserve a better development target"](https://twitter.com/ken_wheeler/status/870812249992122368)
  - DOM just isn't a good app platform. It is a document/site platform!
- [rtorr on Twitter: "I'm glad hacker news is the high bar for modern apps. It looks like it was made in 1993. Platform is ready."](https://twitter.com/richardiii/status/871197129074556928)
- [Mobile Safari (Whyyyy?!) | Engineering Blog](https://www.eventbrite.com/engineering/mobile-safari-why/)
  - no bottom CTAs
- ["The mobile web in 2017"](https://twitter.com/sbholtrop/status/878611398527520768)
  - ![](https://pbs.twimg.com/media/DDF0ZvSXYAI3XGc.jpg)
  - ["Updated: The mobile web in 2017, **now with web fonts!**"](https://twitter.com/markdalgleish/status/879144162389393409)
  - ![](https://pbs.twimg.com/media/DDNYuuVVoAAasvH.jpg)
- [Leland Richardson on Twitter: "randomly looking for some blackjack games on phone and on web... becomes painfully obvious why the web is losing to native mobile"](https://twitter.com/intelligibabble/status/881958748985581568)
- "Is the web ever going to support multiline-text truncation? (Don't @ me about the broken mess that is -webkit-line-clamp)" - [Necolas](https://twitter.com/necolas/status/885150869448085504)
- [Mark Dalgleish on Twitter: "@ryanflorence "Use the platform to display an app install banner""](https://twitter.com/markdalgleish/status/886692085490794496)
- Missing out from recent Android O:
  - Notification Dots
  - Adaptive Icons
  - Notification Channels
  - Shortcuts
  - list from [Android Oreo takes a bite out of Progressive Web Apps](https://medium.com/@firt/android-oreo-takes-a-bite-out-of-progressive-web-apps-30b7e854648f)

## Pros
- ["Available anywhere, on-demand, low storage, low power use, etc. These are things both users and companies want from apps. Web nearly there"](https://twitter.com/necolas/status/850437592285708288)
- ["And once the web supports first-class apps, other wins emerge: low running costs (cheaper services, smaller teams) and fast iteration"](https://twitter.com/necolas/status/850439907726114816)
- ["The web seems to be the only app platform that is hyper-focused on making apps smaller and more performant. It's inherent to the platform."](https://twitter.com/polotek/status/850395053935570944)
  - "For any product that is growing and innovating, the apps tend to get more complicated, slower and buggier over time."
  - "That includes web apps. But the web is the only platform that also has counter-pressure, forcing apps to consider bloat a top level issue."
  - "That's a strategic advantage for the web. Twitter was actually incentivized to bring us a better mobile web experience."
- "The power of the Web is in its universality. Access by everyone regardless of disability is an essential aspect.” — Tim Berners-Lee
- "The "update all the apps" ritual that happens when I plug in my phone at night seems rather archaic in light of what can be done with PWAs." - [Henrik Joreteg on Twitter](https://twitter.com/HenrikJoreteg/status/890094427049472000)
  - "Imagine how much bandwidth must be getting wasted on app updates for apps that will never even be opened again." - [Henrik Joreteg on Twitter](https://twitter.com/HenrikJoreteg/status/890096198740299777)
- Reason to go web: least common denominator

---

> The Web is simultaneously an application platform that blows all other platforms out of the water for delivering content. First, there's a reason why so many native apps embed WebViews -- despite its warts, CSS is the result of hundreds of person-years of tuning for deploying portable textual content.
> But more importantly, you just can't beat the URL. How many more times will we convince the entirety of humanity to know how to visually parse "www.zombo.com" on a billboard or in a text message? It's easy to take the Web for granted, it's fun to snark about its warts, and there's a cottage industry of premature declarations of its death. But I personally believe that the humble little hyperlink is at the heart of the Web's power, competitive strength, and longevity. It was a century-old dream passed on from Vannevar Bush to Doug Englebart to Xerox PARC and ultimately to TBL who made it real.

[Dave Herman on Twitter: "The main reason I care about the Web is because it's the world's biggest software platform that isn't owned\. https://t\.co/czRLdJPQmf"](https://twitter.com/littlecalculist/status/728328046332121089)

---

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
- [Put your Electron app on a diet with Electrino – DailyJS – Medium](https://medium.com/dailyjs/put-your-electron-app-on-a-diet-with-electrino-c7ffdf1d6297)
- [ptmt/react-native-macos: React Native for macOS](https://github.com/ptmt/react-native-macos)
- [jordanIsNotAFunction on Twitter: "Another cool project in conjunction is having a @reasonml native app stack on that WebKit shell, but no JS - native perf - instant startup."](https://twitter.com/jordwalke/status/828336937605828609)
- [Mark Funk on Twitter: "I was really hoping Google would announce a partnership with @github at Google I/O to work on bringing down Electron resource usage."](https://twitter.com/MarkFunk/status/864917340508504064)
- [Sindre Sorhus on Twitter: "Why I chose @electronjs for my Caprine app. https://t.co/KH5GU1PCma https://t.co/tqQzXAJtq0"](https://twitter.com/sindresorhus/status/864887242468335616)
- [Logan Collins on Twitter: "native_apps_are_old_news.gif https://t.co/ifrwNCXEf5"](https://twitter.com/logancollins/status/867022856890142720)
- Figma written in C++ and runs in browser with WebAssembly: [WebAssembly cut Figma’s load time by 3x – Figma Design](https://blog.figma.com/webassembly-cut-figmas-load-time-by-3x-76f3f2395164)
- [Adam Bell on Twitter: "Text editor built using the web™ realizes that DOM is a bottleneck and native code is the best way to render text 🤔 https://t.co/45t2baZxHg"](https://twitter.com/b3ll/status/877957498702921728)
- "Most common anti-pattern among Developers: making choices based on speed of initial development rather than ease of debugging." - [@mikeal](https://twitter.com/mikeal/status/878380425529393152)
  - "Developers spend far more time debugging than on initial development yet consistently optimize the choices of their stack for initial dev."
- [jordanIsNotAFunction on Twitter: "@floydophone @_chenglou Electron apps do embed inside the IDE since they share runtime, but then it ends up like Atom with 4s startup times. Next, you try lazy."](https://twitter.com/jordwalke/status/883819204377325568)
- [Growing Pains: Migrating Slack’s Desktop App to BrowserView](https://slack.engineering/growing-pains-migrating-slacks-desktop-app-to-browserview-2759690d9c7b)
  - [Introducing BrowserView for Electron – Figma Design](https://blog.figma.com/introducing-browserview-for-electron-7b40b4b493d5)

## Good Hybrid examples
- Todoist for MacOS
  - Seems to be a native appwith just a webview and a few custom, native pieces for things like menubar, global hotkeys, quick-add UI.
- Apple's App Store is an interesting example of a hybrid app using webviews.
  - It gives native controls and windowing, but also offers sharing links to content via urls to the site. Without the web portion of this, it'd be way harder to share content and bookmark it for later.

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

Web for your "base". Native to enhance.
- [Nicolas on Twitter: "Ultimately I think PWAs will make native Android apps and desktop wrappers unnecessary for most. Mobile-first PWA as the universal base app"](https://twitter.com/necolas/status/862923667067604992)
- [Paul Lewis on Twitter: "@necolas Agree! I think the key for me is "base": it's a super starting point. If you need to switch up to native, sure, but maybe you won't."](https://twitter.com/aerotwist/status/862926400235462656)

# More
- For DEV: Seems like the real bang for your buck is standardizing paradigms like `components`, layouts like `flexbox` (via `yoga`), etc. See [Litho: Creating a custom Button component – Pavlos-Petros Tournaris – Medium](https://medium.com/@p.tournaris/litho-how-to-create-a-custom-button-b460b5a3b828).

# PWA Pros/Cons
"Progressive Web Apps: Great Experiences Everywhere" is the problem. They aren't great! They're just accessible, and maybe fast.

https://events.google.com/io/schedule/?section=may-17&sid=943de475-c3f2-4069-8d07-435686e6b217

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


See also [Apps are faltering. But progressive web apps seem pretty legit. – Medium](https://medium.com/@cameronmoll/apps-are-dying-2f27baef21dd#.k7dc6wh3j)

[Ken Wheeler on Twitter: "Hey PWA lovers, can you provide me the most native feeling PWA you know of? I need it, for research and shit."](https://twitter.com/ken_wheeler/status/865267013123530752)

[MakeMyTrip.com’s new PWA delivers 3X improvement in conversion rates  |  Web  |  Google Developers](https://developers.google.com/web/showcase/2017/make-my-trip)
- yes, it increases conversion rates __on web__. This is good! It is a better website!

[https://pwa-directory.appspot.com](https://pwa-directory.appspot.com/)

[tastejs/hacker-news-pwas: Hacker News readers as Progressive Web Apps 📱](https://github.com/tastejs/hacker-news-pwas)


[Henrik Joreteg on Twitter: "2 billion active Android devices. Quite a PWA platform."](https://twitter.com/HenrikJoreteg/status/864890889318965248)

[Progressive Web Apps — Yeh or Meh?](http://developer.telerik.com/topics/web-development/progressive-web-apps-yeh-meh/?utm_source=mobilewebweekly&utm_medium=email)

PWA is probably really great for **sites** that would have low app engagement and installs, like Forbes: [Forbes - Redefining Modern Web Development - YouTube](https://www.youtube.com/watch?list=TLGGykzdoCyEWUAxNzA1MjAxNw&v=JmC0xkCMFCE). Should be called a Progressive Web Site, not App.

[Mike Grabowski on Twitter: "Interesting experience, just switched back to Twitter Native from PWA and fonts are much smaller!"](https://twitter.com/grabbou/status/867636983123902467)

PWA with Android Intents: What if you click link twice? Will it open two "apps"?

# STOP
- Stop using titles like [Progressive Web Apps: Great Experiences Everywhere (Google I/O '17) - YouTube](https://www.youtube.com/watch?v=m-sCdS0sQO8)
- [Twitter Lite is a PWA Win - Thurrott.com](https://www.thurrott.com/cloud/116841/twitter-lite-pwa-win)

[(3) Steve Jobs Insult Response - YouTube](https://www.youtube.com/watch?v=FF-tKLISfPE) seems to apply. "You've gotta focus on the customer experience and work backwards to the technology. You can't start with the technology, and figure out where you're going to sell it." Focus on the user's experience. Not the tech, not the engineers. Focus on the cohesive experience as a whole.

[Kent C. Dodds on Twitter: "@satya164 The big question everyone has about not using the DOM for web apps is: Accessibility."](https://twitter.com/kentcdodds/status/865278394354814976)

# Websites that I like
https://www.lily.camera/
- uses native scroller as primary interaction tool
https://www.doubleclickbygoogle.com/articles/mobile-speed-adds-up/
- adapting state of top appbar is just really nice, I think

Long-form learnings:
https://medium.com/retronator-magazine/pixels-and-voxels-the-long-answer-5889ecc18190#.yysvlewsf
- bunch of great, supporting images/videos/gifs



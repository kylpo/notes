# Web
- all about scrolling
  - "scrolling has a special place on the web, and browsers have worked very hard to make sure that scrolling is snappy and responsive" (off-thread scrolling)
  - "The “scroll” event, somewhat counterintuitively, can’t block scrolling because it fires after the scroll event, and thus it isn’t cancelable."
  - [Scrolling on the web: A primer - Microsoft Edge Dev BlogMicrosoft Edge Dev Blog](https://blogs.windows.com/msedgedev/2017/03/08/scrolling-on-the-web/#LG0e2AFJ6auj2GLH.97)
- and about tapping
  - navigate your way by tapping through a journey
- Good for temporal services

## Cons
- [Ken Wheeler on Twitter: "Let me be clear: PWAs are awesome & worth doing: ✅ PWAs are as good as native apps: ❌"](https://twitter.com/ken_wheeler/status/854699025928531968) thread basically sums up how I feel
  - ["Wow thats wierd. Its almost like the web isnt that open and a couple large companies call the shots on what you can do."](https://twitter.com/ken_wheeler/status/854787849710862341)
  - ["No PWA ive ever used felt honestly native. Fast load and TTI, sure. But the difference is there."](https://twitter.com/ken_wheeler/status/854782090205908992)
  - ["Animation, interactions, gestures, access to device APIs"](https://twitter.com/ken_wheeler/status/854781562759634944)
  - ["Bring it. Show me your PWA. I'll out load and anim/interaction perf you on it in react native. Without even trying."](https://twitter.com/ken_wheeler/status/854783170406961152)
  - [Like flipboard. They had to reimplement the dom in canvas because it couldnt hit 60fps for a fancy listview"](https://twitter.com/ken_wheeler/status/854863496676343808)
- [Mark Dalgleish on Twitter: "*Clicks link to article* "Whoa, this site is so clean and easy to read! Loaded super quick too!" ... "Oh, it's a link to the mobile site""](https://twitter.com/markdalgleish/status/854875938932219904)
- [Dan Callahan on Twitter: "AMP requires Google-controlled and Google-hosted JS. Earth requires Chrome. I miss the Google that supported the Web, not subjugated it."](https://twitter.com/callahad/status/854370516353691648)
- [Das Surma on Twitter: "Take a look at https://t.co/Tf6DgrspF6 Do the touch interactions feel like a native app to you? If not: What is breaking the illusion?"](https://twitter.com/DasSurma/status/854820902386647040)
  - so many issues found. Works nicely on first interaction maybe, but then you find the warts quickly after.

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

# Current Conclusions
- When to use Web
  - sites (documents, ecommerce)
    - likely came from a google search
  - desktop apps that do not need platform hooks
    - I can't really think of any that fall into this category. Hangouts, for example, will always be inferior to Skype's native app for me because Skype has the picture-in-picture floating window. A tab in a web browser is not likely to get this functionality soon.
  - apps (desktop and web) that are temporal. A user will only occasionally use this service. Example: banking sites.
- When to use Native
  - Any "daily-driver" service
  - A service that may not be a daily-driver, but is not compelling without the rich gestures and/or platform hooks
- With mobile Safari bringing down the web as a whole, see __this__ link, I currently advize going native on mobile.

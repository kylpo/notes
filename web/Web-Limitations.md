_WIP_

# Transitions/Animations
- growing width/height and adjusting sibling content.
  - seen toggling filters at [apple.com](http://www.apple.com/shop/accessories/all-accessories/whats-new)

# Oddities
- [Show 'Search' button in iPhone/iPad Safari keyboard](http://stackoverflow.com/questions/4864167/show-search-button-in-iphone-ipad-safari-keyboard)
  - must wrap the `<input type='search' />` in a `<form>`
- Unable to prevent user zooming in Safari anymore. The claim is that it helps accessibility, which sounds great, but do they force their native apps to respond this way as well? No? Why!?
  - [New Interaction Behaviors in iOS 10 | WebKit](https://webkit.org/blog/7367/new-interaction-behaviors-in-ios-10/)
- Safari auto zooms-in form `input`s that have font less than 16px
  - [html - Prevent iPhone from zooming form? - Stack Overflow](http://stackoverflow.com/questions/11064237/prevent-iphone-from-zooming-form)

# Ellipsis
Specifically, after X lines

http://caniuse.com/#search=clamp

http://stackoverflow.com/questions/5269713/css-ellipsis-on-second-line
http://cssmojo.com/line-clamp_for_non_webkit-based_browsers/
https://medium.com/mofed/css-line-clamp-the-good-the-bad-and-the-straight-up-broken-865413f16e5#.f3p7l0rjq
https://css-tricks.com/line-clampin/

"The only cross-browser solution is to use js afaik. Several solutions to the problem of multi-line truncation with ellipsis are discussed here: http://css-tricks.com/line-clampin/
I hate them all, but welcome to web development."
http://stackoverflow.com/questions/18763551/clamping-lines-without-webkit-line-clamp

# Transforms affect `position: fixed` children
A transformed element creates a containing block (it also becomes position: relative) for all its positioned descendants, even those that have been set to position: fixed. So, fixed-position children essentially become position: absolute to this continaing block, not the viewport!

http://meyerweb.com/eric/thoughts/2011/09/12/un-fixing-fixed-elements-with-css-transforms/

https://dev.opera.com/articles/css-will-change-property/

# Where Web falls short (and sites that demonstrate it)
Title: The 3 most recent Google web apps prevent mobile - they request native


Dev is all about building on the _platform_ for optimal experience. Native offers so much more as a platform. Maybe web components could close the gap a bit though?


Lacks simple elements like performant accordions: https://shinesolutions.com/2014/03/03/5103/

Sites that are almost good (view these on phone):
http://www.apple.com/macbook-pro/ - does every animation top-down. Very smart.
https://fonts.google.com/ - left nav doesn't lock bg content. Smart to have top bar dropdowns.
https://plus.google.com/ - has locking body when left nav open, but scrolling perf is terrible since it is using a scrolling div, not body scrolling. WHY is this not performant? :(
https://uxplanet.org/mobile-design-best-practices-2d16d37ecfe#.186ilvl8z - nice footer for actions and "open app" cta, but bottom actions require 2 taps in Safari

- totally simple. Optimizing speed, no animations at all.
https://m.facebook.com/home.php
https://mobile.twitter.com

- good accordions
https://store.google.com/product/pixel_phone - uses css-transition
http://www.acnestudios.com/us/en/tinne/1EJ164-Z33.html - js
https://developer.mozilla.org/en-US/docs/Tools/Performance/Scenarios/Animating_CSS_properties - js - LHS has accordions.


- no mobile web presence at all:
https://play.google.com/music/listen?nomobilenative=1#/home
inbox.google.com

Also, throwing in a web app into native doesn't work. See Salesforce 1 reviews: https://play.google.com/store/apps/details?id=com.salesforce.chatter

# Web Problems (as a dev)
## Safari
- 16px inputs
- tapping near bottom will reveal chrome
  - Unable to adopt modern app nav
  - ![](https://pbs.twimg.com/media/C55IvtxVAAApsnm.jpg)
  - Luke Wroblewski on Twitter: "Facebook moves to a bottom navigation bar on Android. ht/ https://t.co/uiWEnt9Lp4 https://t.co/jTEX4iQkss"
- swiping from left, right (back, forward in history), top, bottom, other OS-level elements reveal
- locking scroll for side-navs will scroll body to top
- Had to use scrollTop and element offsetTop instead of getBoundingClient rect for a sticky navbar because Safari would push content down on scroll up when introducing chrome. This messed up the getBoundingClientRect calculation, or something.
- Acting strangely in Safari? Try adding `will-change: transform` to it! The new "did you turn it off and on again?" for web dev :(
- you cannot use 'transparent' in Safari on iOS. You must specify rgba(0,0,0,0) value.
- Safari bug that you experienced. position: absolute went behind position: relative even though absolute had a higher index. The workaround? will-change: transform on the absolute item. BAH!
  - for what gave me the aha! moment https://css-tricks.com/forums/topic/safari-for-ios-z-index-ordering-bug-while-scrolling-a-page-with-a-fixed-element/
## Safari Desktop
- two-finger swipe back shows a Safari page transition. Messes up fadeIn page animations. Different from pressing Back.
## Android
- interactive elements that are close: browser will auto-zoom in
  - https://cloudfour.com/thinks/the-business-case-for-progressive-web-apps/
## All
- Text highlighting different from desktop and mobile (click and hold vs touch and drag)
- Back buttons -> just use browser history
- Accordion Problems
  - https://shinesolutions.com/2014/03/03/5103/
  - good accordions
    - https://store.google.com/product/pixel_phone - uses css-transition
    - http://www.acnestudios.com/us/en/tinne/1EJ164-Z33.html - js
    - https://developer.mozilla.org/en-US/docs/Tools/Performance/Scenarios/Animating_CSS_properties - js - LHS has accordions.
  - "It had difficulties with breaking the back button, in that people couldn’t link directly to content within the accordions. Accordions have a tendency to increase interaction cost - and increase cognitive load. Thus making them a very expensive interface component, and should be used in specific cases with very clear accompanying titles."
  - https://chriswrightdesign.com/experiments/accordion-transitional/

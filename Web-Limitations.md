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

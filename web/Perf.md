# What can we do to lower our JavaScript parse times today?
ship less javascript - this is one argument for using css transitions/animations over including animation libs. The more features used baked in the browser, the better, unfortunately.

thought about while reading https://medium.com/@addyosmani/javascript-start-up-performance-69200f43b201#.6rycp9amd

# Perf considerations
https://twitter.com/jordwalke/status/844854345329926146
^ perf is top priority for WebKit and trumps all. Never regress on perf.

Maybe I should build all products as the `lite` version, first? Then add on polish/animations incrementally to the non-lite site. Always keep lite around for comparison, and users that want it. Lite acts as the master version. Polish is a branch.

[CSS and the First Meaningful Paint - Sessions by Pusher](https://pusher.com/sessions/meetup/london-css/css-and-the-first-meaningful-paint)

[How browsers work](http://taligarsiel.com/Projects/howbrowserswork1.htm)

[Javascript Classes v. Closures (2/3) – Engineering@Livestream – Medium](https://medium.com/engineering-livestream/javascript-classes-v-closures-2-3-9fa3b1296b16)
- use classes over closures. Classes leverage prototypes and sharing methods, which conserves memory usage. Also, classes are better on CPU.

# Tools
## Chrome devtools
- [Performance Analysis Reference  |  Web  |  Google Developers](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)
- [Timeline Profiling with Chrome DevTools — Librato Blog](http://blog.librato.com/posts/chrome-devtools)
  - "Work to the bottom" (of flame charts)
  - "Follow the red" (frames)

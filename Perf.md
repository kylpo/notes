# What can we do to lower our JavaScript parse times today?
ship less javascript - this is one argument for using css transitions/animations over including animation libs. The more features used baked in the browser, the better, unfortunately.

thought about while reading https://medium.com/@addyosmani/javascript-start-up-performance-69200f43b201#.6rycp9amd

# Perf considerations
https://twitter.com/jordwalke/status/844854345329926146
^ perf is top priority for WebKit and trumps all. Never regress on perf.

Maybe I should build all products as the `lite` version, first? Then add on polish/animations incrementally to the non-lite site. Always keep lite around for comparison, and users that want it. Lite acts as the master version. Polish is a branch.
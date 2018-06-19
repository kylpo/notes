[Little UI details from @steveschoger, in HTML and CSS](https://codepen.io/tyrellrummage/pen/ZJPXgy)

[UI Designer Shares His Top Design Tips In Simple Tweets \- UltraLinx](https://theultralinx.com/2018/06/ui-designer-shares-his-top-design-tips-in-simple-tweets/)

https://medium.com/@kollinz/misused-mobile-ux-patterns-84d2b6930570#.9x5etv35u
- don't hide primary navigation
-- see https://medium.com/@kollinz/hamburger-menu-alternatives-for-mobile-navigation-a3a3beb555b8#.ynmeih5d5 for options other than hamburger
- basic functionality can be effectively represented by icons but for complex features, text labels should be used. (And if you use icons, always have them usability tested.)
- empty states

https://medium.com/@kollinz/the-most-underrated-sentence-in-ux-design-d12346c5146b#.vtjfs2e7i
- it is OK to say "I don't know, it depends"

## Always organize elements of information in categories no larger than 9, but preferably ~5 chunks
[The Most Important Rule in UX Design that Everyone Breaks](https://blog.prototypr.io/the-most-important-rule-in-ux-design-that-everyone-breaks-1c1cb188931)

![](https://cdn-images-1.medium.com/max/2000/1*PgZGGwR8UkLPnog2NcyliA@2x.png)

![](https://cdn-images-1.medium.com/max/2000/1*n5o78Gu9qEh4J2ui2GY4Ig@2x.png)

## Infinite Scrolling
http://www.webdesignerdepot.com/2014/04/how-to-use-the-infinite-scrolling-trend-the-right-way/

Back button needs to work. When navigating away from infinite list, pressing back should not send the user all the way to the top.

Footers should not be used if infinite scroll is enabled.

Give visual indication of loading more content.

Most product sites prefer pagination.

Infinite scroll works well for feed content like Facebook, Twitter, etc.

Use react-virtual to load out content above viewport, or else scrolling will slow down from all the non-visible nodes in the dom.

## Mobile
One Screen, One Task
https://uxplanet.org/mobile-design-best-practices-2d16d37ecfe#.iw9bg1oxl

Fill the Screen
Be Pixel Perfect
Slide and Stretch
https://medium.com/outsystems-experts/10-rules-for-creating-a-mobile-look-and-feel-dc81341660e4#.lz09cyoil


## Text
optimize text for reading
"Classic readability theory suggests that an ideal column should contain 70 to 80 characters per line (about 8 to 10 words in English). Thus, each time the width of a text block grows past about 10 words, consider adding a breakpoint."
https://developers.google.com/web/fundamentals/design-and-ui/responsive/

# Notification Considerations
Jeez, I installed the @Medium app and now I get like 5 push notifications per day about stories published. Like the boy who cried wolf!
- https://twitter.com/spikebrehm/status/877579699576217600

# Relative values where possible
So much more useful to see "6 degrees warmer than yesterday" for the weather forecast

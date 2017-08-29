
[Web Font Optimization  \|  Web  \|  Google Developers](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/webfont-optimization#webfonts_and_the_critical_rendering_path)

[The Critical Request | CSS-Tricks](https://css-tricks.com/the-critical-request/)

"I'd suggest using `font-display: swap;`, which will show the fallback font until the web font has loaded—at which point it'll be replaced."

[If you really dislike FOUT, \`font\-display: optional\` might be your jam \| CSS\-Tricks](https://css-tricks.com/really-dislike-fout-font-display-optional-might-jam/)

---

[Addy Osmani on Twitter: "Use Web Fonts? Have a solid font loading strategy to deliver the best user experience 🔥 https://t.co/7HThUtp0AZ https://t.co/n7pxwLdNzP https://t.co/fHahqqfcRA"](https://twitter.com/addyosmani/status/883002839995301888)

![](https://pbs.twimg.com/media/DEEKLTlUQAAFdyo.jpg)


# Decisions to make

rem, em, px

https://www.youtube.com/watch?v=XanhwddQ-PM&index=35&list=WL
https://mindtheshift.wordpress.com/2015/04/02/r-i-p-rem-viva-css-reference-pixel/

lineheight
(Ignatius comment in) https://css-tricks.com/almanac/properties/l/line-height/
https://developer.mozilla.org/en-US/docs/Web/CSS/line-height




Always consider line-height for wrapping text. All other vertical spacing is just margin/padding.

Thomas's problematic example of having 0 lineheight on desktop, then when sizing it down to mobile, it wraps without and spacing.



# Custom Web Fonts

[Web fonts: when you need them, when you don’t – Hacker Noon](https://hackernoon.com/web-fonts-when-you-need-them-when-you-dont-a3b4b39fe0ae)

[A Comprehensive Guide to Font Loading Strategies—zachleat.com](https://www.zachleat.com/web/comprehensive-webfonts/#font-display)

"🚨 NOT A DRILL 🚨 `font-display` is available on now-stable Chrome 60! CSS-only FOUT is here!! Read more: https://t.co/cMASBYtzOH https://t.co/Y3GFIfrYmy" - [Zach Leatherman on Twitter](https://twitter.com/zachleat/status/890242957386944516)

Declaring the webfont as first in family will cause a FOIT (Flash of invisible text) while the client downloads your font. How to fix this? Lazy load your font, then apply a css class to your html to use the newly downloaded font-family.

The invisible content flash is fixed, but now there is a flash of unstyled text (FOUT). How to fix this? Well, you can't really fix it, since you want your readers to view content asap. You can however lessen the effect of text shifting when your primary font has loaded by setting the secondary font to one that matches the character height and width. The font will change, but the content won't shift much, and should appear as an enhancement.

You can go further though. FOFT (Flash of faux text) will load ONLY the roman/normal font first, apply it, then download the bold, italic, and bold italic and apply them - reducing the time of FOUT.

Resiliency: if your font downloads timeout for whatever reason, no worries - your content still loads.

Great talk on this: https://www.youtube.com/watch?v=emLfXChvVPQ&list=WL&index=26

https://meowni.ca/font-style-matcher/ for helping choose FOUT style
https://twitter.com/notwaldorf/status/801138269719171073

Bricolage | Typefaces: The easiest way to self-host open-source fonts
Self hosting more performant than google fonts? And offline-capable.

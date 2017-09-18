
---

# Ads too far
Wow, I never really thought ads were a problem until I saw this page: https://www.phonearena.com/news/How-to-run-several-apps-in-floating-windows-in-Android-7.0-Nougat-no-root_id84549. This, is terrible, and not something I want to support.

---

Ads are so bad now. It makes me an AMP believer.

http://www.zdnet.com/article/amazon-jumps-on-kubernetes-bandwagon/?utm_source=webopsweekly&utm_medium=email had an auto-playing video with sound. WTF!???

---

- [Malte Ubl @ #io17 on Twitter: "Yesterday at #io17 we announced we’re rolling out a change that reduces time to 1st contentful paint across the 2 billion+ AMP pages by ~50%"](https://twitter.com/cramforce/status/865205023495421952)
- [Jason Miller 🦊⚛ on Twitter: "thing people don't realize when bashing amp: anyone can embed, not just google search. eg: twitter, facebook"](https://twitter.com/_developit/status/866307005790773248)
- [What Google AMP means for the JavaScript community · molily](https://molily.de/amp/)
- [amphtml/getting-started-e2e.md at master · ampproject/amphtml](https://github.com/ampproject/amphtml/blob/master/contributing/getting-started-e2e.md#building-amp-and-starting-a-local-server)
- [I decided to disable AMP on my site](https://www.alexkras.com/i-decided-to-disable-amp-on-my-site/)
- [Content Performance Policy, an alternative to AMP?](https://dev.to/damienjubeau/content-performance-policy-an-alternative-to-amp?utm_source=mobilewebweekly&utm_medium=email)
- [The bloat of AMP](https://lolware.net/2017/07/04/amp-bloat.html)
- [Should I implement AMP? 5 meaningless, not proven or misleading assumptions that may lead you to the wrong decision - Blog de Christian Oliveira](https://www.christianoliveira.com/blog/en/web-analytics/should-i-implement-amp/)
- [AMP Project on Twitter: "Meet the⚡️ ShadowReader, a production-ready PWA+AMP sample that uses real data from @guardian. Learn all about it 👇 https://t.co/jpPEPXLWLZ"](https://twitter.com/AMPhtml/status/888181282168946688)

---

[Google Featured Snippets On Mobile Now Serve AMP Content](https://www.seroundtable.com/google-featured-snippets-on-mobile-amp-24401.html#ampshare=https://www.seroundtable.com/google-featured-snippets-on-mobile-amp-24401.html)

![](https://s3.amazonaws.com/images.seroundtable.com/google-featured-snippet-amp-1504526687.jpg)

---

## Against it
- [One Month Without AMP](https://www.alexkras.com/one-month-without-amp/)
> Unless you run a News site that HAS to compete for a spot in Google Carousel enabling AMP is not worth the effort. AMP is an alternative publishing format and most small site can’t afford to maintain two (quality) versions of itself.
- [Using Google AMP for e\-commerce might not be the best choice currently](https://thirtybees.com/blog/amp-is-bad-for-e-commerce/)
- [AMPersand\. — Ethan Marcotte](https://ethanmarcotte.com/wrote/ampersand/?utm_source=mobilewebweekly&utm_medium=email)
  - Publishers use AMP not because it is faster, but because they need to live in the Google search result carousels.

## Using it


## Removing it
- [Remove AMP Content from Google Search  |  Google Developers](https://developers.google.com/search/docs/guides/remove-amp)

---

AMP has already won. This screenshot taken from my Google Feed in July 2017.

![](https://github.com/kylpo/notes/blob/master/assets/AMP-won.png?raw=true)

---

![](https://github.com/kylpo/notes/blob/master/assets/the-fold.png?raw=true)

And by creating this strict, statically laid out environment, it enables platforms such as Google Search to get one step closer to “instant” by preloading just the first viewport.

https://www.smashingmagazine.com/2016/12/progressive-web-amps/

To make the experience reliably fast, you need to live with some constraints when implementing AMP pages. AMP isn’t useful when you need highly dynamic functionality, such as Push Notifications or Web Payments, or really anything requiring additional JavaScript. In addition, since AMP pages are usually served from an AMP Cache, you won’t get the biggest Progressive Web App benefits on that first click, since your own Service Worker can’t run. On the other hand, a Progressive Web App can never be as fast as AMP on that first click, as platforms can safely and cheaply prerender AMP pages – a feature that also makes embedding simpler (e.g. into an inline viewer).



https://ampbyexample.com/#components

https://choumx.github.io/amp-pwa

Interesting that the AMP dev advocate is the creator of jQuery UI: Paul Bakaus. Wonder if he was frustrated with trying to make web more app-like and just settled on how I am currently thinking the web should act.

---
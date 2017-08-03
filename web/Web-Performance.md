_WIP_

[The Critical Request | CSS-Tricks](https://css-tricks.com/the-critical-request/)

---

"If you can't measure it, you can't improve it."

[Siddharth Kshetrapal on Twitter: "1/ Here are the resources from my talk on web performance @js_channel https://t.co/yZTWRB9tAS"](https://twitter.com/siddharthkp/status/890845810748817408)

[Siddharth Kshetrapal on Twitter: "14/ Performance tip #4: Eagerly fetch and cache resources for the next step in the user journey using service workers. https://t.co/1VMCECtKeB"](https://twitter.com/siddharthkp/status/890846397708115968)

[Siddharth Kshetrapal on Twitter: "17/ Use bundlesize and put your javascript on a diet. https://t.co/Rov9JvfHZ5 https://t.co/qyht6vmnzg"](https://twitter.com/siddharthkp/status/890846559918735360)

[Siddharth Kshetrapal on Twitter: "18/ Use perfbench to automate performance audits on every pull request before merging. https://t.co/7gFjbKdFHR https://t.co/mq9zerxuIQ"](https://twitter.com/siddharthkp/status/890846587768807424)

---

Some of my notes: https://drive.google.com/open?id=0B25-OD6y7G4ZOXhrNXFnYjdhSFk

[Kent C. Dodds on Twitter: "Oh snap, look at what babel-plugin-preval has done 😱 https://t.co/4Jpx0UT2qg https://t.co/DCi2zIYK9o"](https://twitter.com/kentcdodds/status/885951024174780416)

![](https://pbs.twimg.com/media/DEuH9sxUwAAGA6u.jpg:large)

---

[Addy Osmani on Twitter](https://twitter.com/addyosmani/status/886169338671112192)

1. Keep your JS small & fast
2. Lazy-load non-critical assets
3. Preload late-discovered resources
4. Optimize Web Fonts
5. Compress images

[Leveraging the Performance Metrics that Most Affect User Experience  |  Web  |  Google Developers](https://developers.google.com/web/updates/2017/06/user-centric-performance-metrics)

# Good reads
- [Twitter Lite and High Performance React Progressive Web Apps at Scale](https://medium.com/@paularmstrong/twitter-lite-and-high-performance-react-progressive-web-apps-at-scale-d28a00e780a3)

# Perf
## div depth does matter
1000s deep will hurt, as mentioned in this [tweet thread](https://twitter.com/owencm/status/847529975615864832)

## Images
- Even full loaded images can cause jank. When we had retina desktop images loaded on mobile, anchor scrolling and carousel scrolling were janky. Reducing image size was the fix.


# Micro-Perf
## Explicit comparisons
```js
if (obj !== undefined) { return obj.x; }
```
15% faster than
```js
if (obj) { return obj.x; }
```
### Ref
- [TurboFan: A new code generation architecture for V8 - Google Slides](https://docs.google.com/presentation/d/1_eLlVzcj94_G4r9j9d_Lj5HRKFnq6jgpuPJtnmIBs88/edit#slide=id.g2134da681e_0_596)

## Only use `||` and `&&` in a boolean context. Else use a ternary.
- From [@bmeurer](https://github.com/developit/preact/pull/610#issuecomment-289981990)
> In general using && or || in a non-boolean context - especially with numbers - is not ideal, because of the semantics of && and || in JavaScript. For example: `let len = o && o.length;` Here `len` can have either the value of o if `ToBoolean(o)` yields `false`, or the value of length property of o. If len is used as a number, then this will prevent the compiler from picking an ideal representation for len, and requires another (expensive) check later to figure out that len is actually a number.

- From [@developit](https://github.com/developit/preact/pull/610#issuecomment-290081189)
> using a ternary seems to avoid an unintentionally different type for falsey conditions - seems like that's the kicker here? (the goal being to have the expression produce a uniform type)

- Current question: what if the default value of a ternary is `undefined` or `null`? Does it suffer from the same perf issue as `something && something.somethingElse`?
  - e.g. Would an `undefined` default (e.g.`vlen = vchildren ? vchildren.length : undefined`) be less optimal for the compiler than the default of `0`? Same question for `null`.
  - "`undefined` or `null` are less ideal than 0 here, as the compiler needs to choose a tagged representation that can represents both `undefined`/`null` as well as numbers. If you use only (small integer) numbers, then the optimizing compilers in VMs can usually pick the ideal unboxed Word/Word32 representation." - [@bmeurer](https://github.com/developit/preact/pull/610#discussion_r108732513)

# Trivia
## Is `something == null` as performant as `something === null || something === undefined`?
Yes, actually. See https://jsperf.com/null-null-vs-null-null/1.

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


IRHydra
http://mrale.ph/blog/2014/01/28/prerelease-irhydra2.html
https://gist.github.com/developit/64027410b3a09d2eca72d73b0a392b08#

---

position: fixed; has performance issues. Expensive to paint. Can fix with gpu using will-change of anything (like will-change: transform).

---

When debugging web performance, turn on Flash Paint, see if repainting is a problem. If so, start at the top of the DOM, <head> even, and start deleting stuff to identify what the problem is.

---

FB perf talk

100s of ms of pageload time is spent parsing the html, js, and css

20% of requests for static resources are unnecessary revalidation due to reload
opening a new tab takes ~200ms

https://atscaleconference.com/videos/web-speed-at-facebook/

---

caching (server and http headers) https://varvy.com/pagespeed/leverage-browser-caching.html

---

someday, go through High Performance Browser Networking https://hpbn.co/

---

Flexbox perf

More performant than floats: https://developers.google.com/web/fundamentals/performance/rendering/avoid-large-complex-layouts-and-layout-thrashing

---

The Frame pipeline

The process that the browser goes through is pretty simple: calculate the styles that apply to the elements (Recalculate Style), generate the geometry and position for each element (Layout), fill out the pixels for each element into layers (Paint Setup and Paint) and draw the layers out to screen (Composite Layers).

To achieve silky smooth animations you need to avoid work, and the best way to do that is to only change properties that affect compositing -- transform and opacity. The higher up you start on the timeline waterfall the more work the browser has to do to get pixels on to the screen.

https://www.html5rocks.com/en/tutorials/speed/high-performance-animations/devtools-waterfall.jpg

also https://developers.google.com/web/fundamentals/performance/rendering/

---

As JS can trigger every part of the rendering pipeline, it makes sense to run it as early as possible each frame.

raf enables you to schedule your js to be run as early as possible in the frame. that way, the rest of the pipeline can run after it (style, layout, paint, composite). To fit into 16ms, shoot for js that runs in 3-4ms.

---

Avoid style changes in input handlers

Input handlers, like those for scroll and touch, are scheduled to run just before any requestAnimationFrame callbacks.

![](https://github.com/kylpo/notes/blob/master/assets/reflow.png?raw=true)

If you make a visual change inside one of those handlers, then at the start of the requestAnimationFrame, there will be style changes pending. If you then read visual properties at the start of the requestAnimationFrame callback, as the advice in “Avoid large, complex layouts and layout thrashing” suggests, you will trigger a forced synchronous layout!



https://developers.google.com/web/fundamentals/performance/rendering/debounce-your-input-handlers

---

offsetTop forces layout?

https://developers.google.com/web/tools/chrome-devtools/rendering-tools/forced-synchronous-layouts is an interactive tutorial to show how forced synchronouse layouts are a problem.

Others: http://gent.ilcore.com/2011/03/how-not-to-trigger-layout-in-webkit.html

https://gist.github.com/paulirish/5d52fb081b3570c81e3a

"The handler computes the image's left CSS style proeprty on the the image's offsetTop value. This forces Chrome to perform a new layout immediately to make sure it provides the correct value." from https://developer.chrome.com/devtools/docs/demos/too-much-layout


---

What is Layout Thrashing?

http://wilsonpage.co.uk/preventing-layout-thrashing/

Layout Thrashing occurs when JavaScript violently writes, then reads, from the DOM, multiple times causing document reflows.

// Read
var h1 = element1.clientHeight;


// Write (invalidates layout)
element1.style.height = (h1 * 2) + 'px';


// Read (triggers layout)
var h2 = element2.clientHeight;


// Write (invalidates layout)
element2.style.height = (h2 * 2) + 'px';


How to fix it?
Ideally, you'd make all your reads at once, then all your writes

// Read
var h1 = element1.clientHeight;
var h2 = element2.clientHeight;
var h3 = element3.clientHeight;


// Write (invalidates layout)
element1.style.height = (h1 * 2) + 'px';
element2.style.height = (h2 * 2) + 'px';
element3.style.height = (h3 * 2) + 'px';


// Document reflows at end of frame


But that isn't realistic, so use raf

// Read
var h1 = element1.clientHeight;


// Write
requestAnimationFrame(function() {
  element1.style.height = (h1 * 2) + 'px';
});


// Read
var h2 = element2.clientHeight;


// Write
requestAnimationFrame(function() {
  element2.style.height = (h2 * 2) + 'px';
});


That still isn't controlled enough - other things might be reading/writing, and you may want to perform a read after a write to affect a write after. This is why virtual doms are so powerful. They batch and optimize everything for you.

---

Reflow

A reflow is even more critical to performance because it involves changes that affect the layout of a portion of the page (or the whole page). Reflow of an element causes the subsequent reflow of all child and ancestor elements as well as any elements following it in the DOM.

What causes a reflow?
Resizing the window.
Changing the font.
Adding or removing a stylesheet.
Content changes, such as a user typing text in an input box.
Activation of CSS pseudo classes such as :hover (in IE the activation of the pseudo class of a sibling)
Manipulating the class attribute.
A script manipulating the DOM.
Calculating offsetWidth and offsetHeight.
Setting a property of the style attribute


---

Paint complexity

When it comes to painting, some things are more expensive than others. For example, anything that involves a blur (like a shadow, for example) is going to take longer to paint than -- say -- drawing a red box. In terms of CSS, however, this isn’t always obvious: background: red; and box-shadow: 0, 4px, 4px, rgba(0,0,0,0.5); don’t necessarily look like they have vastly different performance characteristics, but they do.

https://developers.google.com/web/fundamentals/performance/rendering/simplify-paint-complexity-and-reduce-paint-areas

---

When is js animation faster than css transition?

"A large amount of this comes down to exactly which properties are being animated. If an element’s animation requires layout (width, height, top, left) then you are often better animating via a requestAnimationFrame on the main thread. The alternative is to use a CSS transition / animation, but the problem here is that those are often started on a separate thread — the compositor — so you end up doing a hop from the compositor (CSS anim) to main thread (to do layout) and then back again (because the compositor runs the final composition of the page). This is less advantageous than simply main to compositor, which is what a rAF-based animation will give you.


If, however, you are animating transforms or opacity (as two examples) then those operations can be carried out by the compositor alone, and that gives you two benefits: 1) the browser can do main thread work *while* your animation is handled on the compositor and 2) you avoid two thread hops.


It’s very tempting to say CSS is faster than JS or vice versa, but the truth is much more nuanced and can change depending on which browser you’re talking about and what architecture it sports. My advice is always the same: profile your options (tools, not rules) and then choose the right approach." - https://davidwalsh.name/css-js-animation  - comment from Paul


See also:
http://blogs.adobe.com/webplatform/2014/03/18/css-animations-and-transitions-performance/

---

Modern web browsers can take advantage of the GPU (graphics processing unit) to accelerate page rendering. Among many different features of a GPU, it can hold a limited number of textures (a rectangle of pixels) and manipulate those textures efficiently, including applying a certain transformation (translation, scaling, rotating, etc). This is extremely useful to achieve a fluid animation. Instead of drawing the pixels for every animation frame, the browser will “snapshot” the DOM element and store it as a GPU texture (often called as layer). Later, the browser will simply tell the GPU to transform the said texture to give the perception of an animating DOM element. This is called GPU compositing, naturally referred to as “hardware acceleration”.

http://calendar.perfplanet.com/2014/hardware-accelerated-css-the-nice-vs-the-naughty/

---

Browser paint renders border before painting text.


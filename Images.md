_WIP_

Images on the web are hard. Straight up. You need to make many decisions, it is so much more work than "just throw an image in".

[High Performance Images - By O'Reilly & Akamai](https://www.youtube.com/watch?v=UlrHvF_J-oI) is a good 1 minute video intro to some challenges.

Here are the major decisions you'll need to make
- What type is it?
- What should load?
- When should it load?
- How should it load?
- How should it respond to viewport changes?

## What type is it?
In the wonderful DX world of React Native, we need only reach for one tool: `<Image>`. But on the web, we have more to choose from: `<img>`, `<picture>`, and `background-image` of a `<div>`.

So, which one should we use? Well, let me answer this question with a question. Is the image *content*?

If it is something that you'd like indexed by SEO, and visible if a user printed the page, then it is content. Often these images are stand-alone, like logos, images of a product on an e-commerce site, and images in a blog post, for example. This is the world of `<img>`s and `<picture>`s. Exactly which of these two you'll use is decided in a future question.

If it is there to *enhance the display* of other content, like the background image of a header, then it is likely in the world of `<div>`s with `background-image` styles.

Note: this writeup will not cover `svg` and icons. I think it is different enough to break out into its own.

TODO: example picture with the two

I actually can't think of a case where I've put content on top of content images, so maybe it'd be easier to think of the separation as background vs foreground/content images.

TODO: image of decision tree





## What should load?
When a user loads your page, what should they see? Well, your image, right? Yes, but its not that easy.

### Responsive
If you serve a desktop sized retina image to a mobile user, you negatively affect TTI ([Time To Interactive](https://developers.google.com/web/tools/lighthouse/audits/time-to-interactive)) and scroll performance. On the other hand, if you serve your small mobile image to a 4k desktop user, s/he will surely insta-close that tab. So, we want to serve the smallest possible image that still looks good on the user's display. This is what is known as a *Responsive* or *ResponsiveLoad* Image.

To accomplish this, we'll need to do two things:

1: Create all permutations of image resolutions that you'll potentially serve
2: Tell the browser which permutation to load, and when

The first is either a lot of manual work in exporting, a decent amount of work in setting up a build process to auto-generate these, or a small amount of work and a little bit of money to have a 3rd part service do this work for you. More on this in the Tooling section

The second step depends on the type of image:
- Content -> use `srcset` of an `<img>` tag
  - [Harry Roberts on Twitter: "The simplest way I’ve found (so far) to distill/explain `srcset` and `sizes`"](https://twitter.com/csswizardry/status/836960832789565440)
  - ![](https://pbs.twimg.com/media/C517RYNWgAEqwy5.jpg)
  - [Responsive Images: If you're just changing resolutions, use srcset. | CSS-Tricks](https://css-tricks.com/responsive-images-youre-just-changing-resolutions-use-srcset/)
  - [The anatomy of responsive images - JakeArchibald.com](https://jakearchibald.com/2015/anatomy-of-responsive-images/)
- Style -> either use `@media` queries, or `image-set` if you aren't worried about the browsers lacking the feature
  - See [Responsive Images in CSS | CSS-Tricks](https://css-tricks.com/responsive-images-css/)

### Art Direction
What about going further than just resizing the same image depending on the viewport size? Maybe in a small viewport, you'd like to crop the image to zoom in and focus a specific part of it. Or perhaps you'd like a totally different image. This is *Art Direction*, and to accomplish it, we'll reach for the `<picture>` element for content, and `@media` queries for style.

```html
<picture>
   <source media="(min-width: 36em)"
      srcset="large.jpg  1024w,
         medium.jpg 640w,
         small.jpg  320w"
      sizes="33.3vw" />
   <source srcset="cropped-large.jpg 2x,
         cropped-small.jpg 1x" />
   <img src="small.jpg" alt="A rad wolf" />
</picture>
```
from [Responsive Images Done Right: A Guide To And srcset](https://www.smashingmagazine.com/2014/05/responsive-images-done-right-guide-picture-srcset/)

TODO: image of decision tree





## When should it load?
When a user visits your page, every single image is requested from a server (or local cache), then rendered on the page. It slows down TTI, but there is a solve for this.

### Lazy Loading
"Lazy loading can significantly speed up loading on long pages that include many images *below the fold* by loading them either as needed or when the primary content has finished loading and rendering. In addition to performance improvements, using lazy loading can create infinite scrolling experiences."
- [Images | Web | Google Developers](https://developers.google.com/web/fundamentals/design-and-ui/responsive/images)

Lazy Load monitors scroll position to load in images based on their proximity to the viewport

### Deferred Loading
- Deferred will load every non-main image (usually below the fold) after page load
  - Necessary for those long, anchor-linked, single page sites
  - [Defer images without jQuery or lazy loading](https://varvy.com/pagespeed/defer-images.html)
    - ![](https://varvy.com/pagespeed/images/pageload.png)
    - ![](https://varvy.com/pagespeed/images/pageload-defer.png)

### Strategies
`lazySizes` plugins show how complicated this feature can be: https://github.com/aFarkas/lazysizes#available-plugins-in-this-repo

- [Building a Media Player #9: Lazy-Loading Images - YouTube](https://www.youtube.com/watch?v=ncYQkOrKTaI&feature=youtu.be)
  - uses `IntersectionObserver` instead of listening to `scroll`
- [Simple Image Lazy Load and Fade](https://davidwalsh.name/lazyload-image-fade)
- [lazysizes: High performance and SEO friendly lazy loader for images (responsive and normal), iframes and more, that detects any visibility changes triggered through user interaction, CSS or JavaScript without configuration.](https://github.com/aFarkas/lazysizes)
- [Building a high performance lazy load module – Front-end architecture by Robert Smith](http://rbrtsmith.com/2015/02/building-a-high-performance-lazy-load-module)
  - "Initially this sounds very simple, on page-load we can just grab the offsetTop of the images and store the values in the array, but upon further investigation this presents a problem. When we scroll to an image and it loads in, it pushes the content below further down the page, rendering the remaning offset values invalid. ... One benefit I forgot to mention of the placeholder is that once the image loads the page will not have to be repainted unlike before because the placeholder already takes up that space so another +1 for the performance"

### Considerations/Hurdles
#### Relies on Javascript
"What would happen if JavaScript failed or didn't load for whatever reason? (connectivity problems, bad 3G, JavaScript-blockers, third-party scripts fail... you name it)"

"In that case you need to use the noscript tag. Your final markup should look like:"

```jsx
<img class="lazy" data-original="image-src.jpg" width="1200" height="600">
<noscript>
    <img src="image-src.jpg" width="1200" height="600">
</noscript>
```
from comments section of https://www.sitepoint.com/lazy-loading-images-not-really-annoy-users/

Posts like http://dinbror.dk/blog/lazy-load-images-seo-problem/ argue that noscript is no longer needed, but bing was not able to index the images, so we're not totally there yet
#### SEO

#### Content jumping as images load in
padding-bottom https://www.smashingmagazine.com/2013/09/responsive-images-performance-problem-case-study/
The lazyload_images filter defers loading of images until they become visible in the client's viewport or the page's onload event fires. This avoids blocking the download of other critical resources necessary for rendering the above the fold section of the page.

- https://developers.google.com/speed/pagespeed/module/filter-lazyload-images





## How should it load?
ProgressiveLoad -> load blurry LQIP (Low Quality Image Placeholder), then full

In the browser if you don't give a size to an image, the browser is going to render a 0x0 element, download the image, and then render the image based with the correct size. The big issue with this behavior is that your UI is going to jump all around as images load, this makes for a very bad user experience.





## How should it respond to viewport changes?
How to fill the entire page with an image, no white space, scales as needed, retains aspect ratio, and centered?

```
html {
  background: url(images/bg.jpg) no-repeat center center fixed;
  background-size: cover;
}
```

or use `background-image: url(_)`

https://facebook.github.io/react-native/docs/pixelratio.html

Aspect ratio controls the size of the undefined dimension of a node.
- https://facebook.github.io/react-native/docs/layout-props.html#aspectratio





## Performance considerations
Image decoding can take more than a frame-worth of time. This is one of the major sources of frame drops on the web because decoding is done in the main thread. In React Native, image decoding is done in a different thread. In practice, you already need to handle the case when the image is not downloaded yet, so displaying the placeholder for a few more frames while it is decoding does not require any code change.
https://facebook.github.io/react-native/docs/images.html

Even full loaded images can cause jank. When we had retina desktop images loaded on mobile, anchor scrolling and carousel scrolling were janky. Reducing image size was the fix.

Also see Image section of https://medium.com/@paularmstrong/twitter-lite-and-high-performance-react-progressive-web-apps-at-scale-d28a00e780a3

`sizes` is like the upfront, static form of react router. Pre-parser needs it to optimize performance, but it's a bummer. You'd rather just say that the responsive image is here, not find the right size to load (like RR v4).

### Format and Compression
#### Which format to use?
- [Transparent JPG (With SVG) | CSS-Tricks](https://css-tricks.com/transparent-jpg-svg/)
- webp, transparent png, Progressive JPEG
- [Saving Bandwidth by Using Images the Smart Way — SitePoint](https://www.sitepoint.com/saving-bandwidth-by-using-images-the-smart-way/)
- [Performance Calendar » Squeezing PNG Images](https://calendar.perfplanet.com/2016/squeezing-png-images/)
- [Image Optimization | Web | Google Developers](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization#image-optimization-checklist)

#### How to deliver it?
```html
<picture>
  <source type="image/webp" srcset="snow.webp"/>
  <img alt="Hut in the snow" src="snow.jpg"/>
</picture>
```
from [The anatomy of responsive images - JakeArchibald.com](https://jakearchibald.com/2015/anatomy-of-responsive-images/) will deliver the `webp` if it is supported by the browser. Else it'll fall back to the `<img>`'s `jpg`.

### IMG Sprites
instead of loading multiple small images, consider spriting (single image with coordinates)

### Server considerations
- [Performance Calendar » Even Faster Images using HTTP2 and Progressive JPEGs](https://calendar.perfplanet.com/2016/even-faster-images-using-http2-and-progressive-jpegs/)





## Automation
- Build time solutions (great for a limited amount of images, but does not scale)
  - generate responsive permutations: [responsive-loader: A webpack loader for responsive images](https://github.com/herrstucki/responsive-loader)
  - compression: [image-webpack-loader: Image loader module for webpack](https://github.com/tcoopman/image-webpack-loader)
  - image sprite generation: [webpack-spritesmith: Webpack plugin that converts set of images into a spritesheet and SASS/LESS/Stylus mixins](https://github.com/mixtur/webpack-spritesmith)
- Separate process/task from the usual build
  - responsive and compression: [Performance Calendar » Image Optimization](https://calendar.perfplanet.com/2016/image-optimization/) - see the "Automating the asset creation process" section.
  - image sprite generation: [gulp.spritesmith: Convert a set of images into a spritesheet and CSS variables via gulp](https://github.com/twolfson/gulp.spritesmith)
- 3rd party services
  - [Cloudinary - Cloud image service, upload, storage & CDN](http://cloudinary.com/)
  - [Let The Content Delivery Network Optimize Your Images – Smashing Magazine](https://www.smashingmagazine.com/2017/04/content-delivery-network-optimize-images/)





## Concepts/Terms we learned
- Responsive -> send the smallest asset for the screen that still looks good
- Art Direction -> more than just resizing, it is cropping (or replacing) for specific viewports
- Lazy Loading -> defer loading until last possible moment to speed up TTI
- Deferred Loading ->
- ProgressiveLoad -> load blurry LQIP (Low Quality Image Placeholder), then full





## References
- [Images | Web | Google Developers](https://developers.google.com/web/fundamentals/design-and-ui/responsive/images) good overview of many of these topics
- [An Event Apart News: Responsive Images Are Here. Now What? by Jason Grigsby—An Event Apart video](https://aneventapart.com/news/post/responsive-images-jason-grigsby-an-event-apart-video)
- What type is it?
  - [html - When to use IMG vs. CSS background-image? - Stack Overflow](http://stackoverflow.com/questions/492809/when-to-use-img-vs-css-background-image?rq=1)
  - [React Native - Image](https://facebook.github.io/react-native/docs/image.html)

_WIP_

Images on the web are hard. Straight up. You need to make many decisions, it is so much more work than "just throw an image in".

Here are the major decisions you'll need to make
- What type is it?
- What should load?
- When should it load?
- How should it load?
- How should it respond to viewport changes?

## What type is it?
In the wonderful developer experience world of React Native, we need only reach for one tool: `<Image>`. But on the web, we have more: `<img>`, `<picture>`, and `background-image` of a `<div>`.

So, which one should we use? Well, let me answer this question with a question. Is the image *content*?

If it is something that you'd like indexed by SEO, and visible if a user printed the page, then it is content. Often these images are stand alone, like logos, images of a product on an e-commerce site, and images interspersed in a blog post, for example. This is the world of `<img>`s and `<picture>`s. Exactly which of these two you'll use is decided in a future question.

If it is there to *enhance the display* of other content, like the background image of a header, then it is likely in the world of `<div>`s with `background-image` styles.

TODO: example picture with the two

I actually can't think of a case where I've put content on top of content images, so maybe it'd be easier to think of the separation as background vs foreground/content images.

## What should load?
When a user loads your page, what should they see? Well, your image, right? Not that easy, I'm afraid.


ResponsizeLoad -> use the smallest image that looks good with user's display
Responsive - send the smallest asset for the screen that still looks good
Art Direction - more than just resizing, it is cropping (or replacing) for specific viewports


## When should it load?
Lazy Load - defer loading until last possible moment to speed up TTI
lazy-load https://davidwalsh.name/lazyload-image-fade
padding-bottom https://www.smashingmagazine.com/2013/09/responsive-images-performance-problem-case-study/

# LazyLoad
The lazyload_images filter defers loading of images until they become visible in the client's viewport or the page's onload event fires. This avoids blocking the download of other critical resources necessary for rendering the above the fold section of the page.

- https://developers.google.com/speed/pagespeed/module/filter-lazyload-images
- https://github.com/dinbror/blazy/blob/master/blazy.js

Why Lazy Load?
Images make up over 60% of an average page’s size, according to HTTP Archive. Images on a web page would be rendered once they are available. Without lazy loading, this could lead to a lot of data traffic that is not immediately necessary (such as images outside of the viewport) and longer waiting times. The problem? Visitors are not patient at all. By lazy loading, images outside of the viewport are loaded only when they would be visible to the user, thus saving valuable data and time.

Lazy loading is not limited to images. It can be used on pages with complex JavaScript, iframes and third-party widgets, delaying the loading of these resources until the user actually needs them.

https://www.smashingmagazine.com/2015/02/redefining-lazy-loading-with-lazy-load-xt/

----------
"What would happen if JavaScript failed or didn't load for whatever reason? (connectivity problems, bad 3G, JavaScript-blockers, third-party scripts fail... you name it)"

In that case you need to use the noscript tag. Your final markup should look like:

```jsx
<img class="lazy" data-original="image-src.jpg" width="1200" height="600">
<noscript>
    <img src="image-src.jpg" width="1200" height="600">
</noscript>
```

https://www.sitepoint.com/lazy-loading-images-not-really-annoy-users/

posts like http://dinbror.dk/blog/lazy-load-images-seo-problem/ argue that noscript is no longer needed, but bing was not able to index the images, so we're not totally there yet

----------------
### Deferred vs Lazy Load
- Deferred will load every non-main image (usually below the fold) after page load
  - Necessary for those long, anchor-linked, single page sites
  - [Defer images without jQuery or lazy loading](https://varvy.com/pagespeed/defer-images.html)
    - ![](https://varvy.com/pagespeed/images/pageload.png)
    - ![](https://varvy.com/pagespeed/images/pageload-defer.png)
- Lazy Load monitors scroll position to load in images based on their proximity to the viewport

Lazy Load -> defer loading

Image decoding can take more than a frame-worth of time. This is one of the major sources of frame drops on the web because decoding is done in the main thread. In React Native, image decoding is done in a different thread. In practice, you already need to handle the case when the image is not downloaded yet, so displaying the placeholder for a few more frames while it is decoding does not require any code change.
https://facebook.github.io/react-native/docs/images.html

## How to load?
ProgressiveLoad -> load blurry LQIP (Low Quality Image Placeholder), then full

## Misc
### IMG Sprites
instead of loading multiple small images, consider spriting (single image with coordinates)

https://github.com/mixtur/webpack-spritesmith
https://github.com/tcoopman/image-webpack-loader

Progressive JPEG

## References
- What type is it?
  - [html - When to use IMG vs. CSS background-image? - Stack Overflow](http://stackoverflow.com/questions/492809/when-to-use-img-vs-css-background-image?rq=1)
  - [React Native - Image](https://facebook.github.io/react-native/docs/image.html)

# Perf
Even full loaded images can cause jank. When we had retina desktop images loaded on mobile, anchor scrolling and carousel scrolling were janky. Reducing image size was the fix.

Also see Image section of https://medium.com/@paularmstrong/twitter-lite-and-high-performance-react-progressive-web-apps-at-scale-d28a00e780a3


RN Images
- The packager knows the image dimensions, no need to duplicate it in the code.
- Note that image sources required this way include size (width, height) info for the Image. If you need to scale the image dynamically (i.e. via flex), you may need to manually set { width: undefined, height: undefined } on the style attribute.

In the browser if you don't give a size to an image, the browser is going to render a 0x0 element, download the image, and then render the image based with the correct size. The big issue with this behavior is that your UI is going to jump all around as images load, this makes for a very bad user experience.


In React Native this behavior is intentionally not implemented. It is more work for the developer to know the dimensions (or aspect ratio) of the remote image in advance, but we believe that it leads to a better user experience. Static images loaded from the app bundle via the require('./my-icon.png') syntax can be automatically sized because their dimensions are available immediately at the time of mounting.

---

Aspect ratio control the size of the undefined dimension of a node.
https://facebook.github.io/react-native/docs/layout-props.html#aspectratio

---



---
How to fill the entire page with an image, no white space, scales as needed, retains aspect ratio, and centered?

```
html {
  background: url(images/bg.jpg) no-repeat center center fixed;
  background-size: cover;
}
```

or use `background-image: url(_)`

---

RN
https://facebook.github.io/react-native/docs/pixelratio.html
https://facebook.github.io/react-native/docs/layout-props.html#aspectratio
The Component
<Image background lazy>
	children <- implicit “background” ?
</Image>

For now, build <BackgroundImage> and <Image> because they might be complicated enough. Then, consolidate into <Image background /> if it is feasible.


# Picture, srcset, sizes:
- sizes is like the upfront, static form of react router. Pre-parser needs it to optimize performance, but it's a bummer. You'd rather just say that the responsive image is here, not find the right size to load (like RR v4).
- https://aneventapart.com/news/post/responsive-images-jason-grigsby-an-event-apart-video
- https://github.com/scottjehl/picturefill
- https://afarkas.github.io/lazysizes/ (search for "picture") - see other polyfills



---------------

------------------

lazySizes plugins go into how complicated this feature can be: https://github.com/aFarkas/lazysizes#available-plugins-in-this-repo

https://github.com/aFarkas/lazysizes/blob/gh-pages/src/lazysizes-core.js might be better than blazy since it uses rAF

-----------------
http://rbrtsmith.com/2015/02/building-a-high-performance-lazy-load-module

Initially this sounds very simple, on page-load we can just grab the offsetTop of the images and store the values in the array, but upon further investigation this presents a problem. When we scroll to an image and it loads in, it pushes the content below further down the page, rendering the remaning offset values invalid.
...
One benefit I forgot to mention of the placeholder is that once the image loads the page will not have to be repainted unlike before because the placeholder already takes up that space so another +1 for the performance

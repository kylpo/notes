_WIP_

Images on the web are hard. Straight up. You need to make many decisions, it is so much more than "just throw an image in".

Starting with `<img />` vs `background-image` of a `<div />`

Image tag is inline

Style with backgroundImage, etc is background image. Because the inner View should be the one defining things like centering and margin/padding, not the some Image component...

# Deferred vs Lazy Load
- Deferred will load every non-main image (usually below the fold) after page load
  - Necessary for those long, anchor-linked, single page sites
  - [Defer images without jQuery or lazy loading](https://varvy.com/pagespeed/defer-images.html)
    - ![](https://varvy.com/pagespeed/images/pageload.png)
    - ![](https://varvy.com/pagespeed/images/pageload-defer.png)
- Lazy Load monitors scroll position to load in images based on their proximity to the viewport

# IMG Sprites
instead of loading multiple small images, consider spriting (single image with coordinates)

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

A common feature request from developers familiar with the web is background-image. To handle this use case, simply create a normal <Image> component and add whatever children to it you would like to layer on top of it.

---

Image decoding can take more than a frame-worth of time. This is one of the major sources of frame drops on the web because decoding is done in the main thread. In React Native, image decoding is done in a different thread. In practice, you already need to handle the case when the image is not downloaded yet, so displaying the placeholder for a few more frames while it is decoding does not require any code change.



https://facebook.github.io/react-native/docs/images.html

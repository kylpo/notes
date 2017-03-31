_WIP_

# Deferred vs Lazy Load
- Deferred will load every non-main image (usually below the fold) after page load
  - Necessary for those long, anchor-linked, single page sites
  - [Defer images without jQuery or lazy loading](https://varvy.com/pagespeed/defer-images.html)
    - ![](https://varvy.com/pagespeed/images/pageload.png)
    - ![](https://varvy.com/pagespeed/images/pageload-defer.png)
- Lazy Load monitors scroll position to load in images based on their proximity to the viewport

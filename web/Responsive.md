_WIP_

Use css media queries for all layout-based concerns

Only use `MatchMedia` (js hook to media queries) when it is a functionality concern
- e.g. when a button should change its onClick behavior for mobile vs desktop
- `react-media`
- [contra/react-responsive: Media queries in react for responsive design](https://github.com/contra/react-responsive?utm_campaign=Fullstack%2BReact&utm_medium=email&utm_source=Fullstack_React_56)

Just use https://medium.freecodecamp.com/the-100-correct-way-to-do-css-breakpoints-88d6a5ba1862#.sfq80hxnl

http://include-media.com/



Use MatchMedia for feature differences - like a button press calling different functions
Use for resize - if there are media breakpoints, it is much more performance than onResize.



media query in react Context instead of container components?


[Mobile, Small, Portrait, Slow, Interlace, Monochrome, Coarse, Non-Hover, First | CSS-Tricks](https://css-tricks.com/mobile-small-portrait-slow-interlace-monochrome-coarse-non-hover-first/)





Concern about inline option for server rendering. For server rendering’s sake, use css for media queries. Else, user will see a flash on page load.

-----------

use matchMedia for conditional loading (of components).

Use regular css media queries for others?

-----------

Container-based
https://github.com/walmartreact/container-query
http://engineering.skybettingandgaming.com/2016/05/12/responsive-react-components/
https://github.com/d6u/react-container-query


window-based
https://github.com/contra/react-responsive
https://github.com/matthewwithanm/react-mediaswitch
https://github.com/ReactTraining/react-media

containerSize='desktop'
containerWidth='SMALL_SCREEN'

http://unmatchedstyle.com/news/working-with-media-queries-and-min-width.php

start with mobile design, then use min-width to enhance for desktop, etc. Not the other way around (which would be starting with a fixed-width desktop size, and using max-width to make layout changes for mobile (like width: 100%))

https://github.com/foxhound87/mobx-react-matchmedia
https://css-tricks.com/naming-media-queries/
      // // 1
      // <Media queries=['(max-width: 1022px)', '<phone', '>=tablet']>
      //     {(isSmallScreenWidth, isPhoneWidth, isTabletWidth) => (
      //       <div/>
      //     )
      //   }
      // </Media>
      //
      // // 2
      // <Media queries=['(max-width: 1022px)', '<phone', '>=tablet']>
      //     {(toSmallScreen, beforePhone, fromTablet) => (
      //       <div/>
      //     )
      //   }
      // </Media>
      //
      // // 2.5
      // <Media queries=['(max-width: 1022px)', 'tablet-desktop', '>=tablet']>
      //     {(toSmallScreen, beforePhone, fromTablet) => (
      //       <div/>
      //     )
      //   }
      // </Media>
      //
      // // 3
      // <Media queries=['toSmallScreen', 'beforePhone', 'fromTablet']>
      //     {(toSmallScreen, beforePhone, fromTablet) => (
      //       <div/>
      //     )
      //   }
      // </Media>
      //
      // // 4
      // <Media queries=['toSmallScreen', 'beforePhone', 'fromTablet']>
      //     {(isToSmallScreen, isBeforePhone, isFromTablet) => (
      //       <div/>
      //     )
      //   }
      // </Media>
      //
      // // 5
      // <Media queries=['beforeSmallScreen', 'beforePhone', 'fromTablet']>
      //     {(isToSmallScreen, isBeforePhone, isFromTablet) => (
      //       <div/>
      //     )
      //   }
      // </Media>
      //


      // containerWidth='DESKTOP'
      // containerWidth='SMALL'   // MEDIUM, LARGE         dumb component doesn't care what the widths of these are - only the container does

-------------

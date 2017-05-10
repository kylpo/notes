There are two magical props in React: `key` and `ref`. This post will cover `ref`.

refs
- callbacks, how to avoid boilerplate? called on when unmounted (passes null)?
- how to reduce boilerplate with something like https://github.com/fresk-nc/babel-plugin-transform-jsx-ref-to-function?
- wish I could have a `setRef` prop that just accepts a pointer to my instance field.
- You may not use the ref attribute on functional components because they don't have instances. https://facebook.github.io/react/docs/refs-and-the-dom.html#refs-and-functional-components
- https://facebook.github.io/react/docs/refs-and-the-dom.html#caveats
-

- [Dan Abramov on Twitter: "Ever wondered why callback refs get called with null during the updates? I wrote a bit about this: https://t.co/42kdCy0eKF"](https://twitter.com/dan_abramov/status/859159065498406913)
- [Glen Mailer on Twitter: "@dan_abramov That's a very long way to say "null means unmount, use it as a signal to perform cleanup" 😉😊"](https://twitter.com/glenathan/status/859161300668166146)

- [Jason Miller 🦊⚛ on Twitter: "@aweary This is one reason I recommend linkRef: https://t.co/dEpsDrOrIT https://t.co/euiZDxFF8W"](https://twitter.com/_developit/status/859384258498101250)
- [James Kyle on Twitter: "@_developit @aweary @preactjs Here you go https://t.co/QT6YrAaNBE"](https://twitter.com/thejameskyle/status/859420749844680708)

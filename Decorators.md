# Decorators for Global Events Considered Helpful

I think I've found a really cool use case for decorators: they're perfect for attaching callbacks to global events!

## Without decorators
Lets start with an example component that listens to `scroll` events.

```jsx
class MyComponent extends React.Component {
  componentDidMount() {
    window.addEventListener('scroll', this.handleScroll)
  }

  componentWillUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
  }

  handleScroll = (e) => {
    // ...
  }

  // ...
}
```

Simple enough. We're registering our listener when it is mounted, and cleaning it up on unmount.

Later, we decide we'd also like to respond to `resize` events. So, we create a `handleResize()`, then register and clean it up in the lifecycle hooks.

```jsx
class MyComponent extends React.Component {
  componentDidMount() {
    window.addEventListener('scroll', this.handleScroll)
    window.addEventListener('resize', this.handleResize)
  }

  componentWillUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
    window.removeEventListener('resize', this.handleResize)
  }

  handleScroll = (e) => {
    // ...
  }

  handleResize = (e) => {
    // ...
  }

  // ...
}
```

Not a terrible DX (developer experience).

But you know what? This was actually the wrong call. The `resize` event only applies to a subcomponent, so we decide to extract it out. Now we have to cut/paste the `handleResize()` and cut/paste the `add`/`removeEventListener`.

```jsx
class MyComponent extends React.Component {
  componentDidMount() {
    window.addEventListener('scroll', this.handleScroll)
  }

  componentWillUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
  }

  handleScroll = (e) => {
    // ...
  }

  // ...
}

class MySubComponent extends React.Component {
  componentDidMount() {
    window.addEventListener('resize', this.handleResize)
  }

  componentWillUnmount() {
    window.removeEventListener('resize', this.handleResize)
  }

  handleResize = (e) => {
    // ...
  }

  // ...
}
```

Ugh, not the best DX.

## We can do better with decorators!

```jsx
class MyComponentUsingDecorators extends React.Component {
  @scroll
  handleScroll = (e) => {
    // ...
  }

  @resize
  handleResize = (e) => {
    // ...
  }

  // ...
}
```

What do `@scroll` and `@resize` do?
- They register and clean up their listeners for you
- They co-locate exactly what the `handle` function is used for
  - Maybe not necessary in our example `MyComponent` code, but the more `handle` functions it has, the nicer it is to see exactly what event it handles
  - It is SO much easier to copy/paste this functionality

Now, the refactor is a single cut/paste.

```jsx
class MyComponentUsingDecorators extends React.Component {
  @scroll
  handleScroll = (e) => {
    // ...
  }

  // ...
}

class MySubComponentUsingDecorators extends React.Component {
  @resize
  handleResize = (e) => {
    // ...
  }

  // ...
}
```

They are useful enough to stop here, but we can do more!

```jsx
class MyComponentUsingDecorators extends React.Component {
  @scroll({throttle: 50})
  handleScroll = (e) => {
    // ...
  }

  @resize({throttle: 100, enableResizeInfo: true})
  handleResize = (e, {width, height}) => {
    // ...
  }

  // ...
}
```

As shown, we can pass arguments to these decorators to throttle the event, auto-measure the window's width and height, and more. Convenient, and co-located.

## A powerful abstraction
Just one more benefit to consider. Since we are standardizing our global events with these decorators, we can enforce using something like [subscribe-ui-event](https://github.com/yahoo/subscribe-ui-event) to delegate events. This event delegation allows us to only measure expensive things like `width` and `height` once, then pass them down, as opposed to the default of each listener making these measurements. More on this in a future post.

## Which global events are these decorators helpful for?
I plan to use them for Web and React Native.

Web:
- scroll
  - `@scroll`
  - `@scrollStart`
  - `@scrollEnd`
- resize
  - `@resize`
  - `@resizeStart`
  - `@resizeEnd`
- matchMedia
  - `@media('(min-width: 500px)')`
- keypress
  - `@keydown('Escape')`
- visibilitychange

React Native:
- keyboard visibility
- backgrounded/foregrounded
- battery
- settings
- push notifications

## Conclusion
Global event decorators do wonders for DX. Depending on what they abstract, they can even enforce performance and enable conveniences via decorator arguments.

---
# Other notes


- [Enhancing React Components with decorators – Medium](https://medium.com/@gigobyte/enhancing-react-components-with-decorators-441320e8606a#.sjsi0hxct)
- [JavaScript — Make your Code Cleaner with Decorators – Frontend Weekly – Medium](https://medium.com/front-end-hacking/javascript-make-your-code-cleaner-with-decorators-d34fc72af947)

_WIP_

Use a modal overlay to stay in context after done w/ it.

Portal vs sending via App State
- Portal enables declaring Modal in a component's render:
```jsx
<SomeStuff />
<Modal isVisible={this.state.showOverlay}>
<OverlayConent />
</Modal>
```
  - but until Fiber comes out, this means it'll have to be wrapped in the component's outer div. That seems pretty weird for something that isn't actually rendered inside that div.
- Passing component to App State feels a bit strange in the react world, you end up passing the Component class, not an instance.

Happy to have used `ReactTransitionGroup` to hand enter/leave transitions of the overlay. The component just uses `componentDidEnter()` and `componentWillLeave()` hooks.

Overlay: does not lock scrolling
Modal Overlay (Modal for short): does lock scrolling. Often has an opacityOverlay behind it to denote this modal state.

- Dialog
  - Overlay
    - Modal?
      - opacityOverlay
      - scrollLock

[Modals in React – David Gilbertson – Medium](https://medium.com/@david.gilbertson/modals-in-react-f6c3ff9f4701)

Portals
- [react-portal/portal.js at master · tajo/react-portal](https://github.com/tajo/react-portal/blob/master/lib/portal.js)
- [Sebastian Markbåge on Twitter: "@iammerrick ReactDOM.unstable_renderSubtreeIntoContainer(...) That's what it is for."](https://twitter.com/sebmarkbage/status/694285706827399168?lang=en)


Setting `position: fixed` on `html` works well, but jumps to the top of the page. Also, doesn't it make Safari chrome appear?

[javascript - How to disable scrolling temporarily? - Stack Overflow](http://stackoverflow.com/questions/4770025/how-to-disable-scrolling-temporarily)

[html - Is `position: fixed` on `<body>` problematic? - Stack Overflow](http://stackoverflow.com/questions/37584726/is-position-fixed-on-body-problematic)

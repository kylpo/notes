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

Happy to have used ReactTransitionGroup to hand enter/leave transitions of the overlay. The component just uses `componentDidEnter()` and `componentWillLeave()` hooks.

Overlay: does not lock scrolling
Modal Overlay (Modal for short): does lock scrolling. Often has an opacityOverlay behind it to denote this modal state.

- Dialog
  - Overlay
    - Modal?
      - opacityOverlay
      - scrollLock

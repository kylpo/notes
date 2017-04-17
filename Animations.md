_WIP_

# Unmounting animations
- "unmounting animations are the hardest, I wish it were easier" - [@browniefed](https://twitter.com/browniefed/status/839514443285311488)
- use `transition-group`

# React animations on web
- always start with animating via a `render()` update. Some animations will need the perf of going right to the DOM and avoiding `render()` though, like we do with React Native.
- `setState` for transforms

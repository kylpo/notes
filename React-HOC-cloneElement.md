_WIP_

TASK: read through
[pinnacle/react-event: Declarative way to handle events outside / inside of React Component.](https://github.com/pinnacle/react-event?utm_source=reactnl&utm_medium=email)
- shows how HOC is build-time configuration

Decorator component is runtime config

HOC is a more specific term for HOF. Like Component is a more specific term of Function.


Wrappers -> wrap children and introduce something to dom
Manipulators (or Injectors) -> pass props (injects props into child(ren))

static vs dynamic config
HOC ahead-of-time, not build-time

cloningComponent

I'd like to talk about the two ways to customize components, without actually changing any of their code: HOC and cloneElement.

# Terms
**HOC** wraps a **class** and augments by passing props

**Decorator Component** wraps an **~~instance~~ element** and augments w/ `cloneElement()`

**Higher-Order Functions**, like redux's `connect`, are functions that return a **Higher-Order Component**

You would never want to HOC in a render. You can only cloneElement in a render.

function vs decorator form to produce HOC

our way of getting mixins: HOC, decorator

Many articles call HOF's HOCs. I don't _think_ this is right, but I'm not the expert, either.

Want to learn more about HOCs? See [React Higher Order Components in depth – franleplant – Medium](https://medium.com/@franleplant/react-higher-order-components-in-depth-cf9032ee6c3e)

Also, consider reaching to recompose as a lodash-like helper for some HOCs.

Want to learn more about cloneElement? See my deep dive, here.

[Write a Higher Order Component from Scratch - react Video Tutorial #free @eggheadio](https://egghead.io/lessons/react-write-a-higher-order-component-from-scratch) for a good intro to HOC (other than the terminology)

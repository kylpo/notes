_WIP_

# Terms
**HOC** wraps a **class** and augments by passing props

**Decorator Component** wraps an **~~instance~~ element** and augments w/ `cloneElement()`

**Higher-Order Functions**, like redux's `connect`, are functions that return a **Higher-Order Component**

# Conventions
- see [Official Docs](https://facebook.github.io/react/docs/higher-order-components.html#convention-pass-unrelated-props-through-to-the-wrapped-component)
- `passProps` that aren't related to HOC
- hoist statics
- debug label w/ `displayName`

# Considerations
- `ref`s aren't passed through
  - use `refNode` pattern

# React.cloneElement() workings
Given this page, what do we expect to see in console?
```jsx
class Cloning_ extends React.Component {
  componentDidMount() {
    console.log('Cloning Mount')
  }

  render() {
    console.log('Cloning Render')

    const { children, ...propsToPass } = this.props
    const child = React.Children.only(children)

    console.log('ChildProps: ', child.props)

    return React.cloneElement(child, propsToPass)
  }
}

class Div extends React.Component {
  static defaultProps = {
    bye: 'bye'
  }

  componentDidMount() {
    console.log('Div Mount')
  }

  render() {
    console.log('Div Render')

    return (
      <div>{this.props.children}</div>
    )
  }
}

export default class App extends React.Component {
  render() {
    return (
      <Cloning_>
        <Div hi="hi" />
      </Cloning_>
    )
  }
}
```
```bash
Cloning Render
ChildProps:  Object {hi: "hi", bye: "bye"}
Div Render

Div Mount
Cloning Mount
```

Hmmm, how can `Cloning_` have the child `Div` without `Div` being rendered first? Ahhhh, it must create an instance of it, which `Cloning_` can use. So, lets `console.log()` in each of their `constructor()`s.
```bash
Cloning Constructor
Cloning Render
ChildProps:  Object {hi: "hi", bye: "bye"}

Div Constructor
Div Render

Div Mount
Cloning Mount
```

Nope, that wasn't it.

And why can we see its props - especially the `defaultProps`!? What about its state? If we gave it a state of `state = {why: 'why'}`, could `Cloning_` see it?

First of all, no. `Cloning_` can not see it's child's state. Why? Well, because it doesn't exist yet. Keep in mind that JSX maps to `React.createElement()`, which returns an `element` (a simple object description React uses to apply to DOM).
```jsx
React.createElement(
  Cloning_,
  null,
  React.createElement(
    Div,
    { hi: 'hi' }
  )
)
```
When `App` is rendered (from `ReactDOM.render()`), in creating a `Cloning_` element, it must first create the `Div` element. It is normal javascript execution order, but still nice to see:
```jsx
function createElement(label, component, props, children) {
  console.log(`${label} element created`)

  return React.createElement(
    component,
    props,
    children
  )
}
export default class App extends React.Component {
  render() {
    return (
      createElement(
        'Cloning_',
        Cloning_,
        null,
        createElement(
          'Div',
          Div,
          { hi: 'hi' },
        ),
      )
    )
  }

```
```bash
Div element created
Cloning_ element created
```

Back on topic: `Cloning_` is acting on the `element` of `Div`, and returning a new `element`. The returned `element` is a clone, with potentially modified passed in props.

Oh, is it like `Object.assign()` then? Almost like `Object.assign({}, divElement, {newProp: 'newProp'})`?
Yes, actually. The clone's props will even override the child props. Seen here:
```jsx
class Cloning_ extends React.Component {
  render() {
    const { children, ...propsToPass } = this.props
    const child = React.Children.only(children)

    console.log('childProps: ', child.props)

    const clone = React.cloneElement(child, propsToPass)
    console.log('cloneProps: ', clone.props)

    return clone
  }
}

export default class App extends React.Component {
  render() {
    return (
      <div >
        <Cloning_ hi='bye'>
          <Div hi='hi' />
        </Cloning_>
      </div>
    )
  }
}
```
```bash
childProps:  Object {hi: "hi", bye: "bye"}
cloneProps:  Object {hi: "bye", bye: "bye"}
```

Notice the change in the value of `hi`. OK, one last thing. See that `bye: "bye"` part? That crept in because `Div` has `static defaultProps = {bye: 'bye'}`. Thanks to it being a `static`, `React.CreateElement()` is able to use it for the returned `element`.

## Order of operations in rendering `elements`, `components`, parents, and children?
Allllright, lets finish this exploration. What do you expect to be logged in this example?

```jsx
class Cloning_ extends React.Component {
  constructor() {
    super()

    console.log('Cloning Constructor')
  }

  componentDidMount() {
    console.log('Cloning Mount')
  }

  render() {
    console.log('Cloning Render')

    const { children, ...propsToPass } = this.props
    const child = React.Children.only(children)

    return React.cloneElement(child, propsToPass)
  }
}

class Div extends React.Component {
  constructor() {
    super()

    console.log('Div Constructor')
  }

  componentDidMount() {
    console.log('Div Mount')
  }

  render() {
    console.log('Div Render')

    return (
      <div>{this.props.children}</div>
    )
  }
}

function createElement(label, component, props, children) {
  console.log(`${label} element`)

  return React.createElement(
    component,
    props,
    children
  )
}

export default class App extends React.Component {
  render() {
    /*
    * <Cloning_ >
    *   <Div/>
    * </Cloning_>
    */
   return (
     createElement(
       'Cloning_',
       Cloning_,
       {hi: 'hi'},
       createElement(
         'Div',
         Div,
         null,
       ),
     )
   )
  }
}

// elsewhere...

ReactDOM.render(
  <App />,
  document.getElementById('root')
)
```
```bash
Div element
Cloning_ element

Cloning Constructor
Cloning Render
Div Constructor
Div Render

Div Mount
Cloning Mount
```

Modified template of updates from [offical docs](https://facebook.github.io/react/docs/components-and-props.html)
1. `ReactDOM.render()` is called with with the `<App />` element
2. Using the `App` element, React creates and renders the `App` component
3. Our `App` component creates `Div`, then `Cloning_` elements and returns the tree (`<Cloning_><Div hi='hi' /></Cloning_>`) as the result.
4. Using the `Cloning_` element, React creates and renders  the `Cloning_` component with `{hi: 'hi'}` as the props.
5. Our `Cloning_` component returns a cloned `<Div />` element, with `{hi: 'hi'}` passed as props, as the result.
6. Using the `Div` element, React creates and renders the `Div` component
7. Our `Div` component returns a `<div />` element as the result.
8. React DOM efficiently updates the DOM to match the tree of elements.

Think about nested `cloneElement()`s:
```jsx
<Cloning_>
  <Cloning_>
    <Div />
  </Cloning_>
</Cloning_>
```

Powerful lifecyle hooks, but ultimately `Cloning_` just does work to compute props/children to be passed in to `Div`. `Div` will render last with the passed in props.

Props to the current official [docs](https://facebook.github.io/react/docs/components-and-props.html), which explain all of this nicely. I just needed more examples to solidify everything.


# `cloneElement()` of a PureComponent child
see [shouldComponentUpdate doc](https://github.com/kylpo/notes/blob/master/shouldComponentUpdate.md#cloneelement-of-a-purecomponent-child)

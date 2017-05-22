# Naming Convention for Injector Components
Huh? What is an "injector component"?

An injector component takes props, optionally uses thos props to compute new ones, then passes them down to its child via `React.cloneElement()`. Crucially, they also do not add any new components to do DOM! They just inject to their child.

```jsx
export class InjectorComponent extends React.Component {
  render() {
    const propsToPass = computePropsToPass(this.props)

    // cloneElement requires a single child, no arrays
    const Child = React.Children.only(this.props.children)

    return React.cloneElement(Child, propsToPass)
  }
}

// Used later like...

<InjectorComponent
  something={something}
  another='another'
>
  <ChildToBeCloned />
</InjectorComponent>
```

## When Are Injector Components Useful?
In the prototyping framework, [constelation](https://github.com/constelation/monorepo), we use a LOT of injector components to abstract out logic and nicely separate concerns like style, animation, and interactions from our layout components.

React Native has also used this pattern in [TouchableWithoutFeedback](https://github.com/facebook/react-native/blob/master/Libraries/Components/Touchable/TouchableWithoutFeedback.js#L173).

Here is an example render using many injector components:

```jsx
<Event
  onClick={this.handleClick}
>
  <Animate
    type='fadeIn'
    duration='3000ms'
    ref={node => this.animated = node}
  >
    <Style
      backgroundColor='red'
      border='1px solid black'
      transition='opacity 10000ms ease'
    >
      <View
        height='500px'
        width='200px'
        alignHorizontal='center'
        alignVertical='center'
      >
        <Text>Click me</Text>
      </View>
    </Style>
  </Animate>
</Event>
```

But here's the thing, which of these components are injectors? How many elements are actually added to the DOM?

## The `<Injector_ >` Naming Convention
With `constelation`, we've chosen to denote injector components with a postfix `_`. Think of the postfix `_` as being a blank space that needs to be filled by a child. Also, the name chains well. Below could read like: "an Evented, Animated, Styled View with a Text child"

```jsx
<Event_
  onClick={this.handleClick}
>
  <Animate_
    type='fadeIn'
    duration='3000ms'
    ref={node => this.animated = node}
  >
    <Style_
      backgroundColor='red'
      border='1px solid black'
      transition='opacity 10000ms ease'
    >
      <View
        height='500px'
        width='200px'
        alignHorizontal='center'
        alignVertical='center'
      >
        <Text>Click me</Text>
      </View>
    </Style_>
  </Animate_>
</Event_>
```

Notice how much easier it is to identify the injectors? Also, we can now easily see that there are two elements added to the DOM (two do not have a postfix `_`).

## It Gets Better
Can you spot the errors in this render?

```jsx
<Style_ />

<TouchableWithoutFeedback_>
  <Child1 />
  <Child2 />
</TouchableWithoutFeedback_>
```

Yes! Injector components should never be self-closing, and they should never wrap multiple children. We can fix this at code-time and not wait for the errors at runtime.

This naming convention helps developers understand the component's contract, and certainly would've helped me better understand what `TouchableWithoutFeedback` and `TouchableOpacity` are doing under the hood.

## Even Better With Tooling
Naming conventions enable tooling. I've edited my vim color scheme to color injector components as props are colored, which further reinforces the concept and allows me to easily skim renders and identify them.

![](https://github.com/kylpo/notes/blob/master/assets/InjectorComponents.png?raw=true)

---

Note: I publish these to learn from your responses! Please let me know if you have any thoughts on the subject.

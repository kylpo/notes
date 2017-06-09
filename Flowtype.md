_WIP_

[James Kyle on Twitter: "Just open sourced a Babel plugin for converting Flow types to PropTypes even across modules: https://t.co/U4m53mmv4C https://t.co/Ovbd0i9bFj"](https://twitter.com/thejameskyle/status/870762618599817216)

- [James Kyle on Twitter: "Some @flowtype tricks: Inference, Comment syntax, and typeof, all working together https://t.co/xoDxjY9YfC"](https://twitter.com/thejameskyle/status/868148120504356864)
![](https://pbs.twimg.com/media/DAxIHJYUwAAyaiM.jpg:large)

- [Patrick Stapfer on Twitter: "I need to rephrase: Stop annotating excessively inside your function bodies... stay flexible inside, make the input / output well-typed https://t.co/pHLWQgWRNA"](https://twitter.com/ryyppy/status/850035450811228160)

https://blog.callstack.io/type-checking-react-and-redux-thunk-with-flow-part-1-ad12de935c36#.50qcniea3
- generics for Container components explanation

[James Kyle on Twitter: ".@flowtype comment syntax is so useful for modules like this - No build step - Type-checked - Ships with Flow types https://t.co/4AdQrcl33b https://t.co/KDVgVNw6pY"](https://twitter.com/thejameskyle/status/864649054461886464)


[Flow type cheat sheet - SaltyCrane Blog](https://www.saltycrane.com/blog/2016/06/flow-type-cheat-sheet/)

# FAQ
## Children
```jsx
import React from 'react';
import type { Children } from 'react';
type Props = {
  children?: Children,
};
const SampleText = (props: Props) => (
  <div>{props.children}</div>
);
```
from https://stackoverflow.com/questions/40651126/flow-type-annotation-for-children-react-elements

## binding methods in class gives me some "Covariant" errors
Must type them as `Function` in class:
```jsx
class HeaderContainer extends React.Component {

  handleNavigate: Function;
  toggleMenu: Function;

  constructor(props: Object) {
    super(props);
    this.handleNavigate = this.handleNavigate.bind(this);
    this.toggleMenu = this.toggleMenu.bind(this);
  }

  handleNavigate() {
    console.log('hey');
  }

  toggleMenu() {
    console.log('ho');
  }

  render() {
    return (
      <div />
    );
  }
}
```
from https://github.com/ryyppy/flow-guide/issues/6

## DefaultProps get nullable type errors
"You don’t have to mark your defaultProps as optional properties in your props. Flow knows how to handle them properly."
from [official docs](https://flow.org/en/docs/frameworks/react/#toc-adding-types-for-react-component-props)

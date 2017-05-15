# You Can Spread Props, But Should You?
When I first learned about spreading props in JSX, I was thrilled! It is just so convenient to pass props with `<MyComponent {...this.props} />`, and override props defined after the spread, like `<MyComponent {...this.props} text='override text prop' />`. I knew it made for a great developer experience, but I always wondered if it came with a cost. How does React handle it? Does it affect performance?

Well, it took me far too long, but I've finally answered my questions, thanks to Babel's online repl. You're welcome to play around with the result [here], or read on.

## Transpiling Explicit Props
Let's start with our control.

```jsx
const Comp = (props) => (
  <div hi='bye' yes='no' />
)

// transpiles to:

var Comp = function Comp(props) {
  return React.createElement('div', { hi: 'bye', yes: 'no' });
};
```

Cool, this is showing how JSX is converted to `React.createElement()` and made into valid javascript. Also note that props are converted and passed as a single object literal.

## Transpiling Spread Props
```jsx
const someProps = {
  one: 1,
  two: 2,
}

const OnlySpread = (props) => (
  <div {...someProps} />
)
```

Given the above, how do you expect `OnlySpread` to be transpiled?

```jsx
var someProps = {
  one: 1,
  two: 2
};

var OnlySpread = function OnlySpread(props) {
  return React.createElement('div', someProps);
};
```

Oooh, nice! It just passes in the already created object as its props. No cloning, just passing by reference.

## Transpiling Spread AND Explicit Props
```jsx
const someProps = {
  one: 1,
  two: 2,
}

const SpreadAndExplicit = (props) => (
  <div {...someProps} hi='bye' />
)
```

Given the above, how do you expect `SpreadAndExplicit` to be transpiled?

```jsx
var someProps = {
  one: 1,
  two: 2
};

var SpreadAndExplicit = function SpreadAndExplicit(props) {
  return React.createElement('div', Object.assign({}, someProps, { hi: 'bye' }));
};
```

Bummer! No magic here. It just converts the explicit props to an object literal, then uses `Object.assign()` to merge the two.

`Object.assign()` is a micro-perf hit compared to creating an object literal, as [this esbench](https://esbench.com/bench/58e7f6e899634800a0347ca1) shows. So, it is better to explicitly pass all props and not use a spread at all.

```jsx
const AllExplicit = (props) => (
  <div one={1} two={2} hi='bye' />
)

// transpiles to:

var AllExplicit = function AllExplicit(props) {
  return React.createElement('div', { one: 1, two: 2, hi: 'bye' });
};
```

We're back to a single object literal. Micro-perf win!

## Transpiling Multiple Spread Props
To be pedantic, lets see what happens when we spread two sets of props.

```jsx
const someProps = {
  one: 1,
  two: 2,
}

const TwoSpread = (props) => (
  <div {...someProps} {...props} />
)

// transpiles to:

var TwoSpread = function TwoSpread(props) {
  return React.createElement('div', Object.assign({}, someProps, props));
};
```

Again, no magic. Not surprised that it still uses `Object.assign()`.

## Deopt For Production Transforms
It is also worth noting that spread is a deoptimization for two babel transforms commonly used on production bundles: [transform-react-inline-elements](https://babeljs.io/docs/plugins/transform-react-inline-elements/) and [transform-react-constant-elements](https://babeljs.io/docs/plugins/transform-react-constant-elements/)

## Conclusion
In my perfect world going forward, I'll only see JSX spreads if and only if they are not accompanied with other props. Else, they should all be explicitly passed. Of course, this is just a micro-perf optimization, so it will not be a hard rule, and I will certainly not be frantically updating legacy code.

```jsx
// GOOD
<div {...this.props} />

// GOOD
<div one={1} two={2} />

// BAD
<div {...this.props} two={2} />

// BAD
<div {...this.props} {...otherProps} />
```

---

Note: I publish these to learn from your responses! Please let me know if you have any thoughts on the subject.

[here]: https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&targets=&browsers=&builtIns=false&debug=false&code=const%20someProps%20%3D%20%7B%0A%20%20one%3A%201%2C%0A%20%20two%3A%202%2C%0A%7D%0A%0Aconst%20Comp%20%3D%20(props)%20%3D%3E%20(%0A%20%20%3Cdiv%20hi%3D'bye'%20yes%3D'no'%20%2F%3E%0A)%0A%0Aconst%20OnlySpread%20%3D%20(props)%20%3D%3E%20(%0A%20%20%3Cdiv%20%7B...someProps%7D%20%2F%3E%0A)%0A%0Aconst%20SpreadWithExplicit%20%3D%20(props)%20%3D%3E%20(%0A%20%20%3Cdiv%20%7B...someProps%7D%20hi%3D'bye'%20%2F%3E%0A)%0A%0Aconst%20AllExplicit%20%3D%20(props)%20%3D%3E%20(%0A%20%20%3Cdiv%20one%3D%7B1%7D%20two%3D%7B2%7D%20hi%3D'bye'%20%2F%3E%0A)%0A%0Aconst%20TwoSpread%20%3D%20(props)%20%3D%3E%20(%0A%20%20%3Cdiv%20%7B...someProps%7D%20%7B...props%7D%20%2F%3E%0A)

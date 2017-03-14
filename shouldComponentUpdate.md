_WIP_

- [Dan Abramov on Twitter: "PSA: React.PureComponent can make your app slower if you use it everywhere."](https://twitter.com/dan_abramov/status/820668074223353858)
- React.PureComponent, shallowCompare
- stateless functional component can be pure, but it'll still rerender every time
- use primitives over objects/arrays, as http://ericlathrop.com/2017/02/why-did-this-react-component-rerender/ mentions
- scu => false will not prevent props from updating
  - actually a feature. Animate_'s `start*` to trigger animations without causing a rerender.
    - combines scu with cwrp. Advanced understanding to get here.

be sure to look through your [gdoc](https://docs.google.com/document/d/1KfC1aoQbd9bAVXQGNNGm5-1hCG-P2TeX-vabaVZG6I8/edit)

CDM: child, then parent

cSU == false
- still calls `willReceiveProps`

PureComponent re-rendering in Animate_
- children problem?
- animate() doing something to force re-render?
- I think it is a child mismatch problem
  - because child in render does not match what it returns?

[rnosov/react\-reveal: Easily add reveal on scroll animations to your React app](https://github.com/rnosov/react-reveal)

---

[rafrex/react\-interactive: Inline styles for hover/active/focus interactive states](https://github.com/rafrex/react-interactive?utm_campaign=Fullstack%2BReact&utm_medium=email&utm_source=Fullstack_React_82)

---

Treat the Revealer's role as you would an IDE's _timeline_. It doesn't tell things how to react, necessarily, it just tells them to react, and potentially monitors how long it takes them to fire tiggers afterward.

Like Canary's new Event Timeline: https://twitter.com/umaar/status/849610803368140800

---

```jsx
<Section
  id='myUniqueID'
  groupID=''
  waitForLazy={}
  waitForSection={}
  waitForGroup={}
  onEnter={}
  onLeave={}
>
  ...
</Section>
```

---

row-level animations?

x x x _

How to check neighbors in view? `isLoaded` && `isVisible` => `isReady`

Are others in *group* ready? Timeline is in control of grouping.

---

https://github.com/joshwnj/react-visibility-sensor

http://www.react-flight.io/?utm_source=mybridge&utm_medium=blog&utm_campaign=read_more

https://github.com/stratiformltd/react-loadable-visibility

controls animation sequencing and event (visibility, loaded, etc) sequencing

---

- Timeline
  - like [jondot/react-flight: The best way to build animation compositions for React.](https://github.com/jondot/react-flight)?
  - [madou/yubaba: ✨ Orchestrated page transitions made easy](https://github.com/madou/yubaba)
  - [react\-inview\-monitor Example](https://snipsco.github.io/react-inview-monitor/) - interesting idea to just apply the className, like `ReactCSSTransitionGroup`.
```jsx
return (
  <InViewMonitor
    intoViewRatioShownThreshold={0}
    classNameInitial='tabs'
    classNameScrolledPastView='tabs tabs--fixed'
  >
    <TabsHere />
  </InViewMonitor>
)
```
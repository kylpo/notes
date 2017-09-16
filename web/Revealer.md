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
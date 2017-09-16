In building for the web, you'll likely want tools and components to address:

## Images
Considerations:
Image
- background
- foreground/content

svg (separate from image)

Questions to answer:
- What to load?
- When to load?
- How to load?
- How does it scale?

```jsx
<Image progressive lazy src={}/>
```

Style with backgroundImage, etc is background image. Because the inner View should be the one defining things like centering and margin/padding, not the some Image component...

## Layout
View, Row, Col, Grid

These include things like `zIndex`

Media Queries?

## Style
Would be `paint`, but also applies to transforms

## Coordination/Sequencer
Not just for animations. Also events like lazy loading.

See the Revealer Doc

## Constants
`CHARACTER.js`
`SIZE.js`
`COLOR.js`
`Z_INDEX.js`
`BREAKPOINT.js`

## More components
- Icon
- IMageSequence
- Link
- Video
- Waypoint
- Carousel


---

Misc notes

1. replace div/span/img with view, col, row, flex, space, scrollView?, text, image. Offer `css` prop.
2. breakpoints
3. style_?
4. events

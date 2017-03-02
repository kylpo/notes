_WIP_

margin vs padding (future blog post)
- Margin used solely for layout between components? Padding used solely for layout within components?
- can I have some <Margin /> component that doesn't add an extra div/View and be used specifically for scene layouts?
  - a Margin component would solve my problem with needing to wrap Text with a View just to add some padding between words, too
- Padding: _position_ within component. P for position.
- Margin: _layout_ for component (should not be a component's concern). M for ?

Since I currently use flexbox for all of my layouts, web and native, margin does not collapse and has been used almost interchangeably with padding.

Consider a template-only primitive for margin, maybe named `<Spacer />` as an alternative to requiring all of your composite components to accept a `margin` prop

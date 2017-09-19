# The "Style" Problem
What we refer to as "style" actually includes quite a few concepts:


Layout — how an element/component looks in relationship to others
Appearance — the characteristics of an element/component
Behavior and state — how an element/component looks in a given state

don't add layout styles directly to your component.

http://stackoverflow.com/questions/26882177/react-js-inline-style-best-practices


---

When in developer-mode, what piece of information here, matters?

`<div className='...' />`

Certainly isn't the div. This distinction isn't really useful to the dev unless in accessibility-mode:

`<nav className='...' />`

The className is what matters. More specifically, the layout within that classname is what matters.

Sometimes the style also matters. THis is why we separate the two.

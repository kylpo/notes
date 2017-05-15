_WIP_

# RN
[AppAndFlow/react-native-touchable: React-Native button helper library](https://github.com/AppAndFlow/react-native-touchable)

# Hammer Events

Best generic term for click, touch, etc is *onPress*

- onPress -> press and hold to trigger
- onTap -> press and lift quickly to trigger
- onClick -> pressDown, optionally hold for a while, pressUp to trigger

Hammer should probably eventually be replaced by Pointer Events or some new abstraction on top of it. No Firefox or Safari support yet. https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events

# Event Bubbling vs Capture, and propagation

onClick, browser captures the event top-down, from html, to body, all the way down to the div. If the listener set capture to true, it would call the function on its way down. This is set to false be default though, so when it makes it to the deepest node, it will then fire its function and work its way back up.

e.stopPropagation() stops it from bubling up or capturing down any further.

Basically all events start at the document body then step through the DOM until they hit the element where the event (for example a click) was triggered. Then, if the event can bubble, it reverses back through the DOM until it hits the document body again. (Not all events bubble – for example error and blur events)

As the event moves from the document body towards the target element it is said to be in its capturing phase, when it reaches the target it is at target and is in its bubbling phase when it reverses back up through the

document.https://mattandre.ws/2014/08/small-beautiful-dom-delegation/

React: Event stop propagation by default? Credit to @tdreyno

Be sure to debounce high-rate events like scroll and resize. Debounce with RAF, not lodash. https://www.html5rocks.com/en/tutorials/speed/animations/

# Event Delegation vs adding many event listeners

"Short-story: delegate saves CPU when binding event handlers; bind saves CPU when events trigger (e.g. a user clicks something)"
- http://stackoverflow.com/questions/8827430/event-delegation-vs-direct-binding-when-adding-complex-elements-to-a-page

Problem with many listeners is memory-bound. Use event delegation via event bubbling to get around this. http://gregfranko.com/blog/javascript-performance-tips/


http://stackoverflow.com/questions/12824549/should-all-jquery-events-be-bound-to-document/12824698#12824698

http://stackoverflow.com/questions/23416511/javascript-jquery-event-listener-performance

Enter event delegation. Event delegation allows you to attach an event listener higher up the DOM tree, rather than hundreds or thousands on the individual child elements. In our <ul> of friends, we can attach a click event listener on the <ul> itself. Clicks on the <h3> friend’s names will bubble up to their common container, and run the event listener there:

http://davewasmer.com/javascript-event-delegation/


static vs dynamic (delegated) event handling
http://stackoverflow.com/questions/9730277/jquery-event-handlers-whats-the-best-method/9730309#9730309

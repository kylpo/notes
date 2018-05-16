[Dion Almaer on Twitter: "An animation feature that I love in Elevate is how you can always skip to the end of the animation with a tap\. https://t\.co/rCakWmh9ZG"](https://twitter.com/dalmaer/status/893936268668579840)

---

[Good to great UI animation tips – UX Collective](https://uxdesign.cc/good-to-great-ui-animation-tips-7850805c12e5)

* Shared Elements
* cascading effects
* make content push other elements
* use buttons to show different state
* bring attention to something important

---


Transitions transform elements that already exist. Else, they need to enter from off screen.

Opacity fade in to grab attention or make an enter less harsh.

Transitions are about relationships. Shared elements in transitions.

1. Identify core functionality
2. Make that functionality available using the simplest technology
3. Enhance!

“Animation is about creating the illusion of life.”
Brad Bird


-------------

For anything that is in direct response to a user action, like an expanding UI widget, you should ease out. The reasoning is pretty simple: you want to start fast because it gives the perception of responsiveness. Ease outs will give you that and give you a nice settle. Ease ins and in-outs don’t and the user will feel like they’re willing the animation to get done.

Expand fast, contract slow(er). I typically roll with around 200ms for outward animation and 300ms for returns. This is personal preference, but I find that it’s a decent balance. Getting the animation complete to get to the interactivity on the way out is paramount, but you want some animation so it feels polished. Appearing instead of animating is fine, and if it comes down to it, no animation on the way out is way better than a slow one. On the way back (where the user isn’t interacting anymore) we can afford to be a little gentler.

https://aerotwist.com/tutorials/protip-choose-your-ease/

---------------

An easing function establishes the relation between time and animation’s progress.

Short for in-betweening, the process of generating intermediate frames between two images to give the appearance that the first image evolves smoothly into the second image. Tweening is a key process in all types of animation, including computer animation.

---------------

Need to change the size? Try rotating it while re-sizing. I've seen this a lot int he collect-ui animations.

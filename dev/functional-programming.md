No variables
No loops
Pure functions
- only use inputs
- return something
- no side effects


"We’re always trying to figure out ways of doing the work once and how we can reuse it to do something else.

Code reuse sounds great but is difficult to achieve. Make the code too specific and you can’t reuse it. Make it too general and it can be too difficult to use in the first place.

So what we need is a balance between the two, a way to make smaller, reusable pieces that we can use as building blocks to construct more complex functionality."
- https://medium.com/@cscalfani/so-you-want-to-be-a-functional-programmer-part-3-1b0fd14eb1a7#.vjnitoao5 


--------------

epiphany: Rambda isn't any better than lodash or underscore when considered in isolation in a function. In fact, I think it the style of writting many named, curried functions as steps to one big .compose solution is FAR worse than just chaining for readability in a function.

Where the named, curried functions are helpful is at the _class_ level. If I need to get unwrappedHashTypes() in many different functions,  I can define it once as a curried function (could be with or without Ramda), then use it in my local-to-function chains.

BOOM! Syntax/style figured out for functional programming, and yes, Ramda's curried-first style is worth using over lodash and underscore.

Also, the _curriedFunctionName() syntax does make sense.

-----------


What is wrong with loops vs functions like map, reduce, filter..?
Loops don’t give the reader any information about the kind of operation being performed

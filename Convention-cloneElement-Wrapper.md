# Naming Convention for Decorator Components
First of all, what do I mean by a `Decorator Component`. No, it isn't a class `@decorator`, but it does serve a similar function. "decorators provide a very simple syntax for calling higher-order functions" - from [Exploring EcmaScript Decorators – Google Developers – Medium](https://medium.com/google-developers/exploring-es7-decorators-76ecb65fb841). Decorator Components essentially call a HOF (createElement), which returns a HOC (via cloneElement).

It isn't just a passProps because HOC's are also used to just passProps.

Can you spot which component does not contribute anything to the DOM?

No? Why not?

Because we haven't established a convention for it yet.

I propose we use...

With conventions, we can even start building useful tooling for it. Check out my vim syntax highlighting, which colors these as props are highlighted.


## it gets better
Now, can you spot the error in this render?

```jsx
<Style_ />

<Style_>
  <Child1 />
  <Child2 />
</Style_>
```

Yes, they should never be self-closing. They always required a single child.

Can you tell me which of these components renders nothing in the DOM? i.e. their render looks something like:
```jsx
render() {
  // Potentially do logic

  return null
}
```

```jsx
import Redirct from 'react-router'

<View>
  <Redirect />
</View>
```

If you are familiar with React Router V4, you may know that it doesn't render anything, but what if you could know without prior knowledge?

Introducing the `<_RendersNull_ />` convention

With this naming convention, you quickly see exactly what renders nothing. Even better, you can use tooling to better highlight it. My vim config highlights these a different color.


Now, which of these components renders nothing in the DOM?


```jsx
<View>
  <Style_>
    <View />
  </Style_>

  <_Redirect_ />
</View>
```

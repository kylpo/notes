_WIP_

Just answered a question I’ve long had about spreading props in JSX. I intend to not use it as much as possible going forward. When I do use it, it’ll hopefully be the only props passed in. See this Babel repl link: https://babeljs.io/repl/#?babili=false&evaluate=true&lineWrap=false&presets=es2015%2Creact%2Cstage-2&targets=&browsers=&builtIns=false&code=const%20someProps%20%3D%20%7B%0A%20%20one%3A%201%2C%0A%20%20two%3A%202%2C%0A%7D%0A%0Aconst%20Comp%20%3D%20(props)%20%3D%3E%20(%0A%20%20%3Cdiv%20hi%3D'bye'%20yes%3D'no'%20%2F%3E%0A)%0A%0Aconst%20Comp2%20%3D%20(props)%20%3D%3E%20(%0A%20%20%3Cdiv%20%7B...someProps%7D%20%2F%3E%0A)%0A%0Aconst%20Comp3%20%3D%20(props)%20%3D%3E%20(%0A%20%20%3Cdiv%20%7B...someProps%7D%20%7B...props%7D%20%2F%3E%0A)%0A%0Aconst%20Comp4%20%3D%20(props)%20%3D%3E%20(%0A%20%20%3Cdiv%20%7B...someProps%7D%20hi%3D'bye'%20%2F%3E%0A)%0A%0A

`Object.assign()` is more expensive than object literals. So, it’d be better to just explicitly pass in all props that you had spread. Except when you are only passing in spread props. Then it is ok: it just sends the object and doesn’t assign to a new one.

Also, that first component is extra perf-special. It’s object literal of non-dynamic values is hoisted up, and out of the component render with a babel transform that we likely all have turned on in production. So, the object isn’t re-created on every render.


https://esbench.com/bench/58e7f6e899634800a0347ca1 shows object.assign vs obj literal perf

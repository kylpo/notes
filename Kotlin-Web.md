# KotlinJS
## Attempt to get Linaria's babel-transform working
- Used [create\-react\-kotlin\-app](https://github.com/jetbrains/create-react-kotlin-app) and `eject`ed to be able to customize webpack and babel.
- Added to babel in `package.json`
- Finally figured out how to add Linaria to Kotlin code using `@JsModule` and `external`

```kt
@JsModule("linaria")
external val linaria: Linaria

external interface Linaria {
    fun css(css : String)
}

val intro = linaria.css("background-color: red")

class App : RComponent<RProps, RState>() {
    override fun RBuilder.render() {
        div("App-header") {
            logo()
            h2 {
                +"Welcome to React with Kotlin"
            }
        }
        p("App-intro, $intro") {
            +"To get started, edit "
            code { +"app/App.kt" }
            +" and save to reload."
        }
        p("App-ticker") {
            ticker()
        }
    }
}
```

Above works for runtime Linaria, but not babel-time, because the produced `js`  does not have a Tagged Template Literal.

So, I tried just writing javascript in kotlin with ([Calling JavaScript from Kotlin \- Kotlin Programming Language](https://kotlinlang.org/docs/reference/js-interop.html)):

```kt
js("linaria.css`background-color: red`")
```

But no luck. It errors at first backtick as "invalid js". Asking around on Slack, I learned that kt2js creates ES5 code. ES6 is a feature request that will be worked on "only after we will finish migrating to the new compiler infrastructure. Not very soon." according to Zalim Bashorov.

Follow progress at this issue: [JS: support ES6 as compilation target : KT\-8373](https://youtrack.jetbrains.com/issue/KT-8373#tab=Comments)

### Next Steps
Try a transform on the Kotlin code with Gradle? Or try to get Linaria to transform `css()` functions, too?

Each option probably takes too much time. May as well stick to `js` or `ts` for frontend code. I might decide to share business logic using Kotlin though.

## Findings
- Kotin -> js code lives in `node_modules/.cache/kotlin-webpack/kotlinApp.js` and was produced from a [kotlin-webpack-plugin](https://github.com/JetBrains/create-react-kotlin-app/tree/master/packages/kotlin-webpack-plugin) lib which is used in the webpack config.
- Also uses a javascript frontend to run it's compiler, called [kotlinc-js-api](https://github.com/JetBrains/create-react-kotlin-app/tree/master/packages/kotlinc-js-api).
- Kotlin is not supported in Webstorm. Only IntelliJ Idea ($$$) works with this stack.

## Example Repos
- [GitHub \- JetBrains/kotlinconf\-app: KotlinConf Schedule Application](https://github.com/JetBrains/kotlinconf-app)
- [create\-react\-kotlin\-app](https://github.com/jetbrains/create-react-kotlin-app)
- [gbaldeck/vue\.kt: A Kotlin wrapper and PWA starter for Vue\.js\.](https://github.com/gbaldeck/vue.kt)
- [JetBrains/kotlin\-wrappers: Kotlin wrappers for popular JavaScript libraries](https://github.com/JetBrains/kotlin-wrappers)
- [Kotlin/kotlin\-fullstack\-sample: Kotlin Full\-stack Application Example](https://github.com/Kotlin/kotlin-fullstack-sample)

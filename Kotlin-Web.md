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

## How to get Constelation's AOT functionality in Kotlin?

### Extension Functions?
Can I just add `View` to `RBuilder` as an extension function? It said somewhere that these are done statically. Maybe???

Nope! Statically in the sense that they are not added to classes. Instead they are added as `static` methods. A class is passed in the the static method under the hood.

Point is, all `View` code would still run on the client.

#### References
- [Extensions \- Kotlin Programming Language](https://kotlinlang.org/docs/reference/extensions.html)
- [Static extension methods in Kotlin \- Stack Overflow](https://stackoverflow.com/questions/28210188/static-extension-methods-in-kotlin)
- [The Ugly Truth about Extension Functions in Kotlin – AndroidPub](https://android.jlelse.eu/the-ugly-truth-about-extension-functions-in-kotlin-486ec49824f4)
- [How do extension functions work? \- Kotlin Discussions](https://discuss.kotlinlang.org/t/how-do-extension-functions-work/609)

## Well how is Jet Brains doing css-in-js?
They aren't. Good ole static css. Bummmmmer.

[kotlinconf\-app/style\.css at master · JetBrains/kotlinconf\-app](https://github.com/JetBrains/kotlinconf-app/blob/master/web/src/main/web/style.css)

### Generate code with Annotations?
Can I use kapt to generate the css files?

No, annotations are used to auto-generate kotlin and bytecode classes, not for something like css files. Also, recently, people have [complained](https://discuss.kotlinlang.org/t/kapt-and-generating-kotlin-rather-than-java/2542/4) about gradle task times for kapt.

#### References
- [Hello World of Annotation Processing in Kotlin – ProAndroidDev](https://proandroiddev.com/hello-world-of-annotation-processing-in-kotlin-3ec0290c1fdd)
- [Using kapt \- Kotlin Programming Language](https://kotlinlang.org/docs/reference/kapt.html)

### How does `vue-kotlin` do it?
[vue\-kotlin \| Libraries and tools supporting the use of Vue\.js in Kotlin\.](https://nosix.github.io/vue-kotlin/) has a `translate()` function which creates a `.vue` file.

Cool!

Buuut, the user of the lib needs to call it at the end of their code. As shown [here](https://github.com/nosix/vue-kotlin/blob/ac6fe5447cd751d8a680a7d37f252c593cc525fd/single-file/greeting-component/main/GreetingComponent.kt):

```kotlin
external class GreetingComponent : Vue {
    var greeting: String
}

class GreetingComponentVue : ComponentVue<GreetingComponent> {

    override val template: String = """<p>{{ greeting }} World!</p>"""

    override val style: StyleBuilder = {
        p {
            fontSize = 2.em
            textAlign = center
        }
    }

    override val script: ComponentOptionsBuilder<GreetingComponent> = {
        data = Data {
            json<GreetingComponent> {
                greeting = "Hello"
            }
        }
    }
}

@Suppress("unused")
val options = translate(GreetingComponentVue())
```

Bummmmmer!

### Transform the code
OK, so Kotlin has a compiler which converts kotlin to js. Surely there must be a way.

[Any plans for something like Groovy\-style AST transformations? \- Kotlin Discussions](https://discuss.kotlinlang.org/t/any-plans-for-something-like-groovy-style-ast-transformations/752)

> Yes, we are planning to support AST transformaions, and make them a public API at some point. - Oct of 2012

> Yes, something along these lines is planned - Aug of 2013

> AST transformations are not on our medium-term roadmap at this time, but it’s possible that they will appear in a later version at some point. - Nov of 2016

./flip-table

An API does not exist, but the language architect mentions we have all that is needed in the Kotlin compiler, REPL, and IDE plugins. Look for the `ExpressionTypingVisitor` and classes prefixed with `Jet`. [abstract syntax tree \- How to get Kotlin AST? \- Stack Overflow](https://stackoverflow.com/questions/32664842/how-to-get-kotlin-ast) is the best starting point, including this parser exploration: [kotlin\-script\-parser\-test/CompileTest\.kt at master · vektory79/kotlin\-script\-parser\-test](https://github.com/vektory79/kotlin-script-parser-test/blob/master/src/main/java/hello/CompileTest.kt)

So, long answer is: YES! This all can be done. ..With a lot of work. Worth it? I thought so, until I realized I'd need to build something similar for Apollo's AOT optimizations and any future js tools that rely on it.

#### References
- [kotlin/idea/idea\-repl/src/org/jetbrains/kotlin/console at master · JetBrains/kotlin](https://github.com/JetBrains/kotlin/tree/master/idea/idea-repl/src/org/jetbrains/kotlin/console)
- [kotlin\-js\-example/build\.gradle at master · bascan/kotlin\-js\-example](https://github.com/bascan/kotlin-js-example/blob/master/build.gradle)
- [kotlin/Tasks\.kt at master · JetBrains/kotlin](https://github.com/JetBrains/kotlin/blob/master/libraries/tools/kotlin-gradle-plugin/src/main/kotlin/org/jetbrains/kotlin/gradle/tasks/Tasks.kt)
- [kotlin/js at master · JetBrains/kotlin](https://github.com/JetBrains/kotlin/tree/master/js)
- [Working with the Command Line Compiler \- Kotlin Programming Language](https://kotlinlang.org/docs/tutorials/command-line.html)
- [VerachadW/kraph: GraphQL request string builder written in Kotlin](https://github.com/VerachadW/kraph)

### Conclusion
JS is still too new and moving to quickly for Kotlin to keep up. It has the base case story, but not enough edges cases. Edge cases that I completely rely on the build performant code in a friction-less way.
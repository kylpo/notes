Storing widgets in xml sucks. Not able to quickly comment attributes. So, do it in runtime and have to remember the id? That sucks, too.

Try Anko

---

## Pros:
- composable functions
- real code
- easy to comment attributes
- doesn't need ids, for the most part
- layout variation stays in same file with a simple if statement

## Cons:
- No built-in databinding
- lparams defined after block with children really hurts skim-ability
- constraintlayout requires id, so you need to define them in res/ids
- doesn't seem like any of the big names for Android dev are using it

Themeing, but this is mostly solved.

lparams. To avoid this, declare components as vals above, then nest below w/ the vals.

Seems fairly abandoned: see menus PR from 1 year ago (https://github.com/Kotlin/anko/pull/324)

Only really one dev (https://github.com/yanex), who is not currently working on it. Koan was original project.


https://news.ycombinator.com/item?id=9519787 related

## Using Anko Layouts
https://www.lynda.com/Kotlin-tutorials/Anko-layouts-Basics/642478/710019-4.html

https://www.slideshare.net/mdevtalk/david-bilk-anko-modern-pstup-k-tvorb-layout
- page 82 for custom views
- page 107 for styling/themeing
- page 111 for custom view attributes via custom extensions
- page 124-130 for configurations
- page 162 for disadvantages
- page 188 for tips (like using ids so View state is retained)

Try to build MyViewUI with a broader generic, like:
`class MyViewUI : AnkoComponent<View> { }  // or AnkoComponent<Context>`

or
`open class MyViewUI : AnkoComponent<out T> {}   // Like Event.kt`


ViewHolder: https://github.com/Kotlin/anko/issues/194
Custom Components w/ Anko: https://github.com/Kotlin/anko/issues/267#issuecomment-292225368

## Alternative libraries
https://github.com/zserge/anvil
- UI is in code
- Nice syntax, better thank Anko's: (https://github.com/zserge/anvil-examples/blob/master/todo-kotlin/src/main/kotlin/com/example/anvil/todo/TodoView.kt)
- Reactive w/ virtual-ish DOM
- Maintenance is spotty :(
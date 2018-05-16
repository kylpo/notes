Storing widgets in xml sucks. Not able to quickly comment attributes. So, do it in runtime and have to remember the id? That sucks, too.

Try Anko

---

Pros:
- composable functions
- real code
- easy to comment attributes
- doesn't need ids, for the most part
- layout variation stays in same file with a simple if statement

Cons:
- No built-in databinding
- lparams defined after block with children really hurts skim-ability
- constraintlayout requires id, so you need to define them in res/ids
- doesn't seem like any of the big names for Android dev are using it

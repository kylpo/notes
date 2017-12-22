_WIP_

[Interview with Jesper Louis Andersen about Erlang, Haskell, OCaml, Go, Idris, the JVM, software and…](https://notamonadtutorial.com/interview-with-jesper-louis-andersen-about-erlang-haskell-ocaml-go-idris-the-jvm-software-and-b0de06440fbd)

> The type system saves you countless hours on syntax and type errors. It’s like a spell checker for your program.
https://mat.tm/joy/

# The test:
Header using Text's union string prop
- can it add to the union?

## Typescript
- works perfectly except intellisense in string of inherited prop. Suggests nothing. Properly intellisenses prop and string vals at prop level though.
  - `interface IProps extends HeadaerProps {}`

# Types in general
- [Patrick Stapfer on Twitter: "First super simple example I tried... From left to right #TypeScript -> #Flow -> #ReasonML ... I prefer 100% over 80% in my type system https://t.co/lVMvRMXBmX"](https://twitter.com/ryyppy/status/869208354371010560)
  - [Sven SAULEAU on Twitter: "@ryyppy wow TIL: TypeScript has no inference whatsoever. 👇is completely fine since implicit any. https://t.co/ohOiZZAUtM"](https://twitter.com/svensauleau/status/869211688746274817)
  - [Roman Zanettin 🇨🇭 on Twitter: "@ryyppy @Jakeherringbone @svensauleau that's what make me happy and confident in TS. do not rely on inference and know that i have to type 100% to get the best result 😊"](https://twitter.com/roman_zanettin/status/869279235621494784)
- [Roman Liutikov on Twitter: "@svensauleau It's about type inference like in OCaml and writing types everywhere in Java."](https://twitter.com/roman01la/status/863727468276047873)
  - [Sven SAULEAU on Twitter: "@roman01la Yes I see, Java is aware of this and recently added very limited type inference https://t.co/BNRMuFh2PE"](https://twitter.com/svensauleau/status/863729233415294977)

# Type Inference
- "Type inference doesn't mean code is unreadable. The opposite. It means *everything* becomes readable, not just the manually annotated code!" - [@jordwalke](https://twitter.com/jordwalke/status/874525331171848192)

![](https://pbs.twimg.com/media/DCLviWFUMAAciZV.jpg)

- "we have to infer reason types when code reviewing =/" - [the unlearner on Twitter](https://twitter.com/meoyawn/status/881148463907561472)
  -  "Let's make better code review tools that show us the types! I'm working on something related right now" - [Jared Forsyth on Twitter](https://twitter.com/jaredforsyth/status/881149609728454656)
- type inference, as discussed at ~18:00 of http://androidbackstage.blogspot.com/2017/05/episode-66-kotlin.html
- [MJS \#010: Richard Feldman \- All JavaScript Podcasts by Devchat\.tv](http://pca.st/vXbs#t=1411) ~23:30

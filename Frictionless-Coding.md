_WIP_

- define friction
  - some friction is necessary for maintainable code
  - anything that causes pause while coding, whether these are short moments like scrolling down a page to see see the render, or bigger moments that make you say "ugh" every time

- first target "coding without friction", then evolve to "coding with joy", or something like that
  - thought about this from title of https://pavelfatin.com/typing-with-pleasure/

- imports
  - importjs to the rescue
  - note: ts has something like this in the works

- autoformatting
  - [prettier](https://github.com/prettier/prettier) (someday)
    - "Prettier could enable two things:
      1. Lens-- let code match the eye of the beholder
      2. Law-- enforce the format of checked-in code"
      https://twitter.com/shaunlebron/status/820363199665029121
  - semicolons used to be a point of friction, so I stopped. Now prettier brings them back, but I don't have to type it

- defensive coding
  - types enable me to not null-check everything

- navigating code
  - why I'm stuck in vim
    - I keep trying more modern editors like vscode and atom, but always fall back to vim for its buffers/splits and vinegar.vim approach to opening and traversing files.

- declarative code as much as possible
  - able to go from a Sketch file to real apps by just "describing" what I'm looking at

- less abstractions, more copy/pasting
  - anti-DRY
    - find that you are repeating code 3+ times before considering creating an abstraction

- two modes: speed and quality
  - friction changes between these modes
  - Speed. not velocity, because it is going fast in multiple directions, often going in reverse. Finally ending in a "right" direction.
  - Quality _after_ direction found and feature built. For cleaning up code, documenting, enabling future maintenance.

- testing
  - relieves friction by showing breaking changes as they happen if you have good coverage
  - adds to friction when testing too early. Speed mode means you'll write whole suites of tests that may no longer apply when changing direction

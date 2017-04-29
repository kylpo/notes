_WIP_

# size
- redux is tiny, but realistically, you'll need to add thunk/saga, immutable (60KB), and reselect, which sum up to a lot
- mobx is 53KB
- [Hassan Bazzi on Twitter: "A month of active development & still going strong thanks to #webpack code splitting & tiny libs (<3 @preactjs ). Now to get rid of Redux... https://t.co/da2Xh0bCW7"](https://twitter.com/habazzi/status/842285642444812288)

# Redux
- [jevakallio/redux-offline: Build Offline-First Apps for Web and React Native](https://github.com/jevakallio/redux-offline)
- ["Redux looks far more useful when viewed not as an app state management solution, but a protocol for different libraries to operate on state."](https://twitter.com/VilleImmonen/status/854335136900550656)
  - "Now tools made for Redux can be used with those libraries. Persist the state to disk? Got it. Transactions? Yup. Dev tools, logging? Check."

---

Where Redux is extremely explicit about how data travels through components and its state store, MobX is abstracts away many of those details

Where Redux is based on immutability of data, MobX leverages mutable data to enhance performance and to make the code arguably simpler to read.

http://engineering.pivotal.io/post/tdd-mobx/

redux boilerplate: writing actions, writing reducers, creating containers that are connected to the store

---

no longer worth reading Redux articles. Everytime I finish reading it, I think, "wow, that is so cool! And so complex! Why not just use mobx?"

even one of the original Redux fans (coined Ducks pattern) is on the mobx train now https://twitter.com/erikras/status/821831283089305602

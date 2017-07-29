_WIP_

# React Native
You can, but should you?

- [You’ve got React Native all wrong – DailyJS – Medium](https://medium.com/dailyjs/youve-got-react-native-all-wrong-3b268eca99f4)
- [Investigating React Native – Twitch Blog](https://blog.twitch.tv/investigating-react-native-6032ecced610)
  - great list of cons to React Native
- [ReactJS News on Twitter: "What React native components do you wish existed, or had a better component api?"](https://twitter.com/ReactJSNews/status/862330083134115840)
  - "Notifications and ART/SVG"
  - "Cross platform native routing solutions. Built in animations and animated components."
  - "Cross platform ActionSheet"

# Reasons against RN
- Android Vitals Dashboard in the Play Console
  - also, future tooling and debugging efforts
- [You can tell which apps are built on React Native from the app size. 200MB - 300MB seems common. A full featured true native app: ~50MB](https://twitter.com/MugOfPaul/status/862659087254773761)
  - I think this refers to on Android though, not ios
- [Integrating React Native with Native Infrastructure - Mehdi Mulani at @ReactEurope 2017 - YouTube](https://www.youtube.com/watch?list=PLCC436JpVnK3KpieWtxYN6aC2-exR_IxH&v=QOAoLF6FV7A)
- Perf
  - wix still employs native engineers to avoid the bridge. See [tal's talk](https://youtu.be/OmiXlJ4ZzAo?t=20m27s)
- [An iOS Dev’s Experience with React Native – Made by Windmill](https://blog.madebywindmill.com/an-ios-devs-experience-with-react-native-559275b5a4e8)
- Swift and Kotlin are pretty damn good
  - As js has gotten better with ES2015, so too have native languages
- Seems like those that care about perf drop down to native anyways
  - [Intro to React Native for an iOS Developer - Artsy Engineering](http://artsy.github.io/blog/2017/07/06/React-Native-for-iOS-devs/#React.Native) and [Doing it right per platform](http://artsy.github.io/blog/2017/07/06/React-Native-for-iOS-devs/#Doing.it.right.per.platform)
    - "For most users of React Native, native development has always been unavailable to them, and now it's not, because React Native has lowered the barrier to entry. This means many people are aiming to make cross-platform React Native apps that are entirely in JavaScript ( see Create React Native App. ) They are just trying to get something shipped, which could be different from what you the reader are probably doing. As a native dev, you're probably more interested in making something really fit the platform and shine. Lots of probablys, yes, but it fits the questions we're being asked."

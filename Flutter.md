[What’s Revolutionary about Flutter – Hacker
Noon](https://hackernoon.com/whats-revolutionary-about-flutter-946915b09514) explains how Flutter differs from React
Native

Since Flutter widgets are sent as part of your app (Flutter doesn't use OEM widgets), it does increase your app's
size.
> Moving the widgets and the renderer into the app does affect the size of the app. The minimum size of a Flutter app on Android is approximately 6.7MB, which is similar to minimal apps built with comparable tools. It is up to you to decide if the benefits of Flutter are worth any tradeoff, so the rest of this article discusses these benefits.

Also, a commenter had some great questions:
> How does it interact with the platform? Namely, how are UI states saved between orientation changes and when the system decides to kill the app? How are they restored when the app is restored?
> How are system UI things implemented like copy&paste?
> How about new features like the 'address selection feature’ of Android Oreo? Will they get implemented at all, or are users just left out?
> Splash screens / window drawables : can we use them or do we depend on Flutter to be fully loaded before we can show anything?
> Tooling: IntelliJ is great, but a visual layout editor for developers & designers is kind of a big deal. When will we see something like this? Here I think Flutter could be the best, especially when pulling in all custom-made Flutter widgets from GitHub. App store for widgets! :D

# Against Flutter
- No Instant Apps: no way to separate app, also Flutter adds size to apks
- No launcher widgets (built in Flutter, that is)

# Open Issues
- [Inline Maps support · Issue \#73 · flutter/flutter](https://github.com/flutter/flutter/issues/73)
- [Instance state not saved when app is killed by OS · Issue \#6827 · flutter/flutter](https://github.com/flutter/flutter/issues/6827)

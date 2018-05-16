
# Why I like it
Steel is Democratic metal, just like android.

![](https://o.aolcdn.com/images/dims?quality=100&image_uri=http%3A%2F%2Fwww.blogcdn.com%2Fwww.engadget.com%2Fmedia%2F2013%2F10%2Fdsc08051.jpg&client=cbc79c14efcebee57402&signature=aa83a04c9bf4894207acf309a6bfaf09ffc7c15c)

from [Lenovo's 'Yoga' Android tablet has a built\-in kickstand containing an 18\-hour battery \(hands\-on\)](https://www.engadget.com/2013/10/29/lenovo-yoga-tablet-hands-on/)

Asus Transformers

As a developer, I like android because it lets my imagination run wild! Lock screen apps, instant apps, widgets,
overlays, all the things!

# Why I'm falling in love with Android all over again
Recently, I've been researching OS platforms and their capabilites. Because I landed on MacOS as the best desktop and power user option, I thought I should give iOS another hard look. Also, not gonna lie, the ARKit is compelling. What I learned in my iOS vs Android is that Android is just so well positioned to continue dominance.

Floating windows, lapdock, etc. Termux, AIDE. mouse support.

I'd love to be able to go all-in on Android as an experiment. Just wish there were good android tablets. Also wish Google would make Android devleopment ON an Android device a first-class priority.

Give me an android "Surface"!!!!

# Dev
## Best Practices and Conventions
- [android\-guidelines/project\_and\_code\_guidelines\.md at master · ribot/android\-guidelines](https://github.com/ribot/android-guidelines/blob/master/project_and_code_guidelines.md)
- [futurice/android\-best\-practices: Do's and Don'ts for Android development, by Futurice developers](https://github.com/futurice/android-best-practices)

## android.widget vs android.app
android.widget - mechanism
- shows state to the user
- reports user interaction events to higher level portions of app

## Android's own "VirtualDOM" (how widgets are drawn)
Android has its own form of Virtual DOM, called DisplayList. It is a representation of a tree of rendering commands for
a view that was invalidate()d, traversal()d. This optimization took over the old draw() imperative command.

Java side produces diff of changes, then render thread takes over to apply those changes with the gpu (to
canvas/opengl).

Render Thread: thread responsible for issuing display list operations to GPU. It only talks to GPU, nothing else.

android.app - policy (fragments, activities)
- defines WHAT state to bind to widgets
- HOW to respond to user interaction and HOW to issue changes to model

## Questions I had
#### Layouts in XML? Or programmatic?
- [Anko Layouts · Kotlin/anko Wiki](https://github.com/Kotlin/anko/wiki/Anko-Layouts#why-a-dsl)
- Programmatic is a bit better for performance
- XML can use the visual layout builder. Programmatic does not.

#### Use Google Drive to sync apps across device?
Not really possible. Drive is used to backup and restore.

#### Clean Architecture?
All about making Tests fast, isolated, repeatable. Each layer only cares about one thing.

More notes:

Their prescribed architecture pattern is MVVM (Model-View-View Model) and it uses the ViewModel to source data from a repository, apply presentation logic and pass it to the view using LiveData.

could become bloated with the business logic required to map together these disparate data sources

Nice images here, too: https://medium.com/@thereallukesimpson/clean-architecture-with-mvvmi-architecture-components-rxjava-8c5093337b43


Data layer is represented by Repository interfaces. All data needed for the application comes from this layer. Each repository works with a single, well-defined aspect of application (users, messages, events inbox, etc)

Domain layer’s element is UseCase. UseCase’s role is to combine data layer elements to perform a combination of data operations.

- Business rules here: all the logic happens in this layer. Regarding the android project, you will see all the interactors (use cases) implementations here as well.
- This layer is a pure java module without any android dependencies. All the external components use interfaces when connecting to the business objects.

https://blog.uptech.team/clean-architecture-in-android-with-kotlin-rxjava-dagger-2-2fdc7441edfc

https://fernandocejas.com/2014/09/03/architecting-android-the-clean-way/

https://github.com/android10/Android-CleanArchitecture

./gradlew runUnitTests - Execute domain and data layer tests (both unit and integration).

./gradlew runAcceptanceTests - Execute espresso and instrumentation acceptance tests.


A ViewState is just a data container, holding all the information the view needs to render himself.
-  the view is observing changes in a ViewState objects. These ViewStates are delivered by LiveData objects. The LiveData objects being updated, and are part of, a presenter.

ViewModel has the ViewState, and updates it for the View to observe. It is a data class within the ViewModel.

https://proandroiddev.com/a-guided-tour-inside-a-clean-architecture-code-base-48bb5cc9fc97


## Misc
- [20\+ Awesome Open\-Source Android Apps To Boost Your Development Skills](https://blog.aritraroy.in/20-awesome-open-source-android-apps-to-boost-your-development-skills-b62832cf0fa4)
- [Android Developers Blog: Google releases source for Google I/O 2017 for Android](https://android-developers.googleblog.com/2017/08/google-releases-source-for-google-io.html)
- [Android Distribution: A 5 Year Look at Android Version Adoption](http://www.droid-life.com/2017/08/09/android-o-almost-heres-android-distribution-past-5-years/)
  - ![](http://www.droid-life.com/wp-content/uploads/2017/08/android-distribution-stacked.jpg)
- [Florina Muntenescu on Twitter: "\#Kotlin \+ ViewModels \+ Room \+ \#RxJava = 👩‍💻❤️ New sample here: https://t\.co/BbDUokgCLC \#AndroidDev"](https://twitter.com/FMuntenescu/status/895295774220800001)
- [pedrovgs/AndroidWiFiADB: IntelliJ/AndroidStudio plugin which provides a button to connect your Android device over WiFi to install, run and debug your applications without a USB connected\.](https://github.com/pedrovgs/AndroidWiFiADB)
  - no need to keep your phone connected to your laptop anymore...
## Debugging
  - [Android Performance: An Overview (Google I/O '17) - YouTube](https://www.youtube.com/watch?v=Qfo5fdoXrTU)
    - systrace from `catapult` repo
    - `gfxinfo` + UI Automation = <3
      - set up early in your app building flow with CI
  - [Android Developers Blog: Android Studio 3.0 Canary 1](https://android-developers.googleblog.com/2017/05/android-studio-3-0-canary1.html)
## Architecture Components
  - [Android Developers Blog: Android and Architecture](https://android-developers.googleblog.com/2017/05/android-and-architecture.html)
  - [Exploring the new Android Architecture Components library](https://medium.com/@hitherejoe/exploring-the-new-android-architecture-components-c33b15d89c23)
  - [Joaquim Ley on Twitter: "Excited to get this article out 🙌 Android Architecture Components + MVVM + Open source - #androiddev #mvvm https://t.co/bdn0xxzXfg"](https://twitter.com/JoaquimLey/status/869834859241406464)
  - [Create a Clean\-Code App with Kotlin Coroutines and Android Architecture Components](https://blog.elpassion.com/create-a-clean-code-app-with-kotlin-coroutines-and-android-architecture-components-f533b04b5431)
## MVVM and data binding
- [Applying Data Binding for Views · codepath/android\_guides Wiki](https://github.com/codepath/android_guides/wiki/Applying-Data-Binding-for-Views)
- [Approaching Android with MVVM – ribot labs](https://labs.ribot.co.uk/approaching-android-with-mvvm-8ceec02d5442)
## Wear
  - [From Actions to battery life, these updates will make Android Wear 2.0 even better](https://www.wareable.com/android-wear/android-wear-updates-actions-battery-life-456)
    - "Did you also know that an all-white display can use up to seven times more power than a black display in interactive mode?"
    - "It also wants developers to be smarter with design choices to reduce battery suck, including making use of ambient mode and using fewer animations"
    - "did you know that Bluetooth is way more battery intensive than LTE or Wi-FI? Well it is, and Google wants developers to use the latter when possible to transfer data to Wear devices. It also wants developers to reduce the amount of vibrations and location checks."
## Animation
  - [Nick Butcher on Twitter: "ConstraintSets + Transitions are 🤘 That's basically how we built this interaction in the I/O app. https://t.co/KiSpdKLS4e https://t.co/PhlVGXn3Wj"](https://twitter.com/crafty/status/867376535019368448)
  - [Nick Butcher on Twitter: "Here are the slides from @doris4lt and my #AnDev360 advanced Android animation talk (hit ℹ️ for notes): https://t.co/lVeLUBfQnI"](https://twitter.com/crafty/status/887298579483824128)
  - [Bringing smooth animation transitions to Android – David Ganster – Medium](https://medium.com/@david.gansterd/bringing-smooth-animation-transitions-to-android-88786347e512)
  - [Bodymovin to Android – Google Design – Medium](https://medium.com/google-design/bodymovin-to-android-6e53e5f7a96)
  - [Learn Some New Moves – Nick Butcher – Medium](https://medium.com/@crafty/learn-some-new-moves-b8aad7828014)
## Accessibility
  - [Developing Accessible Apps for Blind and Visually-Impaired Users](https://www.youtube.com/watch?v=1by5J7c5Vz4)
  - [Developing Accessible Apps for Users with Motor Impairments](https://www.youtube.com/watch?v=ElifzykHt7U)
## Navigation
  - [A Primer on Android navigation – Google Design](https://medium.com/google-design/a-primer-on-android-navigation-75e57d9d63fe)
## Platform Features
- [Dieter Bohn on Twitter: "I can’t tell you how much I love these draggable shortcuts in Android. Wait I can: I love them a lot. https://t.co/m8yCpO33lK"](https://twitter.com/backlon/status/890276148399046656)
## Instant Apps
- New `Try Now` option in play store

#### Daydream / Screen Saver
- [How to Set Up Android's Daydream Screensaver](https://www.tomsguide.com/us/android-daydream,review-3306.html)
- [Android SDK: Create an Interactive Screen Saver with Daydream](https://code.tutsplus.com/tutorials/android-sdk-create-an-interactive-screen-saver-with-daydream--mobile-16604)

#### Hotkeys and remapping
- Hardware button remapping
  - [Remap Android's Hardware Buttons Without Root \[How\-To\] \- YouTube](https://www.youtube.com/watch?v=FwLeGdQqh_0)
  - [Button Mapper: Remap your keys \- Android Apps on Google Play](https://play.google.com/store/apps/details?id=flar2.homebutton&hl=en)
- Bluetooth keyboard remapping
  - [How to Use a Bluetooth Keyboard with Your Android Device](https://www.howtogeek.com/175267/the-htg-guide-to-using-a-bluetooth-keyboard-with-your-android-device/)
  - [External Keyboard Helper Demo \- Android Apps on Google Play](https://play.google.com/store/apps/details?id=com.apedroid.hwkeyboardhelperdemo&rdid=com.apedroid.hwkeyboardhelperdemo)


## Icons
  - [Nick Butcher on Twitter: "Check out my 🔥 tips for implementing adaptive icons https://t.co/tWYAHKSmnx"](https://twitter.com/crafty/status/885122099626594304) whole thread is helpful
  - [Understanding Android Adaptive Icons – Google Design – Medium](https://medium.com/google-design/understanding-android-adaptive-icons-cee8a9de93e2)
  - [Designing Adaptive Icons – Google Design – Medium](https://medium.com/google-design/designing-adaptive-icons-515af294c783)
  - [nickbutcher/AdaptiveIconPlayground: An Android app for experimenting with Adaptive Icons.](https://github.com/nickbutcher/AdaptiveIconPlayground)
  - [Implementing Adaptive Icons – Google Developers – Medium](https://medium.com/google-developers/implementing-adaptive-icons-1e4d1795470e)
  - ![](https://github.com/nickbutcher/AdaptiveIconPlayground/raw/master/screenshots/adaptive-icon-playground-demo.webp)
## Testing
  - [Android Developers Blog: Android Testing Support Library 1.0 is here!](https://android-developers.googleblog.com/2017/07/android-testing-support-library-10-is.html)
  - [Automated Android Testing With Kotlin \- DZone DevOps](https://dzone.com/articles/automated-android-testing-with-kotlin)
  - [Knowledge boost for junior Android developers — Part II](https://android.jlelse.eu/knowledge-boost-for-junior-android-developers-part-ii-e62ae5154160#5106)
    - Monkey Tests, Instrumented Tests, StrictMode, Firebase Test Lab, LeakCanary, Google's Test Procedures

[Dimensions](https://dimensionssprint.withgoogle.com/)
- [Dimensions: Uniquely Android - YouTube](https://www.youtube.com/watch?v=J4pQK2463qs)
  - about openness of the platform: sharing, replacing defaults, broadcasting events, etc. Basically everything that made me choose Android from the start.

# Play Store
- [Launching An App? Make App Store Optimization Your Foundation For Growth – Smashing Magazine](https://www.smashingmagazine.com/2017/08/launch-app-store-optimization-growth/?utm_source=mobilewebweekly&utm_medium=email)

# My Android setup
## Chrome config
- [How to customize Chrome's terrible New Tab page](http://www.androidpolice.com/2017/04/27/customize-chromes-terrible-new-tab-page/)
- chrome://flags#ntp-condensed-layout - enabled
- #enable-chrome-home


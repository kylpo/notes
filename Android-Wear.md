Note: Below's notes are just summarizing [Introduction \- Android Wear \- Android Wear design guidelines](https://www.google.com/design/spec-wear/android-wear/introduction.html). Be sure to flip through those pages.

# Architecture
Android Wear 2.0 is all about 1-dimensional, vertical columns. Horizontal can still play a role, but it is secondary, and lives inline to the vertical column (think carousels).

![](https://storage.googleapis.com/material-design/publish/wear_v_3/assets/0B5QhgrCEXHzxZExrQUxveTFTa2s/optimize_for_vertical_layout_1.png) vs ![](https://storage.googleapis.com/material-design/publish/wear_v_3/assets/0B5QhgrCEXHzxNW1aLUFGanJWNjA/optimize_for_vertical_layout_2.png)

## 3 Primary Stages
### Main
Your default column houses your `Watch Face` at the top, and any `notifications` below it.

### Notification Detail

### App

# Display Modes
## Active Mode
Shows all, bright colors and animations. You just pressed something to wake up the watch.

![](https://storage.googleapis.com/material-design/publish/wear_v_3/assets/0B2SJIKn8-BKoMzMxWlRWd0JvU3c/pfadm-01.png)

## Always-on Mode (also called Ambient Mode)
![](https://storage.googleapis.com/gweb-uniblog-publish-prod/original_images/Android-Wear-watches.gif)

Dims screen to grayscale to conserve battery. The more black space on the screen, the more battery is saved.

![](https://storage.googleapis.com/material-design/publish/wear_v_3/assets/0B2SJIKn8-BKoNF9aRzdSci1mSTg/pfadm-02.png)

Note: Apps can take advantage of this, too! No longer just the Face.
- By default your app in ambient mode only updates the screen every minute. This can be changed for time-sensative matters like timers and running apps.
- Read [Keeping Your App Visible \| Android Developers](https://developer.android.com/training/wearables/apps/always-on.html) for more.
- Watch [How to: Use Always\-on Apps with Android Wear \- YouTube](https://www.youtube.com/watch?v=_-xYB9EBTaA) for examples.

![](https://1.bp.blogspot.com/-Jz1tjR2Ouyc/VYyZ9thRtmI/AAAAAAAAAhE/wajr8jHut4Q/s320/Screen%2BShot%2B2015-06-25%2Bat%2B5.16.24%2BPM.png)

from [Official Android Blog: Android Wear: Always\-on apps](https://android.googleblog.com/2015/06/android-wear-always-on-apps.html)

# App Capabilities
- Watch this [fake climbing app](https://youtu.be/Hw37dxW6q5g?t=27m12s) demonstrating many capabilities
- Apps can be built as `Standalone` and installed directly from watch, not needing a paired phone. This opens more doors for the iOS story.

# App Dev
- Watch [Android Wear 2\.0: Building Apps with Material Design \- Google I/O 2016 \- YouTube](https://www.youtube.com/watch?v=LtD7eJp2ILo)
- [Creating and Running a Wearable App \| Android Developers](https://developer.android.com/training/wearables/apps/creating.html)



# Performance
  - [From Actions to battery life, these updates will make Android Wear 2.0 even better](https://www.wareable.com/android-wear/android-wear-updates-actions-battery-life-456)
    - "Did you also know that an all-white display can use up to seven times more power than a black display in interactive mode?"
    - "It also wants developers to be smarter with design choices to reduce battery suck, including making use of ambient mode and using fewer animations"
    - "did you know that Bluetooth is way more battery intensive than LTE or Wi-FI? Well it is, and Google wants developers to use the latter when possible to transfer data to Wear devices. It also wants developers to reduce the amount of vibrations and location checks."
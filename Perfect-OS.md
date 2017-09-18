
TODO: Take notes on Samsung Gear

---

Hard to write this, as there are so many things to consider.

Comes down to hardware (capabilities, size, context),
type of users, (power user or not)
and ___

Combine all I've learned into one post.

I just spent the week researching Windows, MacOS, Android, iOS, Android Wear, etc. I'd like to end the week with identifying all the things I liked about these platforms, and identify what I believe the ideal OS would be for right now.

---

# OS Posts
Evaluating ___ As a Platform
- Windows 10, MacOS, Android, ...

Comparing Android vs iOS as Platforms
Comparing Gear OS vs Android Wear as Platforms

---

I'd like to share with you features of what I think the "perfect" operating system would have. If not for randomly landing in the feed of those that are actually building these things, then just for a reference to my friends and future self. 


the people I talk about this with. I can stop saying "if only" with a fist in the air, and just sink it in to this document.

---

# Why I'm falling in love with Android all over again
Recently, I've been researching OS platforms and their capabilites. Because I landed on MacOS as the best desktop and power user option, I thought I should give iOS another hard look. Also, not gonna lie, the ARKit is compelling. What I learned in my iOS vs Android is that Android is just so well positioned to continue dominance.

Floating windows, lapdock, etc. Termux, AIDE. mouse support.

I'd love to be able to go all-in on Android as an experiment. Just wish there were good android tablets. Also wish Google would make Android devleopment ON an Android device a first-class priority.

Give me an android "Surface"!!!!

---

# Platform Capabilities
List the APIs and extension points of platforms like Mac, Windows, ios, Android, chrome, etc.

First, google to see if someone else has started this work.

Might consider making it a site that can be easily searched around for (also use tagging). Something like https://csstriggers.com/ or caniuse.com

https://uxplanet.org/cross-platform-guidelines-1c7675ec1d0c

---

# Progressive OS

Thinking about the progression of devices and progression of users. Children grow into desktop, professional tools.

AK: Well, a saying I made up at PARC was, “Simple things should be simple, complex things should be possible.” They’ve got simple things being simple and they have complex things being impossible, so that’s wrong.

https://medium.com/fast-company/the-father-of-mobile-computing-is-not-impressed-9ab25dfff0c

Phone -> desktop
Dreamcast

---

Called "First Class OS" because all users, contexts, inputs, devices considered first class.

---

# OS Patterns
Desktop/Home/Landing
- The place you default to when booting up. Always easy to get to (often multiple gestures get you back here).
- Think of this space as an app. This app might be something that houses shortcuts and widgets, a Watch Face, a Chrome New Tab Page (note: the background image is not actually a desktop, it is just an image).
- Sometimes this is replaceable (Android, Chrome, Wear, Ubuntu?)
- As a dev, you are given a lot of power for this space, but it is highly competetive. How many users do you really think you'll get to override their other Home with yours? Especially if it is specific to your product and not supporting more generic things?

---

I believe there will always be power users, and that those power users will likely require tools that should not necessarily be in the hands of the non-power users.

Think: video editors requiring beastly machines. Big-time gamers getting insane graphics cards. Developers using MacOS instead of just a chromebook, etc.

This distinction is critical for my article about Windows. It sacrificed its power user crowd for the more common crowd. In doing so, it lost any advantage it once had. For the users that don't need power user functionality,, there is iOS and Android. They needed to push hard on their mobile/tablet offering as a separate product, completely. Not butcher their power-user, corporate/business platform.

---

Immersive mode. Wear and Android.

Identify common patterns in OSs. Desktop, pinned, floating, full screen. Sharing. Dock, taskbar. Widgets.

Why care? You might want to bring these inside your apps! Like bottom tab bar, for example. Or side dock on web apps like Salesforce builder

---

dconf, registry for scriptable settings. All settings/config are serialized. Makes moving to new laptops and setting up significantly easier.

Basically allows manipulation via non-GUI settings. Just like homebrew enables installing via command line, not just a GUI store/browser.

Also ties in with system-level database, not isolated per-app sqlite

https://askubuntu.com/questions/249887/gconf-dconf-gsettings-and-the-relationship-between-them

Updating an app can also issue a DB migration. If you are renaming a user preference field, for example.

One, big, nested, namespaced json file

---

Workspaces are really just Tabs without a visible TabPanel.

Tabs all the way down. Into Web Apps, even.

---

# Control Center

http://www.phoronix.com/scan.php?page=news_item&px=GNOME-Settings-3.26

---

# App store in charge of all installs and updates.

Side loading possible.

---

# Types of user input (or gestures)
- right click (also the right click keyboard key in Windows)
- hover

---

# Improved Keyboard

Don't need arrow keys. Don't need Insert, Delete, Home, End, PgUp, PgDn.

Double-tap shift for caps-lock. Double-tap super for Super lock.

EMPOWER YOUR THUMBS!

Space bar not allowed to go past 'C' and 'M'.

Caps lock becomes Super, ctrl keys removed - no one can reach easily with their pinky anyways... Or it becomes the Function key to toggle F-keys. Once where you are ripped out of flow anyways.

Left-alt => Ctrl
Left-win => Alt
Right-alt => Super
Right-win/menu => Alt

The Code 61 keyboard is close-ish: https://www.geek.com/news/this-tiny-mechanical-keyboard-might-convince-you-to-ditch-your-big-one-1650830/

## Super Key

Reserved for System and Universal keybindings

Find, New Tab, Close Tab, Keyboard Navigation are all universal keybindings

Maybe not new tab and close tab though, since ctrl-tab to switch still makes more sense. And ctrl+0 to focus first tab makes more sense than overwriting super+0.

---

# Desktop and NTP of ChromeOS
New Tab Page of Chromebooks ARE your desktop. ChromeOS really should replace your desktop with whatever your NTP is. Then for new tabs, it just goes transparent?

Very much like the screenshot shown here: https://www.chromestory.com/2017/09/inspect-chrome-internal-ui/

Thought about while considering live desktops like http://www.omgubuntu.co.uk/2017/09/komorebi-wallpaper-app-new-features

---

Chrome really is its own OS. Shoved into other OSes. Almost like Flash. Ominously like Flash... *feels hot computer and looks at Activity Monitor*...

---

# Workspaces/Spaces/Virtual Desktops
Spaces short for Workspaces. Ubuntu calls them Workspaces.

---

# With a "universal" app platform, we can optimize our builtin browser for documents and sites
- anchor links!
  - [Display \#Anchors \- Chrome Web Store](https://chrome.google.com/webstore/detail/display-anchors/poahndpaaanbpbeafbkploiobpiiieko?utm_source=chrome-app-launcher-info-dialog)
  - Chrome extension to add "Link to Header" context menu option if you click on something with an id.
  - Chrome extension to show anchor links on hover. Needed for Medium articles.
  - e.g. https://medium.com/google-design/a-primer-on-android-navigation-75e57d9d63fe#63f7 does anchor link.

---

widgets
panel
dock
tray
toolbar
gadget
indicator
applet
dash | dashboard

workspace: static vs dynamic creation

ALL keyboard shortcuts configurable, even copy/paste, but start with a good set of defaults.

---

# when phone is docked
stylus acts as bluetooth headset. OR just use speaker if you are in your office

This is a reason to favor the Note

---

video games have progressive enhancement baked in. This is how we need ot think aobut our apps as well

Computer games are amazing with progressive enhancement. Graphics quality.

---

Web Apps are kind of bullshit. They are only valuable to target cross-platform. That is it - the only real reason! Right?

Wouldn't it have been better for OSs to standardize on a language, base set of APIs, etc?
- This would slow innovation, like what has happened to browsers.

---

You can't multitask with a modal.

Thinking about windows Start screen and Metro tiles.

---

# Platform Hooks
Windows:
- Taskbar
- Notification tray
  - System Tray
  - App Icon/quick actions
- Toast Notification (https://msdn.microsoft.com/en-us/library/windows/apps/hh779727.aspx)
- Start Tile and Live Tile

Mac:
- Menu bar
- Notification tray
- widget screen


... etc

Important to force constraints. Without a "window" system, more apps might choose layouts like the following, but then they wouldn't split screens well.
- https://dribbble.com/shots/2362697-Day-28-Contact-Us
- https://dribbble.com/shots/2470984-Day-68-Flight-Search
- https://dribbble.com/shots/2342992-007-Settings

---

# Platforms
Good platforms allow extensions. Plugins are software that use those extension points.

This applies to Gnome Shell, Chrome, even programming languages like oCaml's ppx macros, babel transforms, etc.

https://twitter.com/wokalski/status/897393627214880769

---

# Platform persistent locations
Android
- widgets
- daydream

Chrome
- New tab page

Mac
- Widget
- Notifications widget?

ios
- notification widget

Windows
- live tile

---

# App vs Extension/Integration/Augmentation

Is your app stand-alone? It doesn't require any platform features like monitoring other apps, using certain hardware drivers, hooking in to notifications, widgets, services/share menu? It doesn't hook in to context menu, the menubar, taskbar, etc?

Does it essentially augment the OS?

Cool, if it needs extension/integration, then you're forced to go native. Else, you are in app-world, where we can talk about web vs native pros/cons.

Web => tabs

native => window, immersive, rich animations, etc.

---

# Extension Points
Mac
- menubar
- notification widget
- dashboard (basically a wasteland)

Android
- Daydream
- widget
- notification (actions only)

---

Native for:
- Immersion
  - Reader
  - Writing
  - (full screen-able, tabs not desired)
  - (keeps you focussed)
- Utility
  - Contacts Cleaner - https://itunes.apple.com/us/app/contacts-cleaner/id411369012?mt=12
  - DaisyDisk - https://itunes.apple.com/us/app/daisydisk/id411643860?mt=12
- Extension (extending the feature set of the platform)
  - Hyperdock

---

# Native on Desktop
Global Hotkeys
- cmd y to start new Things 3 task

---

Administrator permissions

---

# WebOS
- Cards (deck of cards in hand)
  - Activities (not necessarily apps)
- Synergy (platform apps)
  - contacts
  - mail
  - browser
  - photos
  - messaging
  - music
- Universal search
- Notifications
- Dashboard control and oversite of everything

---

# Windowing Environments
Apps in app-mode
- own window
- one instance?

Apps in tab-mode
- in browser
- multiple instances

When you open an app, what should it do? With it already open, what happens when you "open" it again?

![](https://github.com/kylpo/notes/blob/master/assets/open-app.png?raw=true)

Tabs handled in-app or by platform's window. Could be considered an enhancement to creating a separate instance or replacing.

---

# Window vs Tabs (native vs web)
When you click a link, what happens? New tab? Open app? What if app is already open? Does it overwrite it? Open multiple instances (can't do this on mobile, I think).

http://a4.mzstatic.com/us/r30/Purple69/v4/c2/db/b1/c2dbb156-afe5-e025-39f7-bd9b8f9c06a7/screen800x500.jpeg

Good uses of Tabs: Explorer/Finder, browser, terminal, editors

---

App ---------------------------------- Site

 |                                       |

Full window                           tab/page

Web advantage: **links**
- `ctrl click` allows not context switching
- able to queue and batch up work

---

love that Android has Back and Home controls on bottom left, and Multitasker bottomr right when on tablets.

---

"I really wish they added mouse support in iOS 11. It’s very awkward to reach up to the screen to tap constantly or move your cursor around." - comment in [Google Docs has finally made working from my iPad possible \- The Verge](https://www.theverge.com/2017/8/18/16165336/google-docs-suggested-edits-ipad-work-game-changer)

[Remix OS for Mobile \- Take your Android experience to the next step\. Phone, desktop, TV\. Anywhere, anytime\.](http://cn.jide.com/remixos-for-mobile)

![](https://webcdn.jide.com/jide_upload/2017_03/1489402993640_nwopep_banner2.png)

love the hardware nav buttons on the dock, too. Nice touch.

[Samsung DeX \| Apps \- The Official Samsung Galaxy Site](http://www.samsung.com/global/galaxy/apps/samsung-dex/)

Dock has a built-in fan! SO smart.

---

# FC (First Class) OS
Because it treats all inputs, all users, and all modes as first-class.


# Inputs
Progressive enhancement of inputs.

Touch, Stylus, Keyboard, Mouse, Trackpad.

Consider gestures, shortcuts, modes.

Everything-first for highest quality apps in any context.

Best to think about starting with mobile (and disabling app in non-touch contexts if you need, like [android on chromeos](https://developer.android.com/topic/arc/index.html#update-manifest))

Mouse, keyboard, and stylus are precision tools. Also more convenient than touching a screen oftentimes.


Cool idea from Preme for Windows: Scroll taskbar to adjust volume. Even better would be scrolling the sound icon, maybe? Also interesting is `esc` `esc` (`esc` twice) to close windows.

# Dock/Taskbar

# Virtual Desktops

# Events
Events broadcast to inform your app how to respond

## Ambient Mode
Not just for screen savers

Even Samsung Gear has it:
- [Event Handling \| Tizen Developers](https://developer.tizen.org/zh-hans/development/training/web-application/understanding-tizen-programming/event-handling?langredirect=1#ambient)

Really like Note 8's `Screen off memo`: Make note without unlocking. [Samsung Galaxy Note 8 S Pen: Stylus Pen \| Samsung US](http://www.samsung.com/us/galaxy/note8/s-pen/)

![](https://github.com/kylpo/notes/blob/master/assets/note-8-memo.jpg?raw=true)

## Inputs
Everything input is first-class, and can accomplish most tasks. I.e. a keyboard shorcut should also be accomplished with a just a mouse, which should be accomplishable with just a touch/gesture.

Even Rotary Events? [Event Handling \| Tizen Developers](https://developer.tizen.org/zh-hans/development/training/web-application/understanding-tizen-programming/event-handling?langredirect=1)

![](https://developer.tizen.org/sites/default/files/dev_guide/org.tizen.gettingstarted/images/rotary_event.png)

#### Wheel
- Scroll Wheel of mouse
- Dial for Windows
- Rotation of Gear
- Even a scroll wheel on Microsoft's old Ergonomic keyboards

Would be nice to associate contexts/modes to this event. e.g. scrolling on sound icon adjusts volume. Scrolling on menubar moves workspace.

#### Future input: eyes
I'd love an OS to track my eyes to replace mouse and hover.

Cheaper keyboards would have dedicated click and scroll wheels, much like Microsoft's old Ergonomic keyboards.

Nicer keyboards would have a touchpad for gestures of what to do to target eyes are looking at.

This is actually quite a bit like being able to scroll a non-active window in Mac, Linux, and now Windows. Just moving your eyes and typing would be pretty amazing. Would use alt-tab much less often.

# Windows/Views
## Full-screen **Immersive mode**
https://developer.android.com/about/versions/kitkat.html#44-immersive

![](https://developer.android.com/images/kk-immersive-n5.jpg)

"A new immersive mode lets apps use every pixel on the screen to show content and capture touch events."

# Storage Access
New in IOS 11, in android since Kitkat (https://developer.android.com/about/versions/kitkat.html#44-storage-access)

Not just local: it enables providers of cloud-based services.

# Keyboard/Hotkeys
## System keyboard key
Mac got this right with `super`. `copy`/`paste` are OS-level functions, so they belong with `super`.

Window's `win` button is similar. They messed up `ctrl c`/`ctrl v` for copy/paste though. Also, `alt-tab` to switch windows, `alt-f4` to close windows. None of those keybinds make sense compared to Mac.

## Simplified keyboard and cursor movement
Again, Mac totally nailed this. Many of us work on laptops today, using the laptop's keyboard. The mac's keyboard is as close to perfect as I can get. Because it has the system level `super` modifier (and emacs keybinds of `ctrl-a`, `ctrl-f`, etc) there is no need for a physical `Home`, `End`, `PgUp`, `PgDn` keys crammed into the layout.

## System touch gestures

## System mouse gestures/hovers
Thinking about Hot Corners

Buttons for clickability, like [eXtra Buttons: utility buttons in the title of the window](http://www.xtrabuttons.com/)

# Widgets (also called Gadgets)
or, pinned mini-apps

![](http://cdn.makeuseof.com/wp-content/uploads/2015/09/muo-windows-w10-desktopgadgets-8gadget.jpg?x92042)

pic from http://www.makeuseof.com/tag/bring-desktop-gadgets-back-windows-10/

[Wearable Widgets \- Android Apps on Google Play](https://play.google.com/store/apps/details?id=com.wearablewidgets)

![](https://lh3.googleusercontent.com/Vk_0wz7QsdWJZQkYVD5u6vsoIMwhUwiUc0ArWO_i8sUAIDJbjhpIgBic21IrSvmAc0RM=h900-rw)

Also found on web: `iGoogle`

[Great Personalized Start Pages: 6 Alternatives To iGoogle](http://www.makeuseof.com/tag/great-personalized-start-pages-6-alternatives-igoogle/)


## Glancable
Windows 8+ tiles. Functionality is pretty much worthless. More like a persistent text/image notification that you must click to understand further. Even worse though, if the News app shows a story you have interest in, it'll take you to the app. NOT to the story inside the app.

## Actionable
Has buttons and/or inputs, basically. Music player controls, sticky notes, to-do lists, etc.

True mini-apps. Likely take up more resources?

---

# Why I like Android
Steel is Democratic metal, just like android.

![](https://o.aolcdn.com/images/dims?quality=100&image_uri=http%3A%2F%2Fwww.blogcdn.com%2Fwww.engadget.com%2Fmedia%2F2013%2F10%2Fdsc08051.jpg&client=cbc79c14efcebee57402&signature=aa83a04c9bf4894207acf309a6bfaf09ffc7c15c)

from [Lenovo's 'Yoga' Android tablet has a built\-in kickstand containing an 18\-hour battery \(hands\-on\)](https://www.engadget.com/2013/10/29/lenovo-yoga-tablet-hands-on/)

Asus Transformers
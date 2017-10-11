
TODO: Take notes on Samsung Gear

---

[The iPhone X is the Beginning of the End for Phones](https://thinkgrowth.org/the-iphone-x-is-the-beginning-of-the-end-for-phones-ab9ac8391a3) resonates with me. The idea that my watch can be my safety device, the thing that non-smart phones used to be, and I can bring around a tablet/laptop for non-active tasks.

I like the idea of thinking about your phone as just a pocket computer, like the Palm used to be. All phone-like functionality exists on the watch. You'd still have internet connectivity to your pocket computer though. This "pocket computer" name makes the futuristic Dex and Laptop less of a mental leap.

I want a pocket computer that has all screen. No cameras/speaker bar. I don't want to take selfies. When I do, I want to add an attachment to my device like the Essential phone? Or have it pop out a selfie camera? I don't even really need the audio since I won't care to put it up to my ear to talk. Earbuds or speaker phone is fine. For authentication, the back finger print sensor is great.

I want the bottom to house OS-level navigation and app switching (continued in Dock section).

"pocket computer" basically just a mini tablet, or phone-form tablet. Like the ipod Touch.

---

Present on Medium as a series with the Table of Contents and italicized intro at the top, like [Code Smells: Too Many Problems \| IntelliJ IDEA Blog](https://blog.jetbrains.com/idea/2017/09/code-smells-too-many-problems/) has done.

---

Nothing here is really earth shattering, just taking pieces/patterns here and there, even accross disciplines (like gaming), and combining in a way that I think would be ideal for users (of multiple contexts like personal, power user, business user, disabled), software developers, hardware developers

---

# Why am I writing this?
More innovation in the OS space, more starting fresh, like Dex, Fuchsia, tizen, Linux.

[Fuchsia \- Fuchsia is Not Linux](https://fuchsia.googlesource.com/docs/+/HEAD/book.md)

Also because I recently did a round of researching these platforms for app development. What are their capabilities: their strengths and limitations. Also because many of these patterns and concepts can and do live within apps.

---

Reach out to Dion when this series is released because of [Operating System? Help Me Operate – Ben and Dion – Medium](https://medium.com/ben-and-dion/operating-system-help-me-operate-c18c698978e1)


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

# Levels of Access
## Functionality **without** unlocking
Camera, 911, see notifications and act on them, galaxy's note [Screen off memo](http://www.samsung.com/us/galaxy/note8/s-pen/#slick-slide13) for making a note without unlocking, ipad pencil's double-tap lock screen to take note, surface pen thumb click to launch OneNote.

Write-only, no Read

Slightly different from Ambient Mode.

## Functionality without logging in (not quite the same as unlocking)
Interesting take on when to require user login for different layers of functionality.

[Why you shouldn’t unlock your phone with your face – freeCodeCamp](https://medium.freecodecamp.org/why-you-should-never-unlock-your-phone-with-your-face-79c07772a28)

"Instead of the current all-or-nothing approach — you’re either authenticated or you aren’t — device manufacturers should take a tiered approach, requiring different levels of authentication to access different apps and data.

This is similar to traditional role-based access control in software. And phones already do this with lock screens.

For example, by default on iOS, you can read incoming text messages without unlocking your phone. And whenever you try to buy something in the App Store, iOS by default requires you to enter an even longer password to confirm a purchase."

## Android's Intents
Android has developed a system similar to this for actions apps should be able to handle. See [Sending the User to Another App \| Android Developers](https://developer.android.com/training/basics/intents/sending.html).


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

Do AMOLED screens remove the desire for something like the Yota e-ink back?

![https://www.engadget.com/2017/09/20/dual-screen-e-ink-yota3-official/](https://o.aolcdn.com/images/dims?quality=100&image_uri=http%3A%2F%2Fo.aolcdn.com%2Fhss%2Fstorage%2Fmidas%2F61a4ebd13362511434c88e797976c92c%2F205685804%2Fyota3.jpg&client=cbc79c14efcebee57402&signature=7e936f920b23d92f43788aef7a1f82f7c73f88db)

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

## Like your phone's lock-screen
Users will want to see the information and be able to act on things quickly. As if they were using their phone/tablet's lock screen.

- [Be Limitless \- Chrome Web Store](https://chrome.google.com/webstore/detail/be-limitless/jdpnljppdhjpafeaokemhcggofohekbp)
  - ![](https://lh3.googleusercontent.com/NDHsBp2DYMgqko36Efrlz4febzo1Dkk0kpBRjKwtG205gu0ojoWWyN15Lw84h0My002QdL5FLA=w640-h400-e365)
- [Momentum \- Chrome Web Store](https://chrome.google.com/webstore/detail/momentum/laookkfknpbbblfpciffpaejjkokdgca)
  - ![](https://lh3.googleusercontent.com/RJ4jnr30NkOL3zFByvWdY0JNWH_q7F4Up2I0RsRxV0m-N25MHB0IlwWg5GzCy3w-XiCK6yy_UA=w640-h400-e365)
- [Focus \- Chrome Web Store](https://chrome.google.com/webstore/detail/focus/paipcheolflniajdfeglfpddafcklepg)
  - ![](https://lh3.googleusercontent.com/VGJGQINGg8IWyeSFF6AhZKJqbceZhLwrLYef7Cj68OJr-jmPHhq2nNF-l2Ld9VG2iajBGuWvpHs=w640-h400-e365)

## Like a dashboard
- [iChrome \- A Fast, Productive Home Page \- Chrome Web Store](https://chrome.google.com/webstore/detail/ichrome-a-fast-productive/oghkljobbhapacbahlneolfclkniiami)
  - ![](https://lh3.googleusercontent.com/LWRpG-0sLNI6eKIw3oje5j96GdZEq4xc9bxTeC68ESkphlwj6pl4uq8AyQUY-z_kfYkzjSNgMw=w640-h400-e365)

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

# Dock
Hover previews (Dash to Panel extension for Gnome Shell):

![http://www.omgubuntu.co.uk/2017/07/dash-panel-updated-window-peek-new-options](http://www.omgubuntu.co.uk/wp-content/uploads/2017/07/dash-to-panel-window-peek-750x470.jpg)

Optional Hotkeys with number overlay (Dash to Panel extension for Gnome Shell):

![http://www.omgubuntu.co.uk/2017/07/dash-panel-updated-window-peek-new-options](http://www.omgubuntu.co.uk/wp-content/uploads/2017/07/unity-style-numbers-750x358.jpg)

Dock can be a launcher in some OSs, but I don't think it should be in this one if workspaces are endorsed.

## Mobile consideration
I want the bottom to house OS-level navigation and app switching. Similar to Android's on-screen buttons, a dock can exist here for normal app usage. Apps can still enter a full-screen mode to hide this bar.

This bottom dock for navigation could extend to tablets, laptops, desktops.

![](https://cdn.vox-cdn.com/thumbor/A1id7a8_yLkJEPW5GuJSOiUJDs8=/0x0:2040x1360/920x613/filters:focal(857x517:1183x843):format(webp)/cdn.vox-cdn.com/uploads/chorus_image/image/54558833/akrales_170425__1644_0006.0.jpg)

## Watch consideration
WatchOS
- Vertical "Dock" of widgets, app launcher as last item
- Hardware Button
- Order by Favorites or Recent (configurable)
  - Kind of similar to showing by Favorites vs currently open of Gnome's Dash to Panel and Windows 10

---

# Statusbar
When the screen is sufficiently large, this'll exist on the bottom Dock. When it isn't it'll live on top, like on phones and portrait tablets.

Dex helped me think of this.

---

# Menus
In Global Menu?

![http://www.omgubuntu.co.uk/2017/07/ubuntu-mate-17-10-alpha-2-hud-global-menu](http://www.omgubuntu.co.uk/wp-content/uploads/2017/07/ubuntu-mate-1710-unity-layout.jpg)

## Without a global menu
Some apps will choose to always display a toolbar of menu items (Terminal, Word). Others choose to house them behind a button (Chrome). Others don't offer any at all (probably not a good idea). ALL must be searchable with a hotkey.

HUD to search them?

![http://www.omgubuntu.co.uk/2017/07/ubuntu-mate-17-10-alpha-2-hud-global-menu](http://www.omgubuntu.co.uk/wp-content/uploads/2017/07/mate-hud-gif.gif)

---

# Dex
[Samsung DeX review: the closest thing we have to using our phones as PCs \- The Verge](https://www.theverge.com/2017/5/2/15495036/samsung-dex-station-galaxy-s8-review-desktop-dock) for a good walkthrough
- takes a minute to load when docked, and a couple to get phone back in usable state after disconnecting
- "All of the apps that you had been using on the phone before you docked it are available as icons at the bottom of the screen, which means there will likely be dozens of icons in the task bar right away. The system tray at the lower right provides access to notifications, settings shortcuts, and the time and date, just like you might find on a Windows 10 computer."
- dock lacks audio out for desktop speakers

## Apps in taskbar dilema
The open apps in taskbar make me think about Workspaces, and how you really should only have one for phone. Hmmm, but you do have split view apps, where there are two apps in a workspace. So maybe mobile workspaces are just merged when you switch to desktop? Or is this just a vim type of thing where you have open buffers, and you system arranges them as splits and tabs. Your mobile layout will be different from your desktop layout.

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

## Related: Browser
Now that tabs are a first-class construct to your OS, it is easier to think of a Web Browser as more of just an html, css, js rendering engine. It is almost like a PDF viewer or Word: it is something that opens a document. And you can have multple instances of that of your Browser app as tabs by having multiple open documents.

This is actually similar to how Chrome works today, and why it made a splash when it was first released. When a tab had some fatal crash, it only broke that specific tab, not the whole browser. And this is because each tab is essentially its own, separate instance. This was not how Firefox ran back in the day. Because all tabs were run as one app (single process on the computer?), a broken tab would break all tabs.

How `html`, `js`, `css` are rendered is standardized, just as `markup`, `unicode`, etc is. Different engines can optimize different things, but there shouldn't really be much of a difference from Safari to Edge. Just how the customized UI looks, plugins are built, etc. Even plugins are getting standardized with the WebExtensions standard.

[jordanIsNotAFunction on Twitter: "There is not one single browser\+JS engine that easily works and runs on every OS and that bothers me to no end\."](https://twitter.com/jordwalke/status/910333937993445378)

---

It is not that web sites and web apps make for nice queued tasking. It is that you can `cmd-click` to open other tabs in the background, not just launch new windows that take your focus.

See video of [Flynx \- Read the web smartly \- Android Apps on Google Play](https://play.google.com/store/apps/details?id=com.flynx)

---

# Window vs Tabs (native vs web)
When you click a link, what happens? New tab? Open app? What if app is already open? Does it overwrite it? Open multiple instances (can't do this on mobile, I think).

http://a4.mzstatic.com/us/r30/Purple69/v4/c2/db/b1/c2dbb156-afe5-e025-39f7-bd9b8f9c06a7/screen800x500.jpeg

Good uses of Tabs: Explorer/Finder, browser, terminal, editors

---

# App Modes
Single App, replaces single app

Multiple instances

tabs

"Tabs provide quick navigation between sibling views inside the same parent screen. They’re coplanar, meaning they can be swiped around, and they live in an extensible, identifiable tab bar."

https://medium.com/google-design/a-primer-on-android-navigation-75e57d9d63fe#63f7

ChromeOS is the perfect place to experiment with this now that Android apps are available. Which do I prefer using: Inbox for web? Or Inbox on Android?

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

# Content Sharing
Use the sharing API. Even the web is able to use it now: [Introducing the Web Share API  \|  Web  \|  Google Developers](https://developers.google.com/web/updates/2016/09/navigator-share)

---

# Search
Universal search, where you can toggle app-specific search, like these Action Launcher search shortcuts.

![](https://9to5google.files.wordpress.com/2017/10/1-vfov3476j4gla7imdgipzw.gif?w=875&h=583)

---

# Notifications
Gnome-Shell has toggles for showing `Lock Screen Notifications` and `Notification Popups`

[How To Design Notifications For Better UX – UX Planet](https://uxplanet.org/how-to-design-notifications-for-better-ux-6fb0711be54d)

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

# Focus
Default to highlighting active focus for keyboard use. Remove highlight for `touch mode`, as Android does: [View \| Android Developers](https://developer.android.com/reference/android/view/View.html#TouchMode) 

Hotkey to highlight/flash available inputs, like Invision

# Dock/Taskbar

# Virtual Desktops

# Events
Events broadcast to inform your app how to respond

## Ambient Mode, or AOD (Always On Display)
Not just for screen savers

Even Samsung Gear has it:
- [Event Handling \| Tizen Developers](https://developer.tizen.org/zh-hans/development/training/web-application/understanding-tizen-programming/event-handling?langredirect=1#ambient)

Really like Note 8's `Screen off memo`: Make note without unlocking. [Samsung Galaxy Note 8 S Pen: Stylus Pen \| Samsung US](http://www.samsung.com/us/galaxy/note8/s-pen/)

Well, screen off memo is probably not a good example of Ambient Mode. Instead it is a feature without needing to unlock, like camera.

![](https://github.com/kylpo/notes/blob/master/assets/note-8-memo.jpg?raw=true)

[Justin Searls on Twitter: "1\. Think of important thing 2\. Pick up phone to take action 3\. See unrelated notification 4\. Forget important thing 5\. Be angry forever\."](https://twitter.com/searls/status/910531247205699586) would be prevented with an AOD note

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
Sane defaults, but still totally configurable. Maybe even themable for different sets of users. emacs/vi/whatever

[Ubuntu Keyboard navigation](https://help.ubuntu.com/stable/ubuntu-help/keyboard-nav.html)

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
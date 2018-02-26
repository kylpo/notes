
---

Problems with Windows UWP: not able to Extend

---

Text on Windows Chrome is just slightly blurry. You'll notice this easily when comparing it to Edge. This is because Chrome uses Windows old text rendering, which has had this issue for a loooong time with better displays.

Fortunately, it seems like Firefox's new Quantum does not suffer from this blurry text. Quantum has allowed me to switch back from Linux to Windows. Blurry text reading all day was a deal breaker.

https://dev.to/kayis/a-reason-to-code and http://view.lyftmail.com/?qs=efe229bb795387bc0401f3fa936408e0fc6d2f19edadf0169c5f3567be348a8a9d9675ea33428b7037717f398763bf7bc4039c339df1c0d90479649356b29506a9c8b6703652cab85606adeb7b6a714d9a2c418a9c3ae403 (the Portland text) helped me see this

---


# Windows 8 should've just added an app store

I've been saying this for years, but now I'd like to put this down as words.

All Windows 8 needed to do was add a store to Windows 7. That's it.

Instead, Microsoft chose to pivot the entire platform to touch. There is nothing wrong with adding touch, but it should have been added as an enhancement, not as it was. When it was added, apps were forced down to the new lowest common denominator, they lost power user hotkeys (press Alt to see shortcuts in legacy Office).

---

For years I've been saying Windows 8 would've been a success, and Microsoft would've remained dominant in the desktop/laptop space, if it had just slapped an App Store onto Windows 7. Nothing else. All it needed was a place to easily advertise and promote the desktop (win32) applications that had already existed on the platform.

How do I know I'm right? Look at MacOS. This is exactly what they've done. They have a successful app store with rich, productive, powerful apps that are able to hook in as extensions to the OS (menubar, widgets, context menus, dock menus, floating and pinned windows, global hotkeys, etc), and be wonderful tools to those with keyboards and mice/trackpads. Very similar apps to what you find in the legacy/desktop applications on Windows 10 today (you know, the ones you downloaded from the web, like Microsoft Office, Outlook, and OneNote).

You see, the Windows Store is a desolate place today because it only promotoes Universal Windows Platform (UWP) apps (touch-first, isolated, but secured apps). These apps have some hooks to extending the OS (notifications, share menu), but are not even close to as capable (missing global hotkeys, not able to launch multiple windows, etc). They work well for tablet gaming, maybe, but are not suitable replacements to desktop Office, desktop OneNote, desktop Evernote, etc.

I think UWP has an overly restrictive API that flat out prevents developers from delivery the same quality that users had previously expected, but I think the another big problem was that they forced being touch-friendly. Instead of *enhancing* experiences with touch, their touch mandate lowered the bar for what an app can/should do. The developer and designer's mentalities changed, and keyboard and mouse/touchpad became afterthoughts.

I'll use OneNote to help me demonstrate what I mean. Here it is in desktop form (not from the app store).

It has a highly configurable UI via an expanding/collapsing Ribbon.

It caters to keyboard-first power users. Just press `alt` to see hotkeys to drill into controls.

then I press...

It also caters to power users in mouse-mode. Highlight text to see a menu of relevant actions pop up right next to this.

![](https://cdn1.tekrevue.com/wp-content/uploads/2015/02/word-search-with-bing.jpg)

(Yes, this is Word, I wasn't able to quickly find a OneNote image, and screenshotting it is a bit tricky)


1874 reviews in Windows Store

26231 reviews in Mac Store


No screen recording apps on Windows Store (because it isn't possible?)



Is this a sufficient UI for touch-only? Totally! Can it work for mouse/keyboard? Yes. Can the keyboard and mouse interactions be brought up to parity? I think so.


---

[Windows Store Guide \| Electron](https://electron.atom.io/docs/tutorial/windows-store-guide/)

"Microsoft developed a tool that compiles Electron apps as .appx packages"

"Another important limitation is that the compiled AppX package still contains a win32 executable - and will therefore not run on Xbox, HoloLens, or Phones."

**UPW Features**: like push notifications, Cortana integration, or live tiles.

[Introducing Electron to the Windows Runtime – Several People Are Coding](https://slack.engineering/introducing-electron-to-the-windows-runtime-4fa789b93d90)

---







Even today, 5 years after Windows 8's release, Microsoft publishes some apps that don't have hoverable information on icons. This expectation is one of the most basic ones for mouse users.

 You can even find the desktop-quality [OneNote](https://itunes.apple.com/us/app/microsoft-onenote/id784801555?mt=12) in Mac's App Store!





I don't know for sure that these capabilities are not possible when building for UWP. I think most aren't, but I don't want to spend any more time researching this. I do know, however, that the tone of UWP is different. Touch-first is the mantra. Keyboard, mouse, and bigger screens are an after thought, which is completely opposite of the Windows 7 application days.

And the result today, 5 years after Windows 8's release, is a best-in-class app in the app store of (oneNote):

Versus the its legacy/desktop version:
- `alt` to show hotkey nav
- menu positioned next to highlighted content
- configurable UI, from controls in the titlebar

Heck, even the web version is better:
- `ctrl-f6` to show hotkey nav
- menu positioned next to highlighted content
- configurable UI, from controls in the titlebar

Again, this app's Mac equivalent is availabe on Mac's app store. (Note: I don't see a way to show the keyboard nav or menu after highlighting text. Not a limitation of the platform, I think it was just deprioritized.)


Let's look some more examples, side-by-side:


If you're curious for more examples, be sure to check out desktop Outlook vs Mail App, all of the other Office products, desktop Wunderlist vs To-Do (no global hotkeys!?)



Microsoft was a king in the desktop space. It built amazing apps, and Windows 7 had plenty of capabilities and hooks to enable them to do it. Amazing applications that just CAN'T be translated to UWP apps. So when the store was released, instead of showcasing the power by promoting its own products like Apple (install Keynote, Pages, iMove, Xcode, even OS upgrades in their app store), it showcased a wasteland of completely underpowered apps. The Mail client, for example, had to be embarassing.

Fast-forward to today, I see Microsoft doubling down on their mistake with Windows 10 S. They are promoting a new OS that can ONLY use apps from their App Store. Students will surely be productive with these UWP apps, right? No, which is why they've enabled Windows 10 S (only!) users to install the legacy/desktop version of Office from the app store ([source](https://www.windowscentral.com/how-install-microsoft-office-apps-windows-10-s-devices)).

My recommendation is to open up the app store completely. Let me as a power user have a reason to open the store. Let me as a developer have a reason to develop for Windows (over MacOS). OR go the way of Apple and have separate app stores for laptop/desktop devices and touch-first devices (iOS). I have no problems with Windows 10 S on a tablet or phone, just don't push it on me as a laptop/desktop user. Could even combine these store in Windows 10, as ChromeOS is doing with Android apps. The Android apps are purely an enhancement, not a detriment.

Touch should have been an opportunity to enhance to the Windows experience. It shouldn't have lowered the bar, like a lowest common denominatior, and crippled everything else.

Do I build a desktop app that users will discover from a web browser? Do I limit my ambition and features to place it in the app store? Or do I raise my hands and just move on to MacOS?

If I am to accept that UWP is still the future of Windows, what incentive do I have to develop for it? We already have thriving markets of Android and iOS that offer the same limitations. They even offer more power and extension hooks, actually.

I didn't want this post to sound ranty, but I'm honestly really upset with Microsoft for giving me no other option but to develop for MacOS. I've never been an Apple fan, but it is my only option for apps that require a certain set of features. And I certainly can't wait any longer for them to address these problems. 5 years is enough.

---

## Updates
Woah, it looks like they are opening the app store to desktop apps!!!
- Evernote, from the app store, is able to use multiple windows and access global hotkeys.
- Spotify is now on the app store, and only works on desktop.

Windows just has really weird display bugs, still. Whyyyyy?

https://www.digitaltrends.com/computing/surface-book-2-as-only-pc/#ampshare=https://www.digitaltrends.com/computing/surface-book-2-as-only-pc/

# TalkBack

Screen reader. `Settings` app on device or emulator > `Accessibility` > `TalkBack`. Toggle "Use service" switch.

Emulator doesn't have TalkBack by default. To install:

1. Download TalkBack [here](https://google-talkback.en.uptodown.com/android).
2. Drag downloaded `.apk` into emulator.

Use volume key shortcut to toggle TalkBack. To turn on shortcut, go to `Settings` > `Accessibility`. At top, turn on Volume key shortcut.

To use volume key shortcut, press both volume keys for 3 seconds to start a11y tool.

Can toggle TalkBack via command line:

**Disable:**

`adb shell settings put secure enabled_accessibility_services com.android.talkback/com.google.android.marvin.talkback.TalkBackService`

**Enable:**

`adb shell settings put secure enabled_accessibility_services com.google.android.marvin.talkback/com.google.android.marvin.talkback.TalkBackService`

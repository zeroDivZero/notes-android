# OVERVIEW

App -> (info & allowed actions) -> A11y framework (`AccessibilityNodeInfo`, `AccessibilityEvent`, `contentDescription`, `get/setStateDescription()`, etc.) -> (generic representation of info & allowed actions) -> `AccessibilityService` (app or util such as **TalkBack** that presents in way to fit user's a11y needs)

Often depended by UI testing frameworks, such as Android's own **UI Automator**.

A11y draws in window on top of all windows. Can replace parts of UI with custom ones, at perf cost.

## Accessibility Scanner

[https://support.google.com/accessibility/android/answer/6376570?hl=en](https://support.google.com/accessibility/android/answer/6376570?hl=en)

App that scans my app's screen and provides suggestions to improve a11y, based on:

* Content labels
* Touch target size
* Clickable items
* Text and image contrast

Automated, but no replacement for manual testing.

## Switch Access

[https://support.google.com/accessibility/android/answer/6122836?hl=en](https://support.google.com/accessibility/android/answer/6122836?hl=en)

A11y setting to let external switch or keyboard hardware interact with Android device without touchscreen. Another `AccessibilityService`.

## Best Practice

Easy to neglect or implement incorrectly. Most devs don't have intuition or experience about user's a11y needs. Use modern framework like **Compose** to get built-in a11y support, and rather than build UI components from scratch, use **Material Design Components**.

Allocate resource to support from beginning. More work to retrofit later.

## Testing

3 types of unit tests cover most issues.

### 1. Make sure info correctly presented to A11y service.

Make sure `AccessibilityNodeInfo` correctly populated.

### 2. Make sure events sent at correct time.

Event indicates change in `AccessibilityNodeInfo` state. Override `sendAccessibilityEvent()`, trigger change in UI, check if correct event passed to function.

### 3. Make sure a11y service can perform action on UI.

Call `performAction()` on component then check view hierarchy or state is as expected.

### Automated

One possibility is to write instrumentation tests driven through a11y object instead of thru UI.

## Other Resource

[Android A11y Dev Doc](https://developer.android.com/guide/topics/ui/accessibility)

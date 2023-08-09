# Capacitor Browser Bug Reproduction

Minimal sample application that demonstrates issue of `@capacitor/browser` library.

## Current Behavior

When starting the app, Browser plugin opens in-app browser and loads requested webpage. When app is minimized and then reopened via the overview button, in-app browser is still present, which is correct. But when minimized app is opened by clicking on application icon, in-app browser is closed.

<img src="./video.gif" width="250"/>

## Expected Behavior

In-app browser should stay opened also in this case.

## Real Use Case

Let's say, user needs to authorize action inside in-app browser by providing 2FA from authenticator app. User minimize the app and opens e.g. google authenticator app. When he reopens original app by clicking on app icon to paste there auth code, there is no running browser anymore and user is confused about that.

## Steps to reproduce

1. Start the app in android emulator `npx cap run android`
2. Wait for the in-app browser to open
3. Minimize the app
4. Reopen the app **by clicking on application icon**

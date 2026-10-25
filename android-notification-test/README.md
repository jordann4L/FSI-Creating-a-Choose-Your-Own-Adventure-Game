# Notification Test (Android)

A minimal Android test app that pops up a notification on the phone. Tapping the
notification, or its **Open browser** button, opens a URL in the device's
default web browser.

## What it does

1. The app opens to a screen with a URL field (default `https://www.google.com`)
   and a **Show notification** button.
2. Pressing the button posts a high-priority notification, which shows as a
   heads-up pop-up at the top of the screen.
3. Tapping the notification body or the **Open browser** action opens the URL
   in the browser and dismisses the notification.

On Android 13 and newer the app asks for notification permission the first time
you press the button.

The code is in
[`app/src/main/java/com/example/notificationtest/MainActivity.kt`](app/src/main/java/com/example/notificationtest/MainActivity.kt).

## Build and run

**Android Studio:** open this `android-notification-test` folder, wait for the
Gradle sync to finish, then press **Run** with a phone or emulator connected.

**Command line** (requires the Android SDK; set `ANDROID_HOME` or create a
`local.properties` file with `sdk.dir=/path/to/Android/sdk`):

```sh
./gradlew assembleDebug
adb install -r app/build/outputs/apk/debug/app-debug.apk
adb shell am start -n com.example.notificationtest/.MainActivity
```

## Requirements

- Android 7.0 (API 24) or newer
- JDK 17 or newer to build

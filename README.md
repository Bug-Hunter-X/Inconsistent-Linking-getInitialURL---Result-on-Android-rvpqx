# Inconsistent Linking.getInitialURL() Result on Android

This repository demonstrates a bug in Expo's `Linking.getInitialURL()` function on Android.  The function sometimes returns `null` even when the app was launched via a deep link, making reliable deep link handling difficult.  The `bug.js` file shows the problem, and `bugSolution.js` presents a potential workaround.

## How to Reproduce

1. Clone this repository.
2. Run the app on an Android device or emulator.
3. Open a deep link that targets the app.
4. Observe that `Linking.getInitialURL()` may return `null` despite the deep link being received.

## Potential Solution

The provided workaround involves repeatedly calling `Linking.getInitialURL()` within a short delay. This approach works by leveraging the asynchronous nature of deep linking. This is not ideal, but offers a functional fix until a more robust solution is provided by Expo.
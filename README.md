# React Native Firebase Starter<a href="https://rnfirebase.io"><img align="left" src="https://camo.githubusercontent.com/dbea9e8e1413431453c9df6876dedf678c0f8a63/68747470733a2f2f692e696d6775722e636f6d2f65424e4a6c48642e706e67"></a>

[![Backers on Open Collective](https://opencollective.com/react-native-firebase/backers/badge.svg)](#backers)
[![Sponsors on Open Collective](https://opencollective.com/react-native-firebase/sponsors/badge.svg)](#sponsors)
[![npm version](https://img.shields.io/npm/v/react-native-firebase.svg?style=flat-square)](https://www.npmjs.com/package/react-native-firebase)
[![NPM downloads](https://img.shields.io/npm/dm/react-native-firebase.svg?style=flat-square)](https://www.npmjs.com/package/react-native-firebase)
[![Chat](https://img.shields.io/badge/chat-on%20discord-7289da.svg?style=flat-square)](https://discord.gg/C9aK28N)
[![Twitter Follow](https://img.shields.io/twitter/follow/rnfirebase.svg?style=social&label=Follow)](https://twitter.com/rnfirebase)

---

A basic react native app with [`react-native-firebase`](https://github.com/invertase/react-native-firebase) pre-integrated  to get you started quickly.

---


### Getting Started

> If you're only developing for one platform you can ignore the steps below that are tagged with the platform you don't require.

#### 1) Clone & Install Dependencies

- 1.1) `git clone https://github.com/invertase/react-native-firebase-starter.git`
- 1.2) `cd react-native-firebase-starter` - cd into your newly created project directory.
- 1.3) Install NPM packages with your package manager of choice - i.e run `yarn` or `npm install`
- 1.4) **[iOS]** `cd ios` and run `pod install` - if you don't have CocoaPods you can follow [these instructions](https://guides.cocoapods.org/using/getting-started.html#getting-started) to install it.
- 1.5) **[Android]** No additional steps for android here.

#### 2) Rename Project

**You will need to be running Node verison 7.6 or greater for the rename functionality to work**

- 2.0) **[iOS]** `cd ..` to return to the root directory of the project
- 2.1) `npm run rename` - you'll be prompted to enter a project name and company name
- 2.2) Note down the package name value - you'll need this when setting up your Firebase project

#### 3) Add `Google Services` files (plist & JSON)

- 3.1) **[iOS]** Follow the `add firebase to your app` instructions [here](https://firebase.google.com/docs/ios/setup#add_firebase_to_your_app) to generate your `GoogleService-Info.plist` file if you haven't done so already - use the package name generated previously as your `iOS bundle ID`.
- 3.2) **[iOS]** Place this file in the `ios/` directory of your project.
- 3.3) **[Android]** Follow the `manually add firebase` to your app instructions [here](https://firebase.google.com/docs/android/setup#manually_add_firebase) to generate your `google-services.json` file if you haven't done so already - use the package name generated previously as your `Android package name`.
- 3.4) **[Android]** Place this file in the `android/app/` directory of your project.
  
#### 4) Start your app

- 4.1) Start the react native packager, run `yarn run start` or `npm start` from the root of your project.
- 4.2) **[iOS]** Build and run the iOS app, run `npm run ios` or `yarn run ios` from the root of your project. The first build will take some time. This will automatically start up a simulator also for you on a successful build if one wasn't already started.
- 4.3) **[Android]** If you haven't already got an android device attached/emulator running then you'll need to get one running (make sure the emulator is with Google Play / APIs). When ready run `npm run android` or `yarn run android` from the root of your project.

If all has gone well you'll see an initial screen like the one below.

---

## Troubleshooting

### Multiple ADB server instances (Unity conflict)

If you see a warning like:

```
Multiple ADB server instances found, the following ADB server instance have been terminated
due to being run from another SDK. If instance restarts during deployment, this may cause
unexpected issues. Please check that ADB versions are consistent across instances.
Process paths: C:\Program Files\Unity\Hub\Editor\...\platform-tools\adb.exe
```

This happens when Unity's bundled Android SDK ADB conflicts with the system Android SDK ADB.
To resolve this, choose **one** of the following options:

**Option A – Point Unity to your system Android SDK (recommended)**

1. Open Unity and go to **Edit > Preferences > External Tools** (Windows/Linux) or **Unity > Preferences > External Tools** (macOS).
2. Under the **Android** section, uncheck `Android SDK Tools Installed with Unity (recommended)`.
3. Set the **SDK** path to your standalone Android SDK directory (e.g. `C:\Users\USERNAME\AppData\Local\Android\Sdk` on Windows or `~/Library/Android/sdk` on macOS).
4. This ensures Unity and React Native share the same ADB, eliminating the conflict.

**Option B – Configure `local.properties` in the Android project**

1. Copy `android/local.properties.sample` to `android/local.properties`.
2. Uncomment and set the `sdk.dir` line to your standalone Android SDK path.
3. This tells Gradle's Android tooling to use the specified SDK/ADB rather than any bundled one.

**Option C – Use a single ADB before deploying**

1. Before running `npm run android`, kill any running ADB processes:
   - **Windows**: `taskkill /F /IM adb.exe`
   - **macOS/Linux**: `killall adb`
2. Then run `adb start-server` once from the system Android SDK's `platform-tools` directory.
3. Subsequent connections from both Unity and React Native will reuse this single server.

---

## Screenshots

![preview](https://i.imgur.com/4lG4HuS.png)


## Contributors

This project exists thanks to all the people who contribute. [[Contribute]](https://github.com/invertase/react-native-firebase/blob/master/CONTRIBUTING.md).
<a href="graphs/contributors"><img src="https://opencollective.com/react-native-firebase/contributors.svg?width=890" /></a>


## Backers

Thank you to all our backers! 🙏 [[Become a backer](https://opencollective.com/react-native-firebase#backer)]

<a href="https://opencollective.com/react-native-firebase#backers" target="_blank"><img src="https://opencollective.com/react-native-firebase/backers.svg?width=890"></a>


## Sponsors

Support this project by becoming a sponsor. Your logo will show up here with a link to your website. [[Become a sponsor](https://opencollective.com/react-native-firebase#sponsor)]

<a href="https://opencollective.com/react-native-firebase/sponsor/0/website" target="_blank"><img src="https://opencollective.com/react-native-firebase/sponsor/0/avatar.svg"></a>
<a href="https://opencollective.com/react-native-firebase/sponsor/1/website" target="_blank"><img src="https://opencollective.com/react-native-firebase/sponsor/1/avatar.svg"></a>
<a href="https://opencollective.com/react-native-firebase/sponsor/2/website" target="_blank"><img src="https://opencollective.com/react-native-firebase/sponsor/2/avatar.svg"></a>
<a href="https://opencollective.com/react-native-firebase/sponsor/3/website" target="_blank"><img src="https://opencollective.com/react-native-firebase/sponsor/3/avatar.svg"></a>
<a href="https://opencollective.com/react-native-firebase/sponsor/4/website" target="_blank"><img src="https://opencollective.com/react-native-firebase/sponsor/4/avatar.svg"></a>
<a href="https://opencollective.com/react-native-firebase/sponsor/5/website" target="_blank"><img src="https://opencollective.com/react-native-firebase/sponsor/5/avatar.svg"></a>
<a href="https://opencollective.com/react-native-firebase/sponsor/6/website" target="_blank"><img src="https://opencollective.com/react-native-firebase/sponsor/6/avatar.svg"></a>
<a href="https://opencollective.com/react-native-firebase/sponsor/7/website" target="_blank"><img src="https://opencollective.com/react-native-firebase/sponsor/7/avatar.svg"></a>
<a href="https://opencollective.com/react-native-firebase/sponsor/8/website" target="_blank"><img src="https://opencollective.com/react-native-firebase/sponsor/8/avatar.svg"></a>
<a href="https://opencollective.com/react-native-firebase/sponsor/9/website" target="_blank"><img src="https://opencollective.com/react-native-firebase/sponsor/9/avatar.svg"></a>



### License

- See [LICENSE](/LICENSE)

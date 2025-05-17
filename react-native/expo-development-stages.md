# Expo Development Stages

[Expo Docs](https://docs.expo.dev)

### 1\. Expo Go 

Expo Go is a sandbox to quickly develop and test your first React Native app.

A React Native app consists of two parts: the **native app** (if using Expo Go, then Expo Go is the native app) and the **JavaScript bundle** (`npx expo start`). It is immutable and when you're using the Expo Go app for development, you can only rely on the native code and tools that exist in Expo Go. The only way to get around it is to build your native app yourself instead of using Expo's pre-packaged sandbox. This is exactly what a **Development Build is, your own version of Expo Go**, where you are free to use any native libraries and change any native config.

The **native app** (if using Expo Go, then Expo Go is the native app) is immutable once installed. Native build tools are required to create this bundle, and it needs to be signed to be installable on real devices. To add a new library with native code or change metadata that is shipped with the app (for example app name, icon, splash screen) the app needs to be rebuilt and re-installed on the device.

The **JavaScript bundle** (`npx expo start`) is where your app's UI code and business logic are. In production apps, there is one **main.js** bundle that is shipped with the app itself. In development, this JS bundle is live reloaded from your local machine. The main role of React Native is to provide a way for the JavaScript code to access the native APIs (Image, Camera, Notifications, and more). However, only APIs and libraries that were bundled in the **native app** can be used.

```
npx expo start
```

To run the app in our physical device, install Expo Go App and scan the QR code that will appear after running `npx expo start` with the camera of our device.

### 2\. Development build

[Development build](https://docs.expo.dev/develop/development-builds/introduction/)

**Why use a development build (a.k.a what can't you do in Expo Go and why)**

Expo Go is the perfect tool for learning, prototyping, and experimenting, but most production apps will convert to using development builds sooner rather than later. It helps to know exactly what is _impossible_ in Expo Go and _why_, so you can make an informed decision on when and why to make this move.

With Expo Go you can only use libraries bundled in Expo Go. To find out which libraries are bundled in Expo Go, go to [React Native Directory](https://reactnative.directory).

As a sandbox, one limitation of Expo Go is that it doesn't use your app specific package name or bundle identifier.


#### 2\.A\. Local Development build

```
npx expo prebuild
```
Creates /android and /ios folders in our App folder structure.

To modify your project's configuration or native code after the first build, you will have to rebuild your project. Running `npx expo prebuild` again layers the changes on top of existing files. It may also produce different results after the build.

To avoid this, add native directories (**ios/** and **android/**) to the project's **.gitignore** and use `npx expo prebuild --clean` command. This ensures that the project is always managed, and the --clean flag will delete existing directories before regenerating them. You can use app config or create a config plugin to modify your project's configuration or code inside the native directories.

We will need XCode and/or Android Studio to run de build locally.

```
npx expo run:ios
```
N.B. "Using development build" will appear in blue color below the QR code.

Here, we are NOT using Expo Go. We are using our own native app called "My App" (or whatever we called it).

The development build is the final result that users are going to get once you publish this application. In a development build, you can install libraries or packages that use native code.

One of the differences is that the Development build is an App on its own, not something inside the Expo Go App.

N.B. Check file eas_ios-simulator.md


#### 2\.B\. Development build using EAS (Expo Application Services)

N.B. Check file eas_eas-cli-setup.md and eas_ios-device.md

```
npm install -g eas-cli
```

```
eas -v
```

```
eas-cli/12.2.0
```

```
eas login
```
To login in to [expo.dev](https://expo.dev)

```
eas whoami
```

```
eas init
```

Creates eas.json in our project folder with "development", "preview" (e.g. to share with the Quality&Assurance testing team) and "production".

Before running the following command, add /ios and /android folders to .gitignore.

```
eas build --profile development --platform ios
```

Will ask if we want to install **expo-dev-client**. This is the package that allows us to run our bundle in a real device. The Expo Go app has the dev menu built in, and that's why you need to install it separately for a development build.

Will ask us to login to our Apple Developer Account and then generate an Apple certificate.

```
npx expo start
```


# EAS Tutorial

1. [EAS Tutorial](https://docs.expo.dev/tutorial/eas/introduction/)
2. Install [Expo Orbit](https://expo.dev/orbit)
3. [Video](https://www.youtube.com/watch?v=uQCE9zl3dXU): How to configure a development build 

# #1: Configure a development build in cloud

### Install expo-dev-client library
```terminal
npx expo install expo-dev-client
```

Start the development server
```terminal
npx expo start
```
_The development server now operates for a "development build" (instead of "Expo Go")._

### Install EAS CLI

Initialize a development build
```terminal
npm install -g eas-cli
```

**NOTE:** Gave EACCESS error for folder /usr/local/lib/node-modules

Checking node and npm versions to see if I can fix the error!!!!!
```terminal
(base) montse@Mac recipe-book % node -v
v21.4.0
(base) montse@Mac recipe-book % npm -v
10.2.4
```

[Fix](https://stackoverflow.com/questions/33725639/npm-install-g-less-does-not-work-eacces-permission-denied/40905762#40905762)


Sign up for an [Expo account](https://expo.dev/signup)

Log in
```terminal
eas login
```
_If it doesn't work, try ```npx eas login```_

Initialize and link the project to EAS
```terminal
eas init
```
_If it doesn't work, try ```npx eas init```_

```terminal
✔ Which account should own this project? > your-username
✔ Would you like to create a project for @your-username/sticker-smash? … yes
✔ Created @your-username/sticker-smash
✔ Project successfully linked (ID: XXXX-XX-XX-XXXX) (modified app.json)
```

Creates EAS project and provides a link to that project which we can open in the Expo dashboard.
Modifies app.json to include ```extra.eas.projectId``` and updates its value with the unique ID created

### Configure project for EAS Build

```terminal
eas build:configure
```
_If it doesn't work, try ```npx eas build:configure```_











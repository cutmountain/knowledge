# Create and run a local build for iOS device

[Create a Development build](https://docs.expo.dev/develop/development-builds/create-a-build/)


```bash
npx expo run:ios --device
```

_If it doesn't work, try ```npx...```_

```bash
(base) montse@Fidels-Air recipe-book % npx expo run:ios --device
  CocoaPods CLI not found in your PATH, installing it now.
› Attempting to install CocoaPods CLI with Gem
› Failed to install CocoaPods CLI with Gem
Failed to install CocoaPods CLI with gem (recommended)
└─ Cause: gem install cocoapods --no-document exited with non-zero code: 1
› Attempting to install CocoaPods CLI with Homebrew
› Failed to install CocoaPods with Homebrew. Please install CocoaPods CLI manually and try again.
⚠️  Unable to install the CocoaPods CLI.
Failed to install CocoaPods with Homebrew. Please install CocoaPods CLI manually and try again.
└─ Cause: spawn brew ENOENT
```

1\. [Uninstall homebrew](https://mac.install.guide/homebrew/5)

2\. [Install homebrew](https://mac.install.guide/homebrew/3)

(base) montse@Fidels-Air ~ % brew doctor
Please note that these warnings are just used to help the Homebrew maintainers
with debugging if you file an issue. If everything you use Homebrew for is
working fine: please don't worry or file an issue; just ignore this. Thanks!

Warning: Unbrewed header files were found in /usr/local/include.
If you didn't put them there on purpose they could cause problems when
building Homebrew formulae and may need to be deleted.

Unexpected header files:
  /usr/local/include/node/*
(base) montse@Fidels-Air ~ % 


N.B. [zshrc vs. zprofile](https://mac.install.guide/terminal/zshrc-zprofile)

3\. [Install asdf version manager](https://mac.install.guide/ruby/5)

Done: 
echo -e "\n. $(brew --prefix asdf)/libexec/asdf.sh" >> ~/.zprofile
Instead of:
echo -e "\n. $(brew --prefix asdf)/libexec/asdf.sh" >> ~/.zshrc


4\. [Update Ruby 3.4](https://mac.install.guide/ruby/update)
4\. Better, [Install Ruby with asdf] (https://mac.install.guide/ruby/6)

Falta fer: asdf global ruby 3.4.3
Però no cal si afegim ~/.tool-versions
ruby 3.4.3

Al final d'executar npx expo run:ios --device obtindrem:
› Installing /Users/montse/Library/Developer/Xcode/DerivedData/recipebook-coakbdqtvtjaulgcjurijdjmkscl/Build/Products/Debug-iphonesimulator/recipebook.app

_Ara ja podem obrir el fitxer .app amb XCode ???_


[Every Way to Build your React Native App with Expo | Expo Go, Prebuild, XCode, Android Studio & EAS](https://youtu.be/cs-zgHjt5RQ?si=caWLKWyiGHJwgf4y)


Ara ja podem obrir el fitxer /recipe-book/ios/recipebook.xcworkspace amb XCode. Provar de fer-ho amb ```xed ios```

XCode > Settings > accounts

XCode > Settings > Components

VSCode > Terminal > npx expo

Press i │ open iOS simulator

› Opening on iOS...
› Opening exp+recipe-book://expo-development-client/?url=http%3A%2F%2F192.168.2.169%3A8081 on iPhone 16 Pro
Error: Command failed: osascript -e tell app "System Events" to count processes whose name is "Simulator"
28:69: execution error: System Events ha donat un error: No s’està executant l’app. (-600)

Click on XCode > RUN button

Ara sí, per fi!!!!
-------------------------------------------------------------------------------------



npx expo run:ios --device

Select:
(Plugged) iPhone (18.4.1)

```bash
(base) montse@Fidels-Air recipe-book % npx expo run:ios --device 
✔ Select a device › 🔌 iPhone (18.4.1)
› Using --device 00008020-001C3C462252002E
› Your computer requires some additional setup before you can build onto physical iOS devices.
  Learn more
CommandError: No code signing certificates are available to use.
(base) montse@Fidels-Air recipe-book % 
```

XCode > Settings > accounts > Manage certificates...

[Setup Code Signing Certificates in XCode for Development](https://expo.fyi/setup-xcode-signing)


https://developer.apple.com/account

Certificates, Identifiers & Profiles


XCode > Window > Devices and Simulators

Select a physical device to build the app onto (XCode > recipebook > iPhone)

VSCode > terminal > npx expo run:ios --device
✔ Select a device › 🔌 iPhone (18.4.1)


› Metro waiting on exp+recipe-book://expo-development-client/?url=http%3A%2F%2F192.168.2.169%3A8081
› Scan the QR code above to open the project in a development build. Learn more

› Web is waiting on http://localhost:8081

› Using development build
› Press s │ switch to Expo Go

› Press a │ open Android
› Press i │ open iOS simulator
› Press w │ open web

› Press j │ open debugger
› Press r │ reload app
› Press m │ toggle menu
› shift+m │ more tools
› Press o │ open project code in your editor

› Press ? │ show all commands

› Installing /Users/montse/Library/Developer/Xcode/DerivedData/recipebook-coakbdqtvtjaulgcjurijdjmkscl/Build/Products/Debug-iphoneos/recipebook.app
✔ Complete 100%


npx expo start

Open URL manually: http://192.168.2.169:8081

Click on XCode > RUN button

Ara sí, per fi!!!!
-------------------------------------------------------------------------------------

Per instal·lar com a standalone, sense necessitat del servidor

XCode > recipebook > Edit Scheme...

Build configuration: Release

Click on XCode > RUN button


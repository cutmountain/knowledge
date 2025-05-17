# Create and run a cloud build for iOS device

[Create a Development build](https://docs.expo.dev/develop/development-builds/create-a-build/)

N.B. [Deploy React Native app on my phone](https://www.reddit.com/r/reactnative/comments/15ryfk3/how_do_i_deploy_a_reactnative_app_on_my_phone_for/?rdt=46560)

Prerequisites:

1. Apple Developer Account
2. [Developer Mode activated on iOS 16 and higher](https://docs.expo.dev/guides/ios-developer-mode/)

### Register an iOS device

```bash
eas device:create
```

_If it doesn't work, try ```npx...```_

```bash
eas build --platform ios --profile development
```

_If it doesn't work, try ```npx...```_

Development builds for iOS devices are generated in the **.ipa** format, which is standard for iOS app installations.






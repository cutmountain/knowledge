# Create and run a cloud build for iOS Simulator

[Create a Development build](https://docs.expo.dev/develop/development-builds/create-a-build/)

Create a simulator build profile in eas.json:

```json
{
  "build": {
    "development": {
    },
    "ios-simulator": {
      "extends": "development",
      "ios": {
        "simulator": true
      }
    }
  }
}
```

Development build for iOS Simulator

```bash
eas build --platform ios --profile ios-simulator
```
_npx..._

Development builds for iOS Simulators are generated in the **.app** format which is different from iOS devices.

https://expo.dev/accounts/<your-expo-dev-account-name>/projects/recipe-book/builds/a5875c8b-0344-45ef-927a-150d79ceac03

After adding expo-image-picker:
https://expo.dev/accounts/<your-expo-dev-account-name>/projects/recipe-book/builds/faa96cc7-1d94-4314-9b3e-c777b7f34f7f

```bash
npx expo start
```

Once the app has launched, we can press `m` on the terminal to open the app inside Expo Go!!!!!
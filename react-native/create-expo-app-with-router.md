# Create Basic Structure, choosing an example

```
(base) montse@Fidels-Air REPOS-HD % npx create-expo-app@latest --example

✔ Choose an example: › with-router
✔ What is your app named? … recipe-book-too

(base) montse@Fidels-Air REPOS-HD % cd recipe-book-too 

(base) montse@Fidels-Air recipe-book-too % npx expo install expo-sqlite

(base) montse@Fidels-Air recipe-book-too % npm run ios```
```

Ctrl+C

>The following packages should be updated for best compatibility with the installed expo version:
> react-native@0.76.3 - expected version: 0.76.7
> react-native-screens@4.1.0 - expected version: ~4.4.0

```
npm install react-native@0.76.7
```

```
npm install react-native-screens@4.4.0
```

```
(base) montse@Fidels-Air recipe-book-too % npm run ios```
```

app.json add:
    "newArchEnabled": true,


# Install React Native Elements for UI

```
(base) montse@Fidels-Air recipe-book-aaron % npm install @rneui/themed @rneui/base
```

```
(base) montse@Fidels-Air recipe-book-aaron % npm install react-native-safe-area-context
```

# References
[`Aaron Saunders - React Native Expo: Offline Data Storage with SQLite`](https://www.youtube.com/watch?v=vgPdAARd6Gw).

[`Native Notify - Expo Navigation with Expo Router | Dynamic Routes, Stack, Tabs, Link, useRouter | React Native`](https://youtu.be/D4XAhkjJXD4?si=gKPqosMpkFYhnZFO)

https://docs.expo.dev/router/advanced/tabs/
https://docs.expo.dev/versions/latest/sdk/sqlite/
https://www.sqlite.org/lang_expr.html
https://reactnativeelements.com

[`Code Step by Step - React Native tutorial #10 Props in react native`](https://youtu.be/wn46XV-dI4E?si=7Rwf661KHtNzzGRu)

# References for overcoming problems
https://stackoverflow.com/questions/28100214/how-can-i-use-the-like-operator-with-a-parameter-in-a-sqlite-query

# Reference for icons
https://icons.expo.fyi/Index

# Fixes

```
[NOT EXECUTED] npx react-native link react-native-gesture-handler
```

The following packages should be updated for best compatibility with the installed expo version:
  react-native-safe-area-context@4.14.1 - expected version: 4.12.0
  react-native-screens@4.9.2 - expected version: ~4.4.0
Your project may not work correctly until you install the expected versions of the packages.


The following packages should be updated for best compatibility with the installed expo version:
  expo@52.0.40 - expected version: ~52.0.41
  expo-sqlite@15.1.2 - expected version: ~15.1.3
Your project may not work correctly until you install the expected versions of the packages.
Commands to run
----------------------------------------

npm install -g react-native-cli

npm install -g rnpm

add the realm depency
----------------------
npm install -g react-native-cli
1). npm install --save realm

2). Next, link your project to the realm native module.

React Native >= 0.31.0

3). react-native link realm
React Native < 0.31.0

rnpm link realm

Warning for Android: Depending on the version, rnpm may generate an invalid configuration, updating Gradle correctly (android/settings.gradle and android/app/build.gradle) but failing to add the Realm module. Confirm that rnpm link has added the Realm module; if it has not, link manually to the library with the following steps:

1). Add the following lines to android/settings.gradle:

gradle include ':realm' project(':realm').projectDir = new File(rootProject.projectDir, '../node_modules/realm/android')

2). Add the compile line to the dependencies in android/app/build.gradle:

gradle dependencies { compile project(':realm') }


--------------------------------------------

react-native bundle --platform android --dev false --entry-file index.android.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res

Keep an AVD running on your system and the run following command

react-native run-android

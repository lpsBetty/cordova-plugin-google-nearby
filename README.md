[![](https://img.shields.io/npm/dm/cordova-plugin-google-nearby.svg)](https://www.npmjs.com/package/cordova-plugin-google-nearby)
# Description
Cordova Plugin to support [Google Nearby Messages API](https://developers.google.com/nearby/messages/overview) API for iOS and Android

# Platforms
- iOS
- Android

# Installation
## Requirements
- iOS only: Nearby pod has to be installed:

  * manually install using ```pod install``` and podfile

    OR

  * Using plugin cordova-plugin-cocoapod-support(https://github.com/blakgeek/cordova-plugin-cocoapods-support):
    * 1. install plugin
    * 2. add this line to config.xml:
```<pod name="NearbyMessages" />```
under ```<platform name="ios">```

  * follow steps 4-6: https://developers.google.com/nearby/messages/ios/get-started

- Android only:

  * follow steps 1-3 explained here: https://developers.google.com/nearby/messages/android/get-started

## Automatically
Cordova
```
cordova plugin add cordova-plugin-google-nearby --variable API_KEY="123456789"
```

Ionic v2
```
ionic cordova plugin add cordova-plugin-google-nearby --variable API_KEY="123456789"
```
## From source 
```
cordova plugin add https://github.com/hahahannes/cordova-plugin-google-nearby --variable API_KEY="123456789"
```

# Usage
The plugin provides three functions for subscription, publishing and unsubscribing.

## Cordova
### Subscribe
```
window.nearby.subscribe(function(success) {
    console.log(success)
}, function(error) {
     console.log(error)
})
```

### Publish
```
window.nearby.publish(message, function(success) {
    console.log(success)
}, function(error) {
    console.log(error)
})
```
### Un-Publish
```
window.nearby.unpublish(message, function(success) {
    console.log(success)
}, function(error) {
    console.log(error)
})
```

### Unsubscribe
```
window.nearby.unsubscribe(function(success) {
    console.log(success)
}, function(error) {
    console.log(error)
})
```

## Ionic 
- you can use [Ionic Native](https://ionicframework.com/docs/native/) 

### Installation

```
ionic cordova plugin add cordova-plugin-google-nearby
npm install --save @ionic-native/google-nearby
```

### Subscribe
```
import { GoogleNearby } from '@ionic-native/google-nearby';
subscribtion: any
constructor(private nearby: GoogleNearby) { 
    this.subscribtion = this.nearby.subscribe().subscribe(result => {
        console.log(result)
    })
}
```

### Unubscribe
```
import { GoogleNearby } from '@ionic-native/google-nearby';
constructor(private nearby: GoogleNearby) { }
this.subscribtion.unsubscribe()
```

### Publish
```
import { GoogleNearby } from '@ionic-native/google-nearby';
constructor(private nearby: GoogleNearby) { }
this.nearby.publish(message).then(result => {
    console.log(result)
})
```
### Un-Publish
```
import { GoogleNearby } from '@ionic-native/google-nearby';
constructor(private nearby: GoogleNearby) { }
this.nearby.unpublish(message).then(result => {
    console.log(result)
})
```

# Debug
```shell
adb logcat 
```

# Remove
Cordova
```
cordova plugin rm org.apache.cordova.nearby
```

Ionic
```
ionic cordova plugin rm org.apache.cordova.nearby
```

# Troubleshooting Android
- make sure that the following content is in the AndroidManifest.xml
- make sure that the following content is in the build.gradle file
- make sure you have the requirements from above
- check in the nearby settings if your app is deactivated 

# Notes
For cordova-android v7 and above use version 1.1.5 of this plugin.

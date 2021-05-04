# safe_device (Null-Safety) <a href="https://pub.dev/packages/safe_device" src="https://img.shields.io/badge/pub-1.0.0-blue"></a>


Flutter (Null-Safety)Jailbroken, root, emulator and mock location detection.

Uses [RootBeer](https://github.com/scottyab/rootbeer) for Android root detection and [DTTJailbreakDetection](https://github.com/thii/DTTJailbreakDetection) for iOS jailbreak detection.
Inspired by [jail-monkey](https://github.com/GantMan/jail-monkey) and [this blog article](http://blog.geomoby.com/2015/01/25/how-to-avoid-getting-your-location-based-app-spoofed/)

## Getting Started

In your flutter project add the dependency:

```yml
dependencies:
  ...
  safe_device: ^1.0.0
```


## Usage
#### Importing package
```
import 'package:safe_device/safe_device.dart';
```
#### Using it

Checks whether device JailBroken on iOS/Android?
```
bool isJailBroken = await SafeDevice.isJailBroken;
```
Checks whether device is real or emulator
```
bool isRealDevice = await SafeDevice.isRealDevice;
```
Can this device mock location - no need to root!
```
bool canMockLocation = await SafeDevice.canMockLocation;
```
(ANDROID ONLY) Check if application is running on external storage
```
bool isOnExternalStorage = await SafeDevice.isOnExternalStorage;
```
Check if device violates any of the above
```
bool isSafeDevice = await SafeDevice.isSafeDevice;
```

# Note:
#### Mock location detection
* **Android** - Location permission needs to be granted in app in order to detect mock location properly
* **iOS** - For now we are checking if device is Jail Broken or if it's not real device. There is no strong detection of mock location in iOS *(Open the PR if you have better way for mock location detection in iOS)*

## ❗Since emulators are usually rooted, you might want to bypass these checks during development. Unless you're keen on constant false alarms ⏰
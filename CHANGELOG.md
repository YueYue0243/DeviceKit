# Changelog

## Version 2.1.0

Releasedate: 2019-09-01

```ruby
pod 'DeviceKit', :git => 'https://github.com/devicekit/DeviceKit.git', :branch => 'master'
```

### New features
- Add support for the new iPod touch (7th generation) ([#189](https://github.com/devicekit/DeviceKit/pull/189))
- Added `Device.allApplePencilCapableDevices` and `Device.current.applePencilSupport` variables for checking Apple Pencil support. ([#179](https://github.com/devicekit/DeviceKit/pull/179))
  - `.applePencilSupport` returns `ApplePencilSupport.firstGeneration` or `ApplePencilSupport.secondGeneration` for checking which Apple Pencil is supported.
- Added 3D Touch (iOS) and Force Touch (watchOS) support variables: ([#183](https://github.com/devicekit/DeviceKit/pull/183))
  - iOS
    - `Device.allDevicesWith3dTouchSupport`
    - `Device.current.has3dTouchSupport`
  - watchOS
    - `Device.allWatchesWithForceTouchSupport`
    - `Device.current.hasForceTouchSupport`
- Added variable to check for the camera's a device has. ([#188](https://github.com/devicekit/DeviceKit/pull/188))
  - Example: `Device.iPhoneXS.cameras` should return `CameraTypes.normal` and `CameraTypes.telephoto`.

### Fixes
- Rename iPod touch 5 and 6 to iPod touch (5th generation) and iPod touch (6th generation) respectively. ([#189](https://github.com/devicekit/DeviceKit/pull/189))
- Rename Apple TV (4th generation) to Apple TV HD to comply with Apple's rename of the device. ([#196](https://github.com/devicekit/DeviceKit/pull/196))
- Improve support for Swift Package Manager. ([#193](https://github.com/devicekit/DeviceKit/pull/193))
- Fixed the `Device.current.isZoomed` variable. ([#59 comment](https://github.com/devicekit/DeviceKit/issues/59#issuecomment-519457674) and [#198](https://github.com/devicekit/DeviceKit/pull/198))


## Version 2.0.0

Releasedate: 2019-04-10

```ruby
pod 'DeviceKit', '~> 2.0'
```

### Breaking changes
- The original `Device()` constructor has been made private in favour of using `Device.current` to match `UIDevice.current`.
- The enum values for the iPhone Xs, iPhone Xs Max and iPhone Xʀ have been renamed to be `.iPhoneXS`, `.iPhoneXSMax` and `.iPhoneXR` to match proper formatting.
- `.description` for the iPhone Xs, iPhone Xs Max and iPhone Xʀ have been changed to contain small caps formatting for the s and the ʀ part.
- `.description` for the iPad 5 and iPad 6 have been changed to the proper names; iPad (5<sup>th</sup> generation) and iPad (6<sup>th</sup> generation).
- `.name`, `.systemName`, `.systemVersion`, `.model`, `.localizedModel`, `.batteryState` and `.batteryLevel` will now all return nil when you try to get its value when the device you are getting it from isn't the current one. (eg. `Device.iPad6.name` while running on iPad 5)

### New features
- Updated to Swift 5!
- New `.allDevicesWithRoundedDisplayCorners` and `.hasRoundedDisplayCorners` values to check if a device has rounded display corners. (eg. iPhone Xs and iPad Pro (3<sup>rd</sup> generation))
- new `.allDevicesWithSensorHousing` and `.hasSensorHousing` values to check if a device has a screen cutout for the sensor housing. (eg. iPhone Xs)

### Bugfixes
- `.isPad` and `.isPhone` are now giving correct outputs again.

## Version 1.13.0 (Last Swift 4.2 release)

Releasedate: 2019-03-29

```ruby
pod 'DeviceKit', '~> 1.13'
```

### New iPads
Added new iPad Mini (5th generation) and iPad Air (3rd generation)
```swift
Device.iPadMini5 // iPad Mini (5th generation)
Device.iPadAir3 // iPad Air (3rd generation)
```

<p align="center">
  <img src="Assets/banner.png" width="780" title="RandomUserSwift">
</p>

[![CocoaPods Version Status](https://img.shields.io/cocoapods/v/RandomUserSwift.svg)][podLink]
[![Carthage compatible](https://img.shields.io/badge/Carthage-Compatible-brightgreen.svg?style=flat)](https://github.com/Carthage/Carthage)
[![CocoaPods](https://img.shields.io/cocoapods/dt/RandomUserSwift.svg)](https://cocoapods.org/pods/RandomUserSwift)
[![CocoaPods](https://img.shields.io/cocoapods/dm/RandomUserSwift.svg)](https://cocoapods.org/pods/RandomUserSwift)
![Platform](https://img.shields.io/badge/platforms-iOS-333333.svg)
[![Swift](https://img.shields.io/badge/Swift-3.0+-orange.svg)](https://swift.org)
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)][mitLink]

<p align="center">
  <img src="Assets/screenshot.gif" width="369" title="Screenshot">
</p>

RandomUserSwift is an easy to use Swift framework that provides the ability to generate Random Users and their accompanying data for your Swift applications. It utilizes [randomuser.me](http://www.randomuser.me) API to generate the data.

1. [Requirements](#requrements)
2. [Integration](#integration)
    - [Cocoapods](#cocoapods)
    - [Carthage](#carthage)
    - [Manually](#manually)
3. [Usage](#usage)
4. [Example](#example)
5. [License](#license)

## Requirements

- Swift 3
- iOS 10
- Xcode 8

## Integration

#### CocoaPods
You can use [CocoaPods](http://cocoapods.org/) to install `RandomUserSwift`by adding it to your `Podfile`:
```ruby
platform :ios, '10.0'
use_frameworks!

target 'MyApp' do
	pod 'RandomUserSwift'
end
```
Note: your iOS deployment target must be 10.0:

#### Carthage
You can use [Carthage](https://github.com/Carthage/Carthage) to install `RandomUserSwift` by adding it to your `Cartfile`:
```
github "dingwilson/RandomUserSwift"
```

#### Manually

To use this library in your project manually you may:  

1. for Projects, just drag RandomUser.swift and User.swift files to the project tree
2. for Workspaces, include the whole RandomUserSwift.xcodeproj

## Usage

```swift
import RandomUserSwift
```
Import the framework into the ViewController

```swift
var randomUser: RandomUser! = RandomUser()
```
Define a randomUser object, which you will use to get a random user.

```swift
randomUser.gender = "male"
```
(Optional) You can select the gender of the users you wish to recieve. Possible selections include `both`, `male`, or `female`. The default is `both`.

```swift
randomUser.nationality = "us,dk,fr,gb"
```
(Optional) You can select the nationality of the users you wish to recieve. Possible selections include `au,br,ca,ch,de,dk,es,fi,fr,gb,ie,ir,nl,nz,tr,us`. You can select multiple nationalities by chaining them together with a comma in between. The default is `us`. 

```swift
randomUser.getUser { success, user in
    if success {
        if let randUser = user as? User {
            // You can now access every aspect of the user.
            print(randUser)
        }
    }
}
```
Use the `getUser` function with a completion handler, and set the `user` response equal to a `User` object. You can then loop through the object and gather whatever data you are interested in. Possible datapoints include `gender`,`title`,`firstName`,`lastName`,`street`,`city`,`state`,`zip`,`email`,`username`,`password`,`salt`,`md5`,`sha1`,`sha256`,`dateOfBirth`,`dateRegistered`,`homePhone`,`cellPhone`,`pictureLargeURL`,`pictureMediumURL`,`pictureThumbnailURL`.

## Example

To view the included example `RandomUserGenerator`, simply run `pod install` to get the latest version of the `RandomUserSwift`, and then open the `RandomUserGenerator.xcworkspace` and run on a compatible iPhone simulator or iOS device.

Note: If you have used RandomUserSwift in your own app, please feel free to submit a PR to have a link of your app added to this section!

## License

`RandomUserSwift` is released under an [MIT License][mitLink]. See `LICENSE` for details.

**Copyright &copy; 2016-present Wilson Ding.**

*Please provide attribution, it is greatly appreciated.*

[podLink]:https://cocoapods.org/pods/RandomUserSwift
[mitLink]:http://opensource.org/licenses/MIT

# Azure DevOps Pipeline for XCode Projects + AppCenter on Real Devices Testing

This project has been created for demonstration purposes only for Microsoft Azure users who are looking for a sample demonstration of automating XCode projects Build, Test and deploy using Azure DevOps and Visual Studio AppCenter.

## About this repository

The App Center SDK modules are already integrated within the application. Simply follow the tutorials to learn how to use each service.

### Build status (master branch)

| Build Service   | Status                                                                                                                                                                                                                                                             |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| App Center      | [![Build status](https://build.appcenter.ms/v0.1/apps/45f31a4b-96a1-4c49-9c26-b2726e00a33d/branches/master/badge)](https://appcenter.ms)                                                                                                                           |
| Azure Pipelines | [![Build Status](https://dev.azure.com/msmobilecenter/Mobile-Center/_apis/build/status/sampleapp/microsoft.appcenter-sampleapp-ios-swift?branchName=master)](https://dev.azure.com/msmobilecenter/Mobile-Center/_build/latest?definitionId=3726&branchName=master) |

## Build the app

After forking the repository, you'll need to install CocoaPods to build the app.

```sh
sudo gem install cocoapods
```

Next, install the dependencies.

```sh
pod install
```

Open the .xcworkspace. The app can now build and run. You can learn to use the sample app with App Center with the tutorials below.

## Codesigning

Auto Codesigning have been used for this project using my iOS team profile. You have to upload your certificate + team provisioning profile which was used for the codesigning "Auto".

To sign the app in Xcode:

1. Open **.xcworkspace** from the sample app's folder.
2. Go to **General** within the .xcworkspace file.
3. Under **Identity**, edit the **Bundle Identifier** to match the app ID.
4. Import and select the provisioning profile under **Signing (Debug)** and **Signing (Release)**.

## Useful commands for local Appcenter testing for this project:

```
xcrun xcodebuild build-for-testing \
  -configuration Debug \
  -workspace sampleapp-ios-swift.xcworkspace\
  -sdk iphoneos \
  -scheme sampleapp-ios-swift \
  -derivedDataPath DerivedData    
```

```
appcenter test run xcuitest \
  --app "mfadin-microsoft.com/sampleios" \
  --devices "mfadin-microsoft.com/iphone13" \
  --test-series "main" \
  --locale "en_US" \
  --build-dir DerivedData/Build/Products/Debug-iphoneos
```

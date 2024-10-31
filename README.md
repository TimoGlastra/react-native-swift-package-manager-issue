# React Native Swift Package Manager Issue

Adding the `https://github.com/eu-digital-identity-wallet/eudi-lib-ios-iso18013-data-transfer.git` package to a react native project using the new `spm_dependency` method available in podpsecs causes `Duplicate symbols` issue when building, even using `USE_FRAMEWORKS=dynamic`

Reproduction

- Clone this repo
- `npm install`
- `cd ios && USE_FRAMEWORKS=dynamic pod install`
- Open in xcode and build.

The error is `18460 duplicate symbols`.

The PR that added support for this (https://github.com/facebook/react-native/pull/44627) mentions the duplicate symbols can be fixed by using `USE_FRAMEWORKS=dynamic` during pod install, but this does not seem to address the issue.

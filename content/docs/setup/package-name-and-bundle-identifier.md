---
title: "Package name and bundle identifier"
description: ""
lead: ""
date: 2021-04-05T08:48:57+00:00
lastmod: 2021-04-05T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "Setup"
weight: 99
toc: true
---

Every flutter project contains 2 Ids: package name (for android) and bundle
identifier (for iOS), these ids must be unique. So, you must change them.
## Android

1. Go to `android/app/src/(main, debug, profile)/AndroidManifest.xml` (3
files) and search for `package` and replace the old package with your
package.

2. Go to `android/app/build.gradle` and search for `applicationId` and
replace the old package with your package.

3. Go to `android
app/src/main/kotlin/com/example/NourishNow/(MainActivity.kt,
Application.kt)` (2 files) and search for `package` keyword and replace
the old package with your package.

4. Change the directory name from:
`android\app\src\main\kotlin\com\example\NourishNow`
to: `android\app\src\main\kotlin\your\package\name`
`(your.package.name)`

## iOS
Go to `ios/Runner.xcodeproj/project.pbxproj` and search for:
`PRODUCT_BUNDLE_IDENTIFIER`
and replace the old bundle identifier with yours (there are 3
replacement).

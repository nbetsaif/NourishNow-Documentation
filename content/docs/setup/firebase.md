---
title: "Firebase"
description: ""
lead: ""
date: 2021-04-05T08:48:57+00:00
lastmod: 2021-04-05T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "Setup"
weight: 102
toc: true
---


Go to firebase [console](https://console.firebase.google.com/) and create project and choose a name.

## Android
1. Add two android apps: for admin and user .

2. For the user app, you need to generate a signing certificate for google
authentication. Go to CMD and type:
`keytool -list -v -alias androiddebugkey -keystore %USERPROFILE%\.android\debug.keystore`
And replace `%USERPROFILE%` with your Windows username.

3. Download google-services.json file.

4. Copy and paste the file into android/app.

5. After these steps, you will have two apps: for admin and user.

## IOS
1. Add two iOS apps: for admin and user.

2. Download GoogleService-Info.plist file.

3. Copy and paste the file into ios/Runner.

4. Add these files using XCODE(open Runner.xcodeproj).

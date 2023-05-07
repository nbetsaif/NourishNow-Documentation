---
title: "Maps"
description: ""
lead: ""
date: 2021-04-05T08:48:57+00:00
lastmod: 2021-04-05T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "Setup"
weight: 107
toc: true
---

###### here are the steps to integrate Google Maps.

1. Go to the Google Cloud Console [https://console.cloud.google.com/](https://console.cloud.google.com/)
2. If you haven't already, create a new project by clicking on the "Select a project" dropdown at the top of the page, and then clicking on "New Project". Give your project a name and click on "Create".
3. Once you have created or selected a project, click on the hamburger menu (three horizontal lines) in the top left corner of the page and select "APIs & Services" from the dropdown menu.
4. Click on the "Library" tab on the left-hand side of the page to see the available APIs.
5. Search for "Maps SDK for Android" and select it.
6. Click on the "Enable" button.
7. Repeat steps 5-6 for the following API: Maps SDK for iOS
8. Once you have enabled all the necessary APIs, go to the "Credentials" page by clicking on the "Credentials" tab on the left-hand side of the page.
9. Click on the "Create credentials" button and select "API key".
10. You can then copy this API key and use it in your app to integrate Google Maps.

**note**: You have to add the Api key on both admin and user app.

### Android
1. Open the AndroidManifest.xml file for your Android app, which can be found in the following directory: `android/app/src/main/AndroidManifest.xml`.
2. Add the following code inside the <application> tag: 
    ```xml
    <meta-data
    android:name="com.google.android.geo.API_KEY"
    android:value="YOUR_API_KEY"/>
3. Replace YOUR_API_KEY with the API key that you obtained from the Google Cloud Console.
### IOS
1. go to `ios/Runner/AppDelegate.swift`.
2. Add the following code snippet to the AppDelegate.swift file:

    ```swift
    import UIKit
    import Flutter
    import GoogleMaps

    @UIApplicationMain
    @objc class AppDelegate: FlutterAppDelegate {
    override func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
    ) -> Bool {
        GMSServices.provideAPIKey("YOUR_API_KEY_HERE")
        GeneratedPluginRegistrant.register(with: self)
        return super.application(application, didFinishLaunchingWithOptions: launchOptions)
    }
    }
3. Replace YOUR_API_KEY_HERE with the API key that you obtained from the Google Cloud Console.

# Ti.DoubleClick Module

## Description

DoubleClick for Publishers (DFP) users can utilize this module to deliver
directly sold ads into applications and monetize on unfilled inventory through the Google AdMob
advertising network

## Getting Started

View the [Using Titanium Modules](http://docs.appcelerator.com/titanium/latest/#!/guide/Using_Titanium_Modules) document for instructions on getting
started with using this module in your application.

## Accessing the Ti.DoubleClick Module

To access this module from JavaScript, you would do the following (recommended):

	var DoubleClick = require('ti.doubleclick');

## Requirements

* The Google AdMob Ads SDK for Android requires a run-time of Android 1.5 or later (set android:minSdkVersion to at least 3 in your AndroidManifest.xml).
This means you can develop with the latest version of the Android SDK and your app will still run on an earlier Android version (1.5 minimum).

* Make sure you have the latest copy of the Android SDK and that you're compiling against at least Android v3.2 (set target in default.properties to android-13).

<strong>You must set the `tool-api-level` in your application's `tiapp.xml` file to at least level 13</strong>

### Example

    <modules>
        <module platform="android" version="3.0">ti.doubleclick</module>
        <module platform="iphone" version="3.0">ti.doubleclick</module>
    </modules>
    <android>
        <tool-api-level>14</tool-api-level>
    </android>

## Breaking Changes

If you are upgrading from an earlier version of this module (prior to version 3.0) you should be
aware of the following breaking changes to the API:

* The `createView` method has been replaced with the `createBannerAdView` method
* The properties used in the `createBannerAdView` method are different than those used in the `createView` method
* The old events for the view have been replaced with new events

## Doubleclick for Publishers Developer Docs
<https://developers.google.com/mobile-ads-sdk/>

## Functions

### Ti.DoubleClick.createBannerAdView({ . . . })

Creates and returns an instance of [Ti.DoubleClick.BannerAdView][]

#### Arguments

parameters[object]: a dictionary object of properties defined in [Ti.DoubleClick.BannerAdView][].

#### Example:

    var ad = DoubleClick.createBannerAdView({
        top: 0, left: 0,
        width: 320 + u, height: 50 + u,
        adUnitId: '<< YOUR AD UNIT ID HERE >>',
        adSize: { width: 320, height: 50 },
        validAdSizes: [
            { width: 320, height: 50 },
            { width: 250, height: 250 },
            { width: 120, height: 20 }
        ],
        testing: true,
        customTargeting: {
            dateOfBirth: new Date(1985, 10, 1, 12, 1, 1),
            gender: 'male',
            keywords: 'test'
        }
    };

### Ti.DoubleClick.createInterstitialAd({ . . . })

Creates and returns an instance of [Ti.DoubleClick.InterstitialAd][]

#### Arguments

parameters[object]: a dictionary object of properties defined in [Ti.DoubleClick.InterstitialAd][].

#### Example:

    var ad = DoubleClick.createInterstitialAd({
        adUnitId: '<< YOUR AD UNIT ID HERE >>',
        testing: true
    });

## Author

Jeff English

## Module History

View the [change log](changelog.html) for this module.

## Feedback and Support

Please direct all questions, feedback, and concerns to [info@appcelerator.com](mailto:info@appcelerator.com?subject=iOS%20Doubleclick%20Module).

## License

Copyright(c) 2010-2013 by Appcelerator, Inc. All Rights Reserved. Please see the LICENSE file included in the distribution for further details.

[Ti.DoubleClick.BannerAdView]: banneradview.html
[Ti.DoubleClick.InterstitialAd]: interstitialad.html
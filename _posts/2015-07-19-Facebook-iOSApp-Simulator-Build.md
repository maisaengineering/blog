---
layout:     post
title:      Facebook-iOS Application Simulator Build
date:       2015-07-19 04:47:59
summary:    
categories: iOS, Facebook
author: Chandan
---

If you are in a process of submitting your iOS app for Facebook review with simulator build, read on...

Follow instructions as per [Facebook Simulator Build](https://developers.facebook.com/docs/ios/getting-started) **till* "Create a Simulator Build".

Since atleast from latest Xcode(6+), installed app path changed on Simulator build. We have to look for installed app in new location.

###### OLD LOCATION (broken)
```
ditto -ck --sequesterRsrc --keepParent `ls -1 -d -t ~/Library/Developer/Xcode/DerivedData/*/Build/Products/*-iphonesimulator/*.app  | head -n 1` path/to/YourApp.zip
```

###### NEW LOCATION (works)
```
ditto -ck --sequesterRsrc --keepParent `ls -1 -d -t ~/Library/Developer/CoreSimulator/Devices/*/data/Containers/Bundle/Application/*/*.app| head -n 1` path/to/YourApp.zip
```

Rest of the instructions works fine.

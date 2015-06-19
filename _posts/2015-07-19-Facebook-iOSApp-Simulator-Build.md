---
layout:     post
title:      Facebook-iOS Application Simulator Build
date:       2015-07-19 04:47:59
summary:    
categories: iOS, Facebook
author: Chandan
---

If you are in a process of submitting your iOS app for Facebook review with simulator build, read on...

Follow instructions as listed on https://developers.facebook.com/docs/ios/getting-started till "Create a Simulator Build"

Atleast with latest Xcode(6+), iOS application path changed. 

### OLD (broken)
```
ditto -ck --sequesterRsrc --keepParent `ls -1 -d -t ~/Library/Developer/Xcode/DerivedData/*/Build/Products/*-iphonesimulator/*.app  | head -n 1` path/to/YourApp.zip
```

### NEW
```
ditto -ck --sequesterRsrc --keepParent `ls -1 -d -t ~/Library/Developer/CoreSimulator/Devices/*/data/Containers/Bundle/Application/*/*.app| head -n 1` path/to/YourApp.zip
```

Rest are same.

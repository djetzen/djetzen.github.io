---
layout: post
title:  "Exodus Privacy"
date:   2019-09-23
categories: privacy
---

## Overview
Today I want to introduce [Exodus Privacy](https://exodus-privacy.eu.org/en/) which analyses the sorts and amount of trackers inside Androd apks. Trackers are modules that analyse your behavior or record your usage and then send it to someone else. Unfortunately this app is not available at iOS, as this is forbidden by Apples DRM. So exodus only analyzes the code of Android apps for embedded trackers and gives you a list of the ones included. 
You can either search on the [website](https://reports.exodus-privacy.eu.org/en/search/) or download the app from [here](https://f-droid.org/en/packages/org.eu.exodus_privacy.exodusprivacy/) or the Google Play Store. Of course the plugin is open source, so you can find the source code on [GitHub](https://github.com/exodus-privacy/).

## Short Explanation
After opening and doing an analysis in the app you will see a list of all your apps installed and which have been checked so far by exodus. For each app there are the attributes `Tracker` and `Permissions`. By clicking on the app icon you can see the details of all the permissions and the trackers. Exodus itself say on their blog in a [post](https://exodus-privacy.eu.org/en/post/exodus_static_analysis/), that they do some static code analysis instead of decompiling the app. 

## Conclusion
So after the initial install and before opening a new app the first time I recommend checking this app for additional trackers with exodus. You will be surprised how many trackers are part of your apps which you use every day, at least for me it was a huge surprise. I do this regularly and if I do not really need this new app, I uninstall it, if too many trackers are included. Also contributions are always welcome, as you can see [here](https://exodus-privacy.eu.org/en/page/contribute/). I think exodus is a really helpful tool for becoming aware of what is included in the apps you currently have installed or you are planning to install.
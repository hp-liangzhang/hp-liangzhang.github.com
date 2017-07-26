---
layout: post
title:  "Session"
date:   2017-07-26 00:41:35 +0800
categories: Configuration
---

## exports all mobility apps in Hello API

The default value is *disable*. 
```
session.renew=disable
```

Usually the *renew* action will make the application slowlier for it create a new session of a different session id every time when an client calling Hello api which has a session Id before, then delete the old session.
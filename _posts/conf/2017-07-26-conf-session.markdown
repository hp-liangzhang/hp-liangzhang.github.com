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

Usually the *renew* action makes the application slower because of more database operations. It duplicates a new session from the old one (if there is one) with a different session ID, then delete the old session.
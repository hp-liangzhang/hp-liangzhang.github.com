---
layout: post
title:  "Database Optimization"
date:   2016-03-1 00:41:34 +0800
categories: Deployment
---

# Index
To speed up queries, please add index to those tables.

```shell
Device
    uuid

Users
    serialNumber

ClientSessionImpl
    userSN
    deviceId
    deviceUuid

ClientAppRevision
    appVersion
    operatingSystem
    status
    updateTime

MobilityApp
    updateTime
    code

MobilityAppRevision
    mobilityAppCode
    version
    status
```


# Archive 
The table 'EventLog' will stored a huge amount of records after months. It will be very slow to generate reports from it. A way to get rid of this issue is to archiving the old data (let's the data which are old then 3 months) in to another table (named by date).s


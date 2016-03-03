---
layout: post
title:  "Hello"
date:   2016-02-3 00:41:34 +0800
categories: ClientApi
---

# Hello

## URL
/client/hello


## METHOD
POST

## Request Parameters

| Param   | Required | Type |  Optional Values |  Descscription |
|---------|:--------:|:----:|------------------|:---------------|
|  |  |  |  |  |
| dev.uuid | true | String | | uuid of a device |
| dev.type | false | String | Moble, Tablet |  |
| dev.manufacturer | false | String |  |  |
| dev.model | false | String |  |  |
| dev.resWidth | false | Number |  | The width of the device screen |
| dev.resHeight | false | Number |  | The height of the device screen |
| dev.retina | false | Boolean | true, false | if the screen is retina or not (for iOS devices) |
| os.name | true | String | Android, iOS, WebOS, Windows_Mobile |  |
| os.version | true | String | 0.0.0 | the version of the device. e.g. 9.0.2 |
| app.name | true | String |  | name of a client app. e.g. com.abc.mobile.app |
| app.seed | true | String |  | a random string |
| env.netType | false | String |  | e.g. CDMA |
| env.pushToken | false | String |  |  |
| env.longitude | false | Number |  |  |
| env.latitude | false | Number |  |  |
| env.locale | false | String |  | e.g. en|

## Request Example

```shell
curl 'http://eoserver.com/client/hello?dev.uuid=1234234123123&dev.type=Mobile&dev.manufacturer=&dev.model=&dev.resWidth=&dev.resHeight=&dev.retina=&os.name=iOS&os.version=8.0&app.name=com.abc.mobile.app&app.version=3.2.0&app.seed=_RANDOM_&env.netType=&env.pushToken=&env.longitude=&env.latitude=&env.altitude=&env.locale=en'
```

## Response Example

```javascript
{
    "timestamp": 1456985519064,
    "environment": {
        "server": "dev"
    },
    "secretKey": "Tv7EBTrM8SgBxIwN",
    "allMobilityApps": {
        "system": [{
            "id": "Bootstrap",
            "version": "3.3.0-3",
            "token": "0CKxxZdTVq",
            "size": 0
        }, {
            "id": "framework",
            "version": "3.3.0-34",
            "token": "rvH3TkWOMU",
            "size": 0
        }, {
            "id": "Login",
            "version": "3.3.0-3",
            "token": "PNDLRLItQJ",
            "size": 0
        }, {
            "id": "CommonService",
            "version": "3.3.0-19",
            "token": "jYZDCXORey",
            "size": 0
        }],
        "user": [{
            "id": "MyDemo",
            "version": "2.5.0-7",
            "token": "0RzpGZfEwf",
            "size": 0
        }]
    },
    "sessionId": "512ee6e9-3607-417f-893b-a639fb9c6e4d",
    "protocols": {
        "login": "http"
    },
    "mobilityApps": {
        "system": [ {
            "id": "framework",
            "version": "3.3.0-34",
            "token": "rvH3TkWOMU",
            "size": 0
        }, {
            "id": "Login",
            "version": "3.3.0-3",
            "token": "PNDLRLItQJ",
            "size": 0
        }],
        "user": []
    }
}
```

## Error
Server sends a response of "*HTTP Status: 403 / Forbidden*" if there are any errors.

When app.version is invalid: 

```javascript
    {
        "message": "Invalid Application Version",
        "updateUrl": "http://ios-update-link/",
        "code": "1-2",
        "updateMessage": ""
    }
```

When os.version is invalid:

```javascript
    { "message": "Invalid Application Version", "code": "1-2" }
```
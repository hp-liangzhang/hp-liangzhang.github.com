---
layout: post
title:  "List mobility apps"
date:   2016-02-3 00:41:53 +0800
categories: ClientApi
---

# List mobility apps
Retrieve metadata or content of manifest of mobility apps.

## URL
/client/mobilityapps

## METHOD
POST

## Request Parameters

| Param   | Required | Type |  Optional Values |  Descscription |
|---------|:--------:|:----:|-------------|:---------------|
|  |  |  |  |  |
| sessionId | true | String | | the session id is accquired from Hello API |
| as | true | String | meta, manifest | meta: indicate retrieve data (id/token/size), manifest: retrieve content of manifest |
| mobilityApps | false | string |  | a Jason Array String, such as: {"Bootstrap": "1.0.0", "Login": "1.1.0". It indicates which apps of which version should be retrieved. When it is empty, server will send all apps that is available for this session. |
| env.locale | false | String |  | only works when as == 'manifest'. It indicates manifest in which language should be retrieved. The default value is 'en'. |

## Request Example

```shell
curl 'http://eosserver/client/properties'
```

## Response Example
A Json Array.

```javascript
{
    "mobilityApps": {
        "system": [{
            "id": "Login",
            "version": "3.3.0-3",
            "token": "PNDLRLItQJ",
            "size": 113255
        }, {
            "id": "res",
            "version": "2.5.0",
            "token": "GiY2v7VydV",
            "size": 91426
        }, {
            "id": "MyCustomersSrv",
            "version": "2.5.0-3",
            "token": "0FPYV1QFeR",
            "size": 14680
        }, {
            "id": "MyCustomersApi",
            "version": "3.4.0",
            "token": "7Sw22u4Ag6",
            "size": 230672
        }],
        "user": [{
            "id": "myapp",
            "version": "3.4.0-5",
            "token": "zLgAv6Bmi3",
            "size": 689733
        }, {
            "id": "resource",
            "version": "3.3.0-6",
            "token": "ykA2Nvpcn9",
            "size": 8960
        }]
    }
}
```

## Error
Server sends a response of "*HTTP Status: 403 / Forbidden*" if the session is invalid.

```javascript
{ "message": "Invalid sessionId", "code": "2-2" }
```
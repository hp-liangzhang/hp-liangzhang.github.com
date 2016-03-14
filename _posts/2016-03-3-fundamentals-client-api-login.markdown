---
layout: post
title:  "Login"
date:   2016-02-3 00:41:57 +0800
categories: ClientApi
---

# Login
Login with credentials.

## URL
/client/login


## METHOD
POST

## Request Parameters

| Param   | Required | Type |  Optional Values |  Descscription |
|---------|:--------:|:----:|------------------|:---------------|
|  |  |  |  |  |
| sessionId | true | String | | the session id is accquired from Hello API |
| domain | false | String |  | A user-defined value， which is used to locate which extension to use for handle login/relogin/refresh/logout API |
| loginName | false | String |  |  |
| password | false | String |  |  |


## Request Example

```shell
curl 'http://eosserver/client/login' --data 'sessionId=9a0b6679-c460-41a3-b26c-26e0d69538c6&domain=customers&loginName=foobat&password=anypwd'
```

## Response Example

```javascript
{
    "expireTime": 1458356527606,
    "secureCode": "20004007594",
    "mobilityApps": {
        "system": [{
            "id": "res",
            "version": "2.5.0",
            "token": "GiY2v7VydV",
            "size": 0
        }, {
            "id": "MyCustomersSrv",
            "version": "2.5.0-3",
            "token": "0FPYV1QFeR",
            "size": 0
        }],
        "user": [{
            "id": "MyDemo",
            "version": "2.5.0-7",
            "token": "0RzpGZfEwf",
            "size": 0
        }, {
            "id": "MyDemoService",
            "version": "1.0.0-2",
            "token": "0ZyOt5tYKB",
            "size": 0
        }, {
            "id": "OpenCVTest",
            "version": "2.6.1-1",
            "token": "z812kDV0Xf",
            "size": 0
        }]
    },
    "profile": {
        "serialNumber": "20004007594",
        "displayName": "Foo Bar",
        "roles": ["Admin", "Tester],
            "contactId": 20004007594,
            "attr_1": "000000000031",
            "attr_2": "LOCATION 023",
            "attr_3": 123
        }
    }
```

## Error
Server sends a response of "*HTTP Status: 403 / Forbidden*" if the credential is invalid.

```javascript
{ "message": "some error msg here", "code": "3-2" }
```
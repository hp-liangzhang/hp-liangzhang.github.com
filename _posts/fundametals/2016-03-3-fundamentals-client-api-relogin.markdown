---
layout: post
title:  "Relogin"
date:   2016-02-3 00:41:56 +0800
categories: ClientApi
---

# Relogin
Do login with the secure code. This API requires the session which user has been logged in.

## URL
/client/relogin


## METHOD
POST

## Request Parameters

| Param   | Required | Type |  Optional Values |  Descscription |
|---------|:--------:|:----:|------------------|:---------------|
|  |  |  |  |  |
| sessionId | true | String | | the session id is accquired from Hello API |
| secureCode | true | String |  | comes from the response of Login API |



## Request Example

```shell
curl 'http://eosserver/client/relogin' --data 'sessionId=9a0b6679-c460-41a3-b26c-26e0d69538c6&secureCode=foobarcode'
```

## Response Example
It is as same as response of Login API

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
{ "message": "Invalid credential", "code": "3-2" }
```
---
layout: post
title:  "Client Property"
date:   2016-02-3 00:41:54 +0800
categories: ClientApi
---

# Client Property
Retrieve preperties from server side. This API requires a valid session but  login is not required.

## URL
/client/properties

## METHOD
GET

## Request Parameters

| Param   | Required | Type |  Optional Values |  Descscription |
|---------|:--------:|:----:|------------------|:---------------|
|  |  |  |  |  |
| sessionId | true | String | | the session id is accquired from Hello API |

## Request Example

```shell
curl 'http://eosserver/client/properties'
```

## Response Example
A Json Array.

```javascript
{
    "propA": "valueA",
    "propB": 123
}
```

## Error
Server sends a response of "*HTTP Status: 403 / Forbidden*" if the session is invalid.

```javascript
{ "message": "Invalid sessionId", "code": "2-2" }
```
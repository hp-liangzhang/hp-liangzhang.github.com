---
layout: post
title:  "Logout"
date:   2016-02-3 00:41:54 +0800
categories: ClientApi
---

# Logout
Logout from current session.

## URL
/client/logout

## METHOD
POST

## Request Parameters

| Param   | Required | Type |  Optional Values |  Descscription |
|---------|:--------:|:----:|------------------|:---------------|
|  |  |  |  |  |
| sessionId | true | String | | the session id is accquired from Hello API |



## Request Example

```shell
curl 'http://eosserver/client/logout' --data 'sessionId=9a0b6679-c460-41a3-b26c-26e0d69538c6&secoreCode=foobarcode'
```

## Response Example
A blank Json Array.

```javascript
{}
```

## Error
Server sends a response of "*HHTTP Status: 400 / Bad Request*" if the session is invalid or has logged out.

```javascript

```
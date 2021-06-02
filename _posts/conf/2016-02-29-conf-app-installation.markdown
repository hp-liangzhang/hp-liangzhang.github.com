---
layout: post
title:  "Http Client"
date:   2016-03-3 00:41:34 +0800
categories: Configuration
---
Modify conf/custom.conf:

```shell
# user agent
httpClient.userAgent=EOS 1.0
# connection timeout (in second)
httpClient.connectionTimeout=10
# request timeout (in second)
httpClient.requestTimeout=10
# read timeout (in second)
httpClient.readTimeout=10
# indicate if enable verbose log. options: enable, disable 
httpClient.verbose=disable
# indicate if enable proxy. options: enable, disable
httpClient.proxy=disable
# the host of proxy
httpClient.proxy.host=
# the port of proxy
httpClient.proxy.port=
```




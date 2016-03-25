---
layout: post
title:  "Client Api"
date:   2016-03-1 00:41:34 +0800
categories: Configuration
---
Modify conf/custom.conf:

```shell
# set enable to output all information of mobility apps in the response of /client/hello 
clientapi.output_all_apps=(enable|disable)
# set enable to output sizes of mobility apps in the response of /client/(hello|login|relogin)
clientapi.set_skin_size=(enable|disable)
```




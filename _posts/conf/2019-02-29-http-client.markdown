---
layout: post
title:  "App installation"
date:   2016-03-3 00:41:34 +0800
categories: Configuration
---
Modify conf/custom.conf:

```shell
# set enable to encrypt lua files as new files when installing
# the encrypted file will be renamed form foo.lua to foo.hyd
mba.encrypt_lua=(enable|disable)
# set enable to keep foo.lua, else foo.lua will be removed
# this option works only when mba.encrypt_lua=enable
mba.keep_plain_lua=(enable|disable)
```




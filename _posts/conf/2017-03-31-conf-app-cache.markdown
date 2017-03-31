---
layout: post
title:  "Cache"
date:   2017-03-31 00:41:34 +0800
categories: Configuration
---

# Caches

By default EOS server will use a standalone cache that stores data in the JVM heap. When it is in a distributed environment, it is recommanded that uses Memcached or Redis as its cache system.

To use memcached:

```
# memcached
memcached=enabled
memcached.host=127.0.0.1:11211
```

Or to use redis:

```
# redis
#redis.cache=enabled
#redis.cache.url=redis://:@localhost:6379
#redis.cache.index=0

If you don’t configure Memcached, Play will use a standalone cache that stores data in the JVM heap
```




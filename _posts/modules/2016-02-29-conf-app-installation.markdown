---
layout: post
title:  "Hydra modules"
date:   2016-05-6 16:56:34 +0800
categories: Module
---

## What is a Hydra module?
A Hydra module is just a [module of Play Framework 1.x](https://www.playframework.com/documentation/1.3.1/modules). 

## How to use it?

As the official repository of modules for Play Framework 1.x is read only at present, those modules are kept in out source codes repository.

It means that it cannot be installed by running the command 'play deps'.

To use an EOS module, please follow those instructions:

1. edit conf/dependencies.yml and add a dependency (let add the status module here)

```
# Application dependencies

require:
    - play
    - play -> guice 1.2
    - play -> status 0.1

```

2. copy the module into modules/

3. start the hydra server

If you see those logs at the beggining:

```
22:11:47,634 INFO  ~ Module status is available (/hydra-server/m
odules/status-0.1)
```

All done.



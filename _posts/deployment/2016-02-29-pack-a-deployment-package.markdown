---
layout: post
title:  "Pack a deployment package"
date:   2016-02-29 14:26:34 +0800
categories: Deployment
---
## Objectives
* To pack a deployment package from the repository.

## Prerequisites
* JDK 7.0 +
* Apache Ant

## Action

Enter the root directory of the repository of Hydra server, then use 'ant' to pack a package.

```shell
ant pkg.deploy
```

Then you get a ziped package that is named 'eos.zip' under the root directory of the repository.





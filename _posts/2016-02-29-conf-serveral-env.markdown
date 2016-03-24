---
layout: post
title:  "Framework ID"
date:   2016-03-1 00:00:34 +0800
categories: Deployment
---

When you work in a team, different developers will use different configuration keys in their application.conf. For example, the log level or some database configuration. This generally leads to recurrent conflicts when you commit the file using your VCS.

Furthermore, different deployment environments – e.g. dev, test, staging and production – need different configurations.

# The Framework ID
To resolve this problem, Play allows you to give an ID to each framework installation. Use the play tool’s id command to define this ID:

```shell
play id
```


# Properties with specific Framework ID

You canprefix your configuration keys with the framework ID for which the configuration option is intended:

```shell
# Test configuration
%test.db=mem
%test.jpa.ddl=create-drop

# Dev configuration
%dev.http.port=8080
%dev.application.log=DEBUG
%dev.application.mode=dev

# Production configuration
%prod.http.port=80
%prod.application.log=INFO
%prod.application.mode=prod
```


# Setting the framework ID from the command line 
You can specify the framework ID to use for a particular command directly from the command line. For example to run an application in production mode you can use:

```shell
play run --%production
```
with these lines defined in the application.conf file:

```shell
application.mode=dev
%production.application.mode=prod
```

# More Reference
See the Play Documentations.

[Manage application.conf in several environments](https://www.playframework.com/documentation/1.4.x/ids)

[Put your application in production](https://www.playframework.com/documentation/1.4.x/production)


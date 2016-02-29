---
layout: post
title:  "Deploy on Mac / Linux"
date:   2016-02-29 14:26:34 +0800
categories: deployment
---
# Objectives
* Deploy a EOS server package on Linux / Mac.

# Prerequisites
* Linux / Mac / Windows
* JDK 7.0
* Playframework 1.3.x

# Action

## Initialization

Let's assume that the deployment package is located at /var/www.

```shell
cd /var/www

# extract the deployment package
unzip eos.zip

cd eos

# init
chmod 755 eos-*
./eos-init
```

## Configaration

By default the EOS server uses:

* a file based H2 database which located in data/db
* a local file system to store mobility app files

Now you should modify the configuration file 'conf/custom.conf' to fit your needs.

## Running

Edit the script 'eos-server', to modify the three properties:

```shell
# path to the executable file of Play Framework
PLAY=/opt/play/current/play

# path to the directory of eos
RUNDIR=/var/www/eos

# path to the pid file 
PIDFILE=/var/www/eos/deploy/server/server.pid
```

To run or stop the server:

```shell
# using the script file 'eos-server'
# start
./eos-server start
# stop
./eos-server stop

# using the play command directly
# start
play start deploy/server
# stop
play start deploy/server
```




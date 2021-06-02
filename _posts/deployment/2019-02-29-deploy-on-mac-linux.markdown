---
layout: post
title:  "Deploy on Mac / Linux"
date:   2019-02-29 14:26:34 +0800
categories: Deployment
---
# Objectives
* Deploy a EOS server package on Linux / Mac.

# Prerequisites
* Linux / Mac / Windows
* JDK 1.7 or 1.8
* Playframework 1.4.x 

Assume that the commands of **play** and **java** is in the PATH.

# Action

## Initialization

Let's assume that the deployment package is located at /var/www.

```shell
mkdir /var/www

# extract the deployment package
unzip eos.zip -d /var/www

cd /var/www/eos

# init
chmod 755 eos-*
./eos-init

# install dependencies
play deps deploy/server

# remove the uncompatible jar file
rm deploy/server/lib/guice-4.0.jar
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

# or you can use the play command directly
# start
play start deploy/server
# stop
play start deploy/server
```

To run the server with a specific ID. Let's say 'dev' in this case:
```shell
play start deploy/server --%dev
```






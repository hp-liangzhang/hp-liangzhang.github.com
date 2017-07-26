---
layout: post
title:  "Database"
date:   2016-03-1 00:41:34 +0800
categories: Configuration
---
Modify conf/custom.conf.
Generally saying, a typical configurations for a database looks like:

```shell
db.url=jdbc:mysql://localhost/test
db.driver=com.mysql.jdbc.Driver
db.user=root
db.pass=
```

## H2 database in memory

```shell
db=mem
```

## H2 database in local file

```shell
db.url=jdbc:h2:file:./data/db;MVCC=true;LOCK_TIMEOUT=100;LOCK_MODE=0
db.driver=org.h2.Driver
```

## PostgreSQL

```shell
db.url=jdbc:postgresql:database_name
db.driver=org.postgresql.Driver
db.user=root
db.pass=secret
```


## Mysql

```shell
db.url=jdbc:mysql://localhost/test
db.driver=com.mysql.jdbc.Driver
db.user=root
db.pass=
```

## SqlServer

```shell
db.url=jdbc:sqlserver://0.0.0.0;databaseName=foo
db.driver=com.microsoft.sqlserver.jdbc.SQLServerDriver
jpa.dialect=utils.SQLServer2008Dialect
db.user=root
db.pass=
```



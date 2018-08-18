# Simple Use

## Introduction
MongoDB is an open-source document database that provides high performance, high availability, and automatic scaling.

### Document Database
A record in MongoDB is a document, which is a data structure composed of field and value pairs. MongoDB documents are similar to JSON objects. The values of fields may include other documents, arrays, and arrays of documents.

### Key Features
#### High Performance

#### Rich Query Language

#### High Availability

#### Horizontal Scalability

#### Support for Multiple Storage Engines

## Install mongodb
os: mac os
```
┌─[baidu@baidudeMacBook-Pro-97] - [~] - [Sat Aug 18, 17:35]
└─[$] <> brew search mongodb
==> Searching local taps...
homebrew/php/php54-mongodb              homebrew/php/php70-mongodb              mongodb                                 mongodb@3.2
homebrew/php/php55-mongodb              homebrew/php/php71-mongodb              mongodb@2.6                             percona-server-mongodb
homebrew/php/php56-mongodb              homebrew/php/php72-mongodb              mongodb@3.0
==> Searching taps on GitHub...
homebrew/cask-versions/mongodb-compass-beta          homebrew/cask/mongodb-compass                        homebrew/cask/mongodb-compass-readonly
homebrew/cask/mongodb                                homebrew/cask/mongodb-compass-community              homebrew/cask/orelord-mongodb
==> Searching blacklisted, migrated and deleted formulae...

brew install mongodb@3.2
Updating Homebrew...
^C==> Installing dependencies for mongodb@3.2: openssl
==> Installing mongodb@3.2 dependency: openssl
==> Downloading https://homebrew.bintray.com/bottles/openssl-1.0.2m.high_sierra.bottle.tar.gz
##################################################                        69.6%
######################################################################## 100.0%
==> Pouring openssl-1.0.2m.high_sierra.bottle.tar.gz
==> Caveats
A CA file has been bootstrapped using certificates from the SystemRoots
keychain. To add additional certificates (e.g. the certificates added in
the System keychain), place .pem files in
  /usr/local/etc/openssl/certs

and run
  /usr/local/opt/openssl/bin/c_rehash

This formula is keg-only, which means it was not symlinked into /usr/local,
because Apple has deprecated use of OpenSSL in favor of its own TLS and crypto libraries.

If you need to have this software first in your PATH run:
  echo 'export PATH="/usr/local/opt/openssl/bin:$PATH"' >> ~/.zshrc

For compilers to find this software you may need to set:
    LDFLAGS:  -L/usr/local/opt/openssl/lib
    CPPFLAGS: -I/usr/local/opt/openssl/include
For pkg-config to find this software you may need to set:
    PKG_CONFIG_PATH: /usr/local/opt/openssl/lib/pkgconfig

==> Summary
🍺  /usr/local/Cellar/openssl/1.0.2m: 1,792 files, 12.3MB
==> Installing mongodb@3.2
==> Downloading https://homebrew.bintray.com/bottles/mongodb@3.2-3.2.11.high_sierra.bottle.1.tar.gz
###################################################                       72.2%
####################################################                      73.4%
#####################################################################     96.0%
######################################################################## 100.0%
==> Pouring mongodb@3.2-3.2.11.high_sierra.bottle.1.tar.gz
==> Caveats
This formula is keg-only, which means it was not symlinked into /usr/local,
because this is an alternate version of another formula.

If you need to have this software first in your PATH run:
  echo 'export PATH="/usr/local/opt/mongodb@3.2/bin:$PATH"' >> ~/.zshrc


To have launchd start mongodb@3.2 now and restart at login:
  brew services start mongodb@3.2
Or, if you don't want/need a background service you can just run:
  mongod --config /usr/local/etc/mongod.conf
==> Summary
🍺  /usr/local/Cellar/mongodb@3.2/3.2.11: 19 files, 255.5MB
```

## Basic Use
### start mongodb service
default port 27017
```
┌─[baidu@baidudeMacBook-Pro-97] - [~] - [Sat Aug 18, 18:10]
└─[$] <> brew services start mongodb@3.2
==> Tapping homebrew/services
Cloning into '/usr/local/Homebrew/Library/Taps/homebrew/homebrew-services'...
remote: Counting objects: 14, done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 14 (delta 0), reused 7 (delta 0), pack-reused 0
Unpacking objects: 100% (14/14), done.
Tapped 1 command (43 files, 55.2KB).
==> Successfully started `mongodb@3.2` (label: homebrew.mxcl.mongodb@3.2)
```

```
┌─[baidu@baidudeMacBook-Pro-97] - [/usr/local/var/mongodb] - [Sat Aug 18, 19:31]
└─[$] <> mongod -repair
2018-08-18T19:32:54.633+0800 I CONTROL  [initandlisten] MongoDB starting : pid=33712 port=27017 dbpath=/data/db 64-bit host=baidudeMacBook-Pro-97.local
2018-08-18T19:32:54.633+0800 I CONTROL  [initandlisten] db version v3.6.6
2018-08-18T19:32:54.633+0800 I CONTROL  [initandlisten] git version: 6405d65b1d6432e138b44c13085d0c2fe235d6bd
2018-08-18T19:32:54.633+0800 I CONTROL  [initandlisten] OpenSSL version: OpenSSL 1.0.2p  14 Aug 2018
2018-08-18T19:32:54.633+0800 I CONTROL  [initandlisten] allocator: system
2018-08-18T19:32:54.633+0800 I CONTROL  [initandlisten] modules: none
2018-08-18T19:32:54.633+0800 I CONTROL  [initandlisten] build environment:
2018-08-18T19:32:54.633+0800 I CONTROL  [initandlisten]     distarch: x86_64
2018-08-18T19:32:54.633+0800 I CONTROL  [initandlisten]     target_arch: x86_64
2018-08-18T19:32:54.633+0800 I CONTROL  [initandlisten] options: { repair: true }
2018-08-18T19:32:54.635+0800 I STORAGE  [initandlisten] exception in initAndListen: NonExistentPath: Data directory /data/db not found., terminating
2018-08-18T19:32:54.635+0800 I CONTROL  [initandlisten] now exiting
2018-08-18T19:32:54.635+0800 I CONTROL  [initandlisten] shutting down with code:100
```

### login
mongo 127.0.0.1:27017
or 
mongo
```
┌─[baidu@baidudeMacBook-Pro-97] - [~] - [Sat Aug 18, 18:14]
└─[$] <> mongo
MongoDB shell version: 3.2.11
connecting to: test
Welcome to the MongoDB shell.
For interactive help, type "help".
For more comprehensive documentation, see
	http://docs.mongodb.org/
Questions? Try the support group
	http://groups.google.com/group/mongodb-user
>
```

### Questions
1. Start error
```
┌─[baidu@baidudeMacBook-Pro-97] - [~] - [Sat Aug 18, 19:22]
└─[$] <> mongo
MongoDB shell version v3.6.6
connecting to: mongodb://127.0.0.1:27017
2018-08-18T19:22:06.335+0800 W NETWORK  [thread1] Failed to connect to 127.0.0.1:27017, in(checking socket for error after poll), reason: Connection refused
2018-08-18T19:22:06.335+0800 E QUERY    [thread1] Error: couldn't connect to server 127.0.0.1:27017, connection attempt failed :
connect@src/mongo/shell/mongo.js:251:13
@(connect):1:6
exception: connect failed
```
How to fix it up:
```
rm -rf /usr/local/var/mongodb/*
```

2. Start warning
```
┌─[baidu@baidudeMacBook-Pro-97] - [/usr/local/var] - [Sat Aug 18, 19:56]
└─[$] <> mongo
MongoDB shell version v4.0.1
connecting to: mongodb://127.0.0.1:27017
MongoDB server version: 4.0.1
Server has startup warnings:
2018-08-18T19:56:58.150+0800 I CONTROL  [initandlisten]
2018-08-18T19:56:58.150+0800 I CONTROL  [initandlisten] ** WARNING: Access control is not enabled for the database.
2018-08-18T19:56:58.150+0800 I CONTROL  [initandlisten] **          Read and write access to data and configuration is unrestricted.
2018-08-18T19:56:58.150+0800 I CONTROL  [initandlisten]
---
Enable MongoDB's free cloud-based monitoring service, which will then receive and display
metrics about your deployment (disk utilization, CPU, operation statistics, etc).

The monitoring data will be available on a MongoDB website with a unique URL accessible to you
and anyone you share the URL with. MongoDB may use this information to make product
improvements and to suggest MongoDB products and deployment options to you.

To enable free monitoring, run the following command: db.enableFreeMonitoring()
To permanently disable this reminder, run the following command: db.disableFreeMonitoring()
---

>
```

1) add user
```
use admin
db.createUser(
  {
    user: "u_admin",
    pwd: "123456",
    roles: [ { role: "userAdminAnyDatabase", db: "admin" } ]
  }
)

db.createUser(
  {
    user: "root", 
    pwd: "123456",
    roles:["root"]
  }
)

db.createUser(
  {
    user: "tester",
    pwd: "123456",
    roles: [ { role: "readWrite", db: "test" },
             { role: "read", db: "reporting" } ]
  }
)

```

list the users:
```
use admin
db.system.users.find()
```

2) modify mongo.conf and restart service
Add two lines in /usr/local/etc/mongod.conf, as follows:
```
security:
  authorization: enabled
```

And then restart mongodb service, like this:
```
brew services restart mongodb
```

3) login in 
```
mongo -port 27017 -username admin -password 123456  --authenticationDatabase=admin
```
or
```
mongo --port 27017 -u "admin" -p "123456" --authenticationDatabase "admin"
```
or
```
mongo

db.auth("admin", "123456")
```


### Simple Use
#### Database
In MongoDB, databases hold collections of documents.

#### Collections
MongoDB stores documents in collections. Collections are analogous to tables in relational databases.




## Reference
1. [MongoDB Doc](https://docs.mongodb.com/)
2. [Learn MongoDB](https://university.mongodb.com/)

# Simple Use

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

### Simple Use



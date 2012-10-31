---
layout: post
title: "Authentication: authom, passports, everyauth"
description: "Face40 #1"
category: "Face40"
tags: ["node", "authentication"]
comments : false
---
{% include JB/setup %}

# Authom

## References
* [jed/authom](https://github.com/jed/authom)

## Practice
<pre>
express -s -c stylus authentication-ex1
cd authentication-ex1/
npm install authom
# npm start authom
cd node_modules/authom/
sudo /home/song10/opt/bin/node ./example/server.js /home/song10/my/js/authom-ex1/node_modules/authom spawning
# browse http://authom.jedschmidt.com
</pre>

## Comments
* simple, neat code!
* no account / password support
* it doesn't handle logins, persistence, sessions, or anything past authentication, it is more of a tool and less of a framework.

# Passports

## References
* [jaredhanson/passport](https://github.com/jaredhanson/passport)

## Practice
<pre>
# password only
git clone https://github.com/jaredhanson/passport-local.git
cd passport-local/examples/express3/
npm install
node app.js
# browse http://localhost:3000
</pre>

<pre>
# passport-twitter
git clone https://github.com/jaredhanson/passport-twitter.git
cd passport-twitter/examples/signin/
npm install
node app.js
# browse http://localhost:3000
</pre>

### Notes
* need to app.use(app.router) after Passport.
* ensure local.host in /etc/hosts
 > cat /etc/hosts
 127.0.0.1 localhost local.host

## Comments
* simple, acceptable code complexity.
* modular plugins in separated packages

# Everyauth
## References
* [bnoguchi/everyauth](https://github.com/bnoguchi/everyauth/)

## Practice
<pre>
# to build webkit_server@0.1.0
sudo apt-get install qt4-qmake libqt4-dev
# webkit_server@0.1.0 does NOT like dash, switch to bash
sudo dpkg-reconfigure dash
git clone https://github.com/bnoguchi/everyauth.git
cd everyauth/example
npm install
node server.js
# browse http://local.host:3000
</pre>

## Comments
* dependancy is heavy (webkit-server/qt)
* not friendly with express3
* simple, acceptable code complexity.

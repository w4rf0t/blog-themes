---
layout: wiki
title: Python
cate1: Programming Language
cate2:
description: Python common modules and resource records.
keywords: Python
---

## module

### requests

Elegant and simple HTTP module.

### BeautifulSoup

Very useful HTML/XML parser.

### json

JSON codec.

Application examples:

* Format JSON file

  ````sh
  python -m json.tool src.json > dst.json
  ````

  Format JSON in Vim:

  ````sh
  :%!python -m json.tool
  ````

### CGIHTTPServer

Simple and practical HTTP server.

Application examples:

* Run a simple HTTP server

  ````sh
  python -m CGIHTTPServer 80
  ````

### base64

A module for convenient base64 encoding and decoding.

Application examples:

* decode base64

  ````sh
  echo aGVsbG93b3JsZA== | python -m base64 -d
  ````

  you can see the output

  ````sh
  helloworld
  ````

## problem solved

### Your PYTHONPATH points to a site-packages dir

Error message:

``
~/github/hs-airdrop $ npm install
``
> bcrypto@5.0.3 install /Users/username/github/hs-airdrop/node_modules/bcrypto
> node-gyp rebuild

Your PYTHONPATH points to a site-packages dir for Python 3.x but you are running Python 2.x!
     PYTHONPATH is currently: "/usr/local/lib/node_modules/npm/node_modules/node-gyp/gyp/pylib"
     You should `unset PYTHONPATH` to fix this.
gyp ERR! configure error
gyp ERR! stack Error: `gyp` failed with exit code: 1
gyp ERR! stack at ChildProcess.onCpExit (/usr/local/lib/node_modules/npm/node_modules/node-gyp/lib/configure.js:351:16)
gyp ERR! stack at ChildProcess.emit (events.js:210:5)
gyp ERR! stack at Process.ChildProcess._handle.onexit (internal/child_process.js:272:12)
gyp ERR! System Darwin 19.3.0
gyp ERR! command "/usr/local/Cellar/node/12.12.0/bin/node" "/usr/local/lib/node_modules/npm/node_modules/node-gyp/bin/node-gyp.js" "rebuild "
gyp ERR! cwd /Users/username/github/hs-airdrop/node_modules/bcrypto
gyp ERR! node -v v12.12.0
gyp ERR! node-gyp -v v5.0.5
gyp ERR! not ok
npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! bcrypto@5.0.3 install: `node-gyp rebuild`
npm ERR! Exit status 1
npm ERR!
npm ERR! Failed at the bcrypto@5.0.3 install script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.

npm ERR! A complete log of this run can be found in:
npm ERR! /Users/username/.npm/_logs/2020-02-19T14_14_34_524Z-debug.log
````

Solution:

Delete sitecustomize.pyc in the /usr/local/lib/python3.7/site-packages/ folder, rename the sitecustomize.py file to sitecustomize.py~, and change it back after the installation is successful.
Simple application which brings all features together

Online version
==============

* http://ember-couchdb-kit.roundscope.pw


Installation
============

change to parent directory, run "npm install" (chose ember#~1.0.0 bower component version if prompted) and run "grunt build"

```
cd ..
npm install
grunt build
```

change back to "example" directory and run "npm install"

```
cd example
npm install
```



setup application related design docs

```
curl -X PUT http://localhost:5984/boards
```

```
curl -X PUT http://localhost:5984/boards/_design/issues -H 'Content-Type: application/json' -d '
{
   "_id": "_design/issues",
   "language": "javascript",
   "filters": {
     "only_positions": "function(doc, req) { if(doc.type == \"position\") { return true; } }",
     "issue": "function(doc, req) {if(doc.type == \"issue\") { return true; } }"
   }
}'
```

Run
===

```
grunt server
open -a safari http://127.0.0.1:9001/index.html
```
==============

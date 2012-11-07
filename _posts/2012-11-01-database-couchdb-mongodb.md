---
layout: post
title: "Database: CouchDB, MongoDB"
description: "Face40 #2"
category: "Face40"
tags: ["node", "database"]
---
{% include JB/setup %}

# CouchDB

## References
* [Getting Started with CouchDB](http://net.tutsplus.com/tutorials/getting-started-with-couchdb/)
* [dscape/nano](https://github.com/dscape/nano)
* [cloudhead/cradle](https://github.com/cloudhead/cradle)

## CouchDB ABC
<pre>
cat person.json
{
  "forename": "Steven",
  "surname" : "Cooper",
  "type"    : "person"
}

# create doc
curl -X POST http://127.0.0.1:5984/mycouchshop/ -d @person.json -H "Content-Type: application/json"
# POST – creates a new record
# GET – reads records
# PUT – updates a record
# DELETE – deletes a record

# view all doc
curl -X GET http://127.0.0.1:5984/mycouchshop/_all_docs

# Simple Map Function
Futon: View: "Temporary View"
function (doc) {
  if (doc.type === "product" &amp;&amp; doc.name) {
    emit(doc.name, doc);
  }
}
Futon: Save as, product, products

# view products
curl -X GET http://127.0.0.1:5984/mycouchshop/_design/products/_view/products

# Performing a Reduce
## map
function (doc) {
  if (doc.type === "product" &amp;&amp; doc.price) {
    emit(doc.id, doc.price);
  }
}
## reduce
function (keys, prices) {
  return sum(prices);
}
</pre>

## Practices
<pre>
# nano exercise
node > ...
</pre>

<pre>
# cradle exercise
node > ...
</pre>

## Commonts
* nano has more intuitive API, and better documentation than cradle

# MongoDB

## References
* [Getting Started with MongoDB – Part 1](http://net.tutsplus.com/tutorials/databases/getting-started-with-mongodb/)
* [Getting Started with MongoDB – Part 2](http://net.tutsplus.com/tutorials/databases/getting-started-with-mongodb-part-2/)
* [LearnBoost/mongoose](https://github.com/learnboost/mongoose)
* [christkv/node-mongodb-native](https://github.com/christkv/node-mongodb-native)
* [kissjs/node-mongoskin](https://github.com/kissjs/node-mongoskin)

## Practices
<pre>
# mongoose exercise
node > ...
</pre>

<pre>
# node-mongodb-native exercise
node > ...
</pre>

<pre>
# node-mongoskin exercise
node > ...
</pre>

## Commonts
* similar user model with CouchDB, might have performance difference.
* No GUI tool as CouchDB's futon.

# Conclusion
Pick CouchDB with Nano module as my choices.

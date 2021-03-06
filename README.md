express-crud
======================
[![Build Status](https://travis-ci.org/jsdevel/node-express-crud.png)](https://travis-ci.org/jsdevel/node-express-crud)

Easily route a resource's crud methods to express apps!

##Example
Here's a User resource that exposes some CRUD methods:

````javascript
module.exports = {
  create:function(model, cb){},
  delete:function(id, cb){},
  read:function([id,] query, cb){},
  update:function(id, model, cb){}
};
````

Here's how you add the routes to your express app:
````javascript
var app = require('express')();
var User = require('./models/User');

require('express-crud');

app.crud('users', User);
````

Now your express app has the following routes:
````
DELETE /users/:id
GET /users
GET /users/:id
POST /users
PUT /users/:id
````

Node.js interface to Totango
============================
This project is based on [https://www.npmjs.com/package/totango](https://www.npmjs.com/package/totango).
As it seems abandoned and we need to continue bumping its dependencies. So all credit to its authors.

[Totango](http://www.totango.com) is a SaaS analytics solution for tracking your users, improve conversion
and rention.

This is a node.js module wrapping Totango's [REST API](http://help.totango.com/installing-totango/quick-start-http-api-server-side-integration/)

# Installation
```
npm install totango
```
Or better, add it to your project's ```package.json```

# Usage

```js
var totango = require('totango');
var t = new totango('YOUR_TOTANGO_SERVICE_KEY');

// A user in Totango is identified by a unique user id, an account id,
// and an account name (used by totango to display the account nicely)
var user = t.user('userId', 'accountId', 'Account Name');

// Record an event on a user
user.event('Login', 'Checkout', function(err) {
    if (err) { console.log(err.message());}
    // event registered successfully
});

// Set attributes on a customer account
user.setAccountAttributes({
    "Status": "Free"
    }, function(err) {
    if (err) { console.log(err.message());}
    // attribute registered successfully
});

// Set some attributes on a user
user.setAttributes({
    "Attr1": "value1",
    "Attr2": "value2"}, function(err) {
    if (err) { console.log(err.message());}
    // attribute registered successfully
});
```

# Credits
This npm module is implemented by Olivier Crameri and provided for free by [BugBuster](http://bugbuster.com)

# License

```
Copyright (C) 2013, BugBuster SA, Switzerland
Authors(s): Olivier Crameri

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

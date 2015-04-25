throt-fb
============================================================================

Throttling API client for Facebook Graph API.

## Install

```bash
$ npm install throt-fb
```

## Run test

Assign api.token with a correct value in ```test/api.js``` . Start looking in this link for access token 'https://developers.facebook.com/tools-and-support/' ---> Graph API Explorer

Make sure that latest version of nodejs and nvm are installed. (Remove legacy versions)

```bash
$ npm test
```

## Usage

```javascript
var api = require('throt-fb');

// Set endpoint and token
api.endpoint = 'https://graph.facebook.com';
api.token = 'Your token';
```


### Methods

api.

- get(url)
- post(url, parameters)
- delete(url)
- put(url, parameters)

All of them returns data that consits from 2 parts: 

- json /payload/
- response 

#### Example

```javascript
api.get('/me').then(function (data) {
  console.dir(data.json);
}).catch(function(e){
  console.dir(e)
}).finally(function(){
  console.dir('Done with the request')
});

api.post('/me/feed', { message: 'Welcome to Smartly.io!' }).then(function (data) {
  console.dir(data.json);
}).catch(function(e){
  console.dir(e)
}).finally(function(){
  console.dir('Done with the request')
});
```

To find URLs and params, go to [Graph API Reference](https://developers.facebook.com/docs/graph-api/reference/v2.1)

#License
The MIT License (MIT)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
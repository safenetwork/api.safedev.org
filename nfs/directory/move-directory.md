# Move directory

Move or copy a directory.

Only authorized requests can invoke this endpoint.

### Request

```
POST /nfs/movedir
```

#### URL

```
http://localhost:8100/nfs/movedir
```

#### Header

| Field | Description |
| --- | --- |
| Authorization | The [authorization token](/auth) obtained from SAFE Launcher. |
| Content-Type | The [media type](https://www.iana.org/assignments/media-types/media-types.xhtml) of the request body (`application/json`). |

##### Example

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
Content-Type: application/json
```

#### Body

| Property | Description |
| --- | --- |
| srcRootPath | Which root directory to use (`app` or `drive`). |
| srcPath | The full path of the source directory. |
| destRootPath | Which root directory to use (`app` or `drive`). |
| destPath | The full path of the destination directory. |
| action | Whether to `move` or `copy` the directory. Defaults to `move` if not specified. |

##### Example

```json
{
	"srcRootPath": "app",
	"srcPath": "/images",
	"destRootPath": "drive",
	"destPath": "/websites/www-example",
	"action": "move"
}
```

### Response

On success, the HTTP status code in the response header is `200` (OK).

### Example

```js
var request = require('request');
var endpoint = 'http://localhost:8100/nfs/movedir';

var payload = {
  srcRootPath: 'app',
  srcPath: '/images',
  destRootPath: 'drive',
  destPath: '/websites/www-example',
  action: 'move' // or copy
};

var onResponse = function(err, response, body) {
  if (err) {
    return console.error(err.message);
  }
  if (response.statusCode === 200) {
    return console.log('Directory moved successfully');
  }
  console.error('Operation failed', body);
};

request.post(endpoint, {
  auth: {
    bearer: constants.token // pass the auth token
  },
  json: true,
  body: payload
}, onResponse);
```

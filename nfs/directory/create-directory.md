# Create directory

Create a public or private directory either in the app's root directory or in the SAFE Drive of the user.

Only authorized requests can invoke this endpoint.

### Request

```
POST /nfs/directory/:rootPath/:directoryPath
```

#### URL

| Parameter | Description |
| --- | --- |
| rootPath | Which root directory to use (`app` or `drive`). |
| directoryPath | The full path of the directory. |

##### Example

```
http://localhost:8100/nfs/directory/drive/websites/www-example
```

#### Header

| Field | Description |
| --- | --- |
| Authorization | The [authorization token](/auth) obtained from SAFE Launcher. |
| Content-Type | The [media type](https://www.iana.org/assignments/media-types/media-types.xhtml) of the request body (`application/json`).<br>Only include this field if the request body is present. |

##### Example

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
Content-Type: application/json
```

#### Body

The request body is optional.

| Property | Description |
| --- | --- |
| isPrivate | Whether the directory should be private or public (`true` or `false`).<br>This is an optional field. If not specified, it defaults to `false`. |
| metadata | Metadata to be associated with the directory. It should be encoded as a base64 string.<br>This is an optional field. If not specified, it defaults to an empty string. |

##### Example

```json
{
	"isPrivate": true,
	"metadata": "c2FtcGxlIG1ldGFkYXRh"
}
```

### Response

On success, the HTTP status code in the response header is `200` (OK).

### Example

```js
var request = require('request');

var endpoint = 'http://localhost:8100/nfs/directory/drive/websites/www-example';
var payload = {
  isPrivate: true,
  metadata: new Buffer('sample metadata').toString('base64')
};

var onResponse = function(err, response, body) {
  if (err) {
    return console.error(err.message);
  }
  if (response.statusCode === 401) {
    return console.error('Failed to authorize');
  }
  if (response.statusCode === 200) {
    return console.log('Directory created');
  }
  console.error('Failed to create directory.', body);
};

request.post(endpoint, {
  auth: {
    bearer: constants.token // pass the auth token
  },
  json: true,
  body: payload
}, onResponse);
```

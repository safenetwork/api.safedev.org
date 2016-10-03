# Update directory

Rename a directory and update its metadata.

Only authorized requests can invoke this endpoint.

### Request

```
PUT /nfs/directory/:rootPath/:directoryPath
```

#### URL

| Parameter | Description |
| --- | --- |
| rootPath | Which root directory to use (`app` or `drive`). |
| directoryPath | The full path of the directory. |

##### Example

```
http://localhost:8100/nfs/directory/app/images
```

#### Header

| Field | Description |
| --- | --- |
| Authorization | The [authorization token](/auth) obtained from SAFE Launcher. |
| Content-Type | The [media type](https://www.iana.org/assignments/media-types/media-types.xhtml) of the request body (`application/json`). |

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
Content-Type: application/json
```

#### Body

| Property | Description |
| --- | --- |
| name | The new name of the directory. |
| metadata | Metadata to be associated with the directory. It should be encoded as a base64 string.<br>Defaults to an empty string if not specified. |

##### Example

```json
{
	"name": "pictures",
	"metadata": "c2FtcGxlIG1ldGFkYXRhIHVwZGF0ZWQ="
}
```

### Response

On success, the HTTP status code in the response header is `200` (OK).

### Example

```js
var request = require('request');

var endpoint = 'http://localhost:8100/nfs/directory/app/images';
var payload = {
  name: 'pictures',
  metadata: new Buffer('sample metadata updated').toString('base64')
};

var onResponse = function(err, response, body) {
  if (err) {
    return console.error(err.message);
  }
  if (response.statusCode === 401) {
    return console.error('Failed to authorize');
  }
  if (response.statusCode === 200) {
    return console.log('Directory Updated');
  }
  console.error('Failed to update directory.', body);
};

request.put(endpoint, {
  auth: {
    bearer: constants.token
  },
  json: true,
  body: payload
}, onResponse);
```

# Update file metadata

Rename a file and update its metadata.

Only authorized requests can invoke this endpoint.

### Request

```
PUT /nfs/file/metadata/:rootPath/:filePath
```

#### URL

| Parameter | Description |
| --- | --- |
| rootPath | Which root directory to use (`app` or `drive`). |
| filePath | The full path of the file. |

##### Example

```
http://localhost:8100/nfs/file/metadata/app/images/sample.png
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
| name | The new name of the file. |
| metadata | Metadata to be associated with the file.<br>Defaults to an empty string if not specified. |

```json
{
	"name": "Sample.png",
	"metadata": "RmlsZSBtZXRhZGF0YQ=="
}
```

### Response

On success, the HTTP status code in the response header is `200` (OK).

### Example

```js
var request = require('request');
var fs = require('fs');
var endpoint = 'http://localhost:8100/nfs/file/metadata/app/home/sample.png';

var onResponse = function(err, response, body) {
  if (err) {
    return console.error(err.message);
  }
  if (response.statusCode === 401) {
    return console.error('Failed to authorize');
  }
  if (response.statusCode === 200) {
    return console.log('File metadata updated');
  }
  console.error('Failed to update file metadata.', body);
};

var payload = {
  name: 'Sample.png',
  metadata: new Buffer("File metadata").toString('base64')
};

request.put(endpoint, {
  auth: {
    bearer: constants.token // pass auth token
  },
  json: true,
  body: payload
}, onResponse);
```

# Create file

Create a file in an existing directory.

Only authorized requests can invoke this endpoint.

### Request

```
POST /nfs/file/:rootPath/:filePath
```

#### URL

| Parameter | Description |
| --- | --- |
| rootPath | Which root directory to use (`app` or `drive`). |
| filePath | The full path of the file. |

##### Example

```
http://localhost:8100/nfs/directory/app/images/sample.png
```

#### Header

| Field | Description |
| --- | --- |
| Authorization | The [authorization token](/auth) obtained from SAFE Launcher. |
| Content-Type | The [media type](https://www.iana.org/assignments/media-types/media-types.xhtml) of the file being uploaded. |
| Content-Length | The size of the file being uploaded |
| Metadata | Metadata to be associated with the file. It should be encoded as a base64 string.<br>This is an optional field. If not specified, it defaults to an empty string. |

##### Example

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
Content-Type: image/png
Content-Length: 25607
Metadata: c2FtcGxlIG1ldGFkYXRh
```

#### Body

Binary data of the file being uploaded.

### Response

On success, the HTTP status code in the response header is `200` (OK).

### Example

```js
var request = require('request');
var fs = require('fs');
var endpoint = 'http://localhost:8100/nfs/file/app/images/sample.png';

var onResponse = function(err, response, body) {
  if (err) {
    return console.error(err.message);
  }
  if (response.statusCode === 401) {
    return console.error('Failed to authorize');
  }
  if (response.statusCode === 200) {
    return console.log('File created');
  }
  console.error('Failed to create file.', body);
};

var localFilePath = './api/sample.png'
var size = fs.statSync(localFilePath).size;
fs.createReadStream(localFilePath).pipe(request.post(endpoint, {
  headers: {
    'Content-Type': 'image/png',
    'Content-Length': size,
    'Metadata': new Buffer('sample metadata').toString('base64')
  },
  auth: {
    bearer: constants.token
  }
}, onResponse));
```

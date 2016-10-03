# Get file

Read a file. The file can be streamed in chunks and also fetched as partial content based on the range header specified in the request.

Only authorized requests can invoke this endpoint.

### Request

```
GET /nfs/file/:rootPath/:filePath
```

#### URL

| Parameter | Description |
| --- | --- |
| rootPath | Which root directory to use (`app` or `drive`). |
| filePath | The full path of the file. |

##### Example

```
http://localhost:8100/nfs/file/app/images/sample.png
```

#### Header

| Field | Description |
| --- | --- |
| Authorization | The [authorization token](/auth) obtained from SAFE Launcher. |
| Range | Partial content of the file can be obtained by specifying the range. The start and end offset can be passed in the range header (e.g `bytes 0-1000`).<br>This is an optional field, if not specified the entire file is streamed to the client. |

##### Example

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
```

### Response

On success, the HTTP status code in the response header is `200` (OK).

#### Header

| Property | Description |
| --- | --- |
| Content-Range | Range being streamed / total size. |
| Created-On | Created timestamp ([ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)). |
| Last-Modified | Last modified timestamp ([ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)). |
| Content-Type | [Media type](https://www.iana.org/assignments/media-types/media-types.xhtml) of the file. |
| Content-Length | Actual size of the file. |
| Metadata | Metadata related to the file (encoded as a base64 string). |

##### Example

```
Content-Range: bytes 0-25607/25607
Created-On: 2016-09-27T08:46:26.921Z
Last-Modified: 2016-09-27T08:46:27.599Z
Content-Type: image/png
Content-Length: 25607
Metadata: c2FtcGxlIG1ldGFkYXRh
```

#### Body

Binary data of the file.

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
    console.log(JSON.stringify(response.headers));
    return console.log('File downloaded');
  }
  console.error('Failed to download file.', body);
};

var filestream = fs.createWriteStream('./api/sample.png'); // local path
request.get(endpoint, {
  auth: {
    bearer: constants.token // pass the auth token
  }
}, onResponse).pipe(filestream);
```

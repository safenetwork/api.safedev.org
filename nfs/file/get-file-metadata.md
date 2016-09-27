# Get file metadata

Fetch the metadata of a file.

Only authorized requests can invoke this endpoint.

### Request

```
HEAD /nfs/file/:rootPath/:filePath
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

##### Example

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
```

### Response

On success, the HTTP status code in the response header is `200` (OK).

#### Header

| Property | Description |
| --- | --- |
| Created-On | Created timestamp ([ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)). |
| Last-Modified | Last modified timestamp ([ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)). |
| Content-Type | [Media type](https://www.iana.org/assignments/media-types/media-types.xhtml) of the file. |
| Content-Length | Actual size of the file. |
| Metadata | Metadata related to the file (encoded as a base64 string). |

##### Example

```
Created-On: 2016-09-27T08:46:26.921Z
Last-Modified: 2016-09-27T08:46:27.599Z
Content-Type: image/png
Content-Length: 25607
Metadata: c2FtcGxlIG1ldGFkYXRh
```

### Example

```js
var request = require('request');
var endpoint = 'http://localhost:8100/nfs/file/app/images/sample.png';

var onResponse = function(err, response, body) {
  if (err) {
    return console.error(err.message);
  }
  if (response.statusCode === 200) {
    return console.log(JSON.stringify(response.headers));
  }
  console.error('Failed', body);
};

request.head(endpoint, {
  auth: {
    bearer: constants.token // pass auth token
  }
}, onResponse);
```

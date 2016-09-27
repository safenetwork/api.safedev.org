# Get file

Read a file from a service home directory.

Authorized and unauthorized requests can invoke this endpoint, but private data can only be acquired via an authorized request.

### Request

```
GET /dns/:serviceName/:longName/:filePath
```

#### URL

| Parameter | Description |
| --- | --- |
| serviceName | The service name for which the file has to be fetched. |
| longName | The long name associated with the service that contains the home directory. |
| filePath | The full path of the file from the root of the service home directory. |

##### Example

```
http://localhost:8100/dns/www/example/index.html
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
Content-Range: bytes 0-175786/175786
Created-On: 1970-01-18T00:21:05.210Z
Last-Modified: 1970-01-18T00:21:05.212Z
Content-Type: text/html
Content-Length: 175786
Metadata: c2FtcGxlIG1ldGFkYXRh
```

#### Body

Binary data of the file.

### Example

```js
var request = require('request');
var fs = require('fs');
var endpoint = 'http://localhost:8100/dns/www/example/index.html';

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
  console.error('Failed to dowload file.', body);
};


var filestream = fs.createWriteStream('./api/index.html');
request.get(endpoint, {
  auth: {
    bearer: constants.token
  }
}, onResponse).pipe(filestream);
```

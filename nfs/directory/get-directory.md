# Get directory

Fetch the metadata of a directory as well as the metadata of its files and subdirectories.

Only authorized requests can invoke this endpoint.

### Request

```
GET /nfs/directory/:rootPath/:directoryPath
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

##### Example

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
```

### Response

On success, the HTTP status code in the response header is `200` (OK).

#### Body

| Property | Description |
| --- | --- |
| info.name | The name of the directory. |
| info.isPrivate | Whether the directory is private or public. |
| info.createdOn | Created timestamp ([ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)). |
| info.modifiedOn | Last modified timestamp ([ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)). |
| info.metadata | Metadata associated with the directory (encoded as a base64 string). |
| files | List of metadata related to the files in the directory. |
| subDirectories | List of metadata related to the subdirectories. |

##### Example

```json
{
	"info": {
		"name": "images",
		"isPrivate": true,
		"createdOn": "2016-09-26T04:41:05.342Z",
		"modifiedOn": "2016-09-26T04:41:05.342Z",
		"metadata": "c2FtcGxlIG1ldGFkYXRh"
	},
	"files": [],
	"subDirectories": []
}
```

### Example

```js
var request = require('request');
var endpoint = 'http://localhost:8100/nfs/directory/app/images';

var onResponse = function(err, response, body) {
  if (err) {
    return console.error(err.message);
  }
  if (response.statusCode === 200) {
    return console.log(body);
  }
  console.error('Failed', body);
};

request.get(endpoint, {
  auth: {
    bearer: constants.token
  }
}, onResponse);
```

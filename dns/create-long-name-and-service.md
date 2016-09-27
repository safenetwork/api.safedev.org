# Create long name and service

Register a long name and a service.

Only authorized requests can invoke this endpoint.

### Request

```
POST /dns
```

#### URL

```
http://localhost:8100/dns
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
| longName | The long name to be created. |
| serviceName | Name of the service to be added. |
| rootPath | Which root directory to use (`app` or `drive`). |
| serviceHomeDirPath | The full path of the directory to be associated to the service. |

##### Example

```json
{
	"longName": "example",
	"serviceName": "www",
	"rootPath": "drive",
	"serviceHomeDirPath": "/websites/example"
}
```

### Response

On success, the HTTP status code in the response header is `200` (OK).

### Example

```js
var request = require('request');
var endpoint = 'http://localhost:8100/dns';

var payload = {
  longName: 'example',
  serviceName: 'www',
  rootPath: 'drive',
  serviceHomeDirPath: '/websites/example'
};

var onResponse = function(err, response, body) {
  if (err) {
    return console.error(err.message);
  }
  if (response.statusCode === 200) {
    return console.log('DNS registered successfully');
  }
  console.error('Operation failed', body);
};

request.post(endpoint, {
  auth: {
    bearer: constants.token
  },
  json: true,
  body: payload
}, onResponse);
```

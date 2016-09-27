# Delete service

Delete a service from a long name.

Only authorized requests can invoke this endpoint.

### Request

```
DELETE /dns/:serviceName/:longName
```

#### URL

| Parameter | Description |
| --- | --- |
| serviceName | The name of the service to be deleted. |
| longName | The long name associated with the service. |

##### Example

```
http://localhost:8100/dns/blog/example
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

### Example

```js
var request = require('request');
var endpoint = 'http://localhost:8100/dns/blog/example';

var onResponse = function(err, response, body) {
  if (err) {
    return console.error(err.message);
  }
  if (response.statusCode === 200) {
    return console.log('Service name deleted');
  }
  console.error('Operation failed', body);
};

request.del(endpoint, {
  auth: {
    bearer: constants.token
  }
}, onResponse);
```

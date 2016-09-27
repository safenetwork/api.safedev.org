# List services

List the services associated with a long name.

Only authorized requests can invoke this endpoint.

### Request

```
GET /dns/:longName
```

#### URL

| Parameter | Description |
| --- | --- |
| longName | The long name for which the list of services has to be fetched. |

##### Example

```
http://localhost:8100/dns/example
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

The response body contains the list of services associated with the long name.

##### Example

```json
[
	"www",
	"test"
]
```

### Example

```js
var request = require('request');
var endpoint = 'http://localhost:8100/dns/example';

var onResponse = function(err, response, body) {
  if (err) {
    return console.error(err.message);
  }
  if (response.statusCode === 200) {
    return console.log(body);
  }
  console.error('Operation failed', body);
};

request.get(endpoint, {
  auth: {
    bearer: constants.token
  }
}, onResponse);
```

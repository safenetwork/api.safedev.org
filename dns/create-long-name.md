# Create long name

Register a long name. Long names are public names that can be shared.

Only authorized requests can invoke this endpoint.

### Request

```
POST /dns/:longName
```

#### URL

| Parameter | Description |
| --- | --- |
| longName | The long name to be created. |

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

### Example

```js
var longName = 'example'; // Long name to be created

var request = require('request');
var endpoint = 'http://localhost:8100/dns/' + longName;

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
  }
}, onResponse);
```

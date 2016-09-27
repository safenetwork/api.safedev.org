# Validate app authorization

Check whether the authorization token obtained from SAFE Launcher is still valid.

This endpoint can be useful for apps that cache their authorization token to avoid making unnecessary authorization requests to SAFE Launcher (e.g. a user could restart an app while SAFE Launcher is still running).

The `Authorization` header field must be present in the request.

### Request

```
GET /auth
```

#### URL

```
http://localhost:8100/auth
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
var endpoint = 'http://localhost:8100/auth';

var onResponse = function(err, response, body) {
  if (err) {
    return console.error(err.message);
  }
  if (response.statusCode === 200) {
    return console.log('Token valid');
  }
  console.error('Invalid token.', body);
};

request.get(endpoint, {
  auth: {
    bearer: constants.token // pass the auth token
  }
}, onResponse);
```

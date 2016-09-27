# Authorize app

Request an authorization token from SAFE Launcher.

Any app that wants to access endpoints that require [authorized access](/auth#authorized-access) must receive an authorization token from SAFE Launcher.

### Request

```
POST /auth
```

#### URL

```
http://localhost:8100/auth
```

#### Header

| Field | Description |
| --- | --- |
| Content-Type | The [media type](https://www.iana.org/assignments/media-types/media-types.xhtml) of the request body (`application/json`). |

#### Body

| Property | Description |
| --- | --- |
| app.name | Name of the app requesting authorization with the SAFE Launcher. |
| app.id | ID of the app. It should be unique among the apps provided by the vendor.<br>If the ID (or the vendor name of the app) changes, the app data will be lost.<br>Likewise, if multiple apps of the same vendor use the same the ID, then they will share the same app folder. |
| app.version | Version of the app. |
| app.vendor | Vendor name of the app. |
| permissions | List of permissions requested by the app (e.g. `SAFE_DRIVE_ACCESS`). |

##### Example

```json
{
	"app": {
		"name": "Sample Application",
		"id": "com.maidsafe.sample",
		"version": "0.0.1",
		"vendor": "MaidSafe"
	},
	"permissions": [
		"SAFE_DRIVE_ACCESS"
	]
}
```

### Response

On success, the HTTP status code in the response header is `200` (OK).

#### Body

| Property | Description |
| --- | --- |
| token | JWT token that can be used in API calls that require authorization. This token has to be passed in the `Authorization` header field. |
| permissions | List of permissions approved by the user. |

##### Example

```json
{
	"token": "eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4",
	"permissions": [
		"SAFE_DRIVE_ACCESS"
	]
}
```

### Example

```js
var request = require('request');

var endpoint = 'http://localhost:8100/auth';

// authorization payload
var payload = {
  "app": {
    "name": "Sample Application",
    "id": "com.maidsafe.sample",
    "version": "0.0.1",
    "vendor": "MaidSafe"
  },
  "permissions": [
    "SAFE_DRIVE_ACCESS"
  ]
};

var onResponse = function(err, response, body) {
  if (err) {
    return console.error(err.message);
  }
  if (response.statusCode === 401) {
    return console.error('Failed to authorize');
  }
  console.log('Auth token', body.token);
};

request.post(endpoint, {
  json: true,
  body: payload
}, onResponse);
```

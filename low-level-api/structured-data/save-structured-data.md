# Save structured data

`safe_core` calls PUT to store a new structured data on the SAFE Network and POST to update
an existing structured data. When a structured data is created for the first time, the app should call the PUT endpoint and when updating an existing structured data, the
app should call the POST endpoint.

## PUT endpoint

Only authorized requests can invoke this endpoint.

### Request

```
PUT /structured-data/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing a structured data handle. |

##### Example

```
http://localhost:8100/structured-data/2
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

## POST endpoint

Only authorized requests can invoke this endpoint.

### Request

```
POST /structured-data/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing a structured data handle. |

##### Example

```
http://localhost:8100/structured-data/2
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

# Save appendable data

`safe_core` calls PUT to store a new appendable data on the SAFE Network and POST to update
an existing appendable data. When an appendable data is created for the first time, the app should call the PUT endpoint and when updating an existing appendable data, the
app should call the POST endpoint.

## PUT endpoint

Only authorized requests can invoke this endpoint.

### Request

```
PUT /appendable-data/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing an appendable data handle. |

##### Example

```
http://localhost:8100/appendable-data/9
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
POST /appendable-data/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing an appendable data handle. |

##### Example

```
http://localhost:8100/appendable-data/23
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

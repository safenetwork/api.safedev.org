# Remove signing keys

Remove signing keys from the filter of an appendable data. You need to use the [Save appendable data](../save-appendable-data.md) endpoint for this change to reflect on the SAFE Network.

Only authorized requests can invoke this endpoint.

### Request

```
DELETE /appendable-data/filter/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing an appendable data handle. |

##### Example

```
http://localhost:8100/appendable-data/filter/39
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

A list of signing key handles.

##### Example

```json
[
	35
]
```

### Response

On success, the HTTP status code in the response header is `200` (OK).

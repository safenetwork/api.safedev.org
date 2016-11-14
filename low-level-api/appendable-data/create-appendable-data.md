# Create appendable data

Create an appendable data. To save it on the SAFE Network, you need to use the [Save appendable data](save-appendable-data.md) endpoint.

Only authorized requests can invoke this endpoint.

### Request

```
POST /appendable-data
```

#### URL

```
http://localhost:8100/appendable-data
```

#### Header

| Field | Description |
| --- | --- |
| Authorization | The [authorization token](/auth) obtained from SAFE Launcher. |
| Content-Type | The [media type](https://www.iana.org/assignments/media-types/media-types.xhtml) of the request body (`application/json`). |

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
Content-Type: application/json
```

#### Body

| Property | Description |
| --- | --- |
| name | A 32-byte identifier (encoded as a base64 string). |
| isPrivate | Whether the appendable data should be private or public (`true` or `false`).<br>Optional. Defaults to `false`. |
| filterType | What filter type the appendable data should have (`WHITE_LIST` or `BLACK_LIST`).<br>Optional. Defaults to `BLACK_LIST`. |
| filterKey | List of signing key handles.<br>Optional. |

##### Example

```json
{
	"name": "b2E2+Rh29TsjjSWkgu47d/PyK1p6i4T3c35rdFQb/VM=",
	"isPrivate": true
}
```

### Response

On success, the HTTP status code in the response header is `200` (OK).

#### Body

| Property | Description |
| --- | --- |
| handleId | u64 representing the appendable data handle. |

##### Example

```json
{
	"handleId": 9
}
```

# Create structured data

Create a structured data. To save it on the SAFE Network, you need to use the [Save structured data](save-structured-data.md) endpoint.

Only authorized requests can invoke this endpoint.

### Request

```
POST /structured-data
```

#### URL

```
http://localhost:8100/structured-data
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
| typeTag | Unversioned (500), versioned (501) or custom (above 15000).<br>Optional. Defaults to 500. |
| cipherOpts | u64 representing a [cipher options](/low-level-api/cipher-options) handle.<br>Optional. Defaults to `PLAIN`. |
| data | Content of the structured data (encoded as a base64 string).<br>Optional. |
| version | Normally the version should be 0, but when you want to claim a structured data, you need to specify a version based on the current version of the structured data (v + 1).<br>Optional. Defaults to 0. |

##### Example

```json
{
	"name": "b2E2+Rh29TsjjSWkgu47d/PyK1p6i4T3c35rdFQb/VM=",
	"typeTag": 501,
	"cipherOpts": 0,
	"data": "dGVzdCBzdHJ1Y3R1cmVkIGRhdGE="
}
```

### Response

On success, the HTTP status code in the response header is `200` (OK).

#### Body

| Property | Description |
| --- | --- |
| handleId | u64 representing the structured data handle. |

##### Example

```json
{
	"handleId": 2
}
```

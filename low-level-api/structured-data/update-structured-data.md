# Update structured data

Update the data held by a structured data using a structured data handle. To save it on the SAFE Network, you need to use the [Save structured data](save-structured-data.md) endpoint.

Only authorized requests can invoke this endpoint.

### Request

```
PATCH /structured-data/:handleId
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
| Content-Type | The [media type](https://www.iana.org/assignments/media-types/media-types.xhtml) of the request body (`application/json`). |

##### Example

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
Content-Type: application/json
```

#### Body

| Property | Description |
| --- | --- |
| cipherOpts | u64 representing a [cipher options](/low-level-api/cipher-options) handle.<br>Optional. Defaults to `PLAIN`. |
| data | Content of the structured data (encoded as a base64 string).<br>Optional. |

##### Example

```json
{
	"cipherOpts": 0,
	"data": "dGVzdCB1cGRhdGVkIHN0cnVjdHVyZWQgZGF0YQ=="
}
```

### Response

On success, the HTTP status code in the response header is `200` (OK).

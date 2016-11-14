# Get structured data metadata

Fetch the metadata of a structured data using a structured data handle.

Authorized and unauthorized requests can invoke this endpoint.

### Request

```
GET /structured-data/metadata/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing a structured data handle. |

##### Example

```
http://localhost:8100/structured-data/metadata/2
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

| Property | Description |
| --- | --- |
| isOwner | Whether the current user is the owner of the structured data. |
| version | Version of the structured data. |
| dataVersionLength | The number of data versions (only for type tag 501). |

##### Example

```json
{
	"isOwner": true,
	"version": 0,
	"dataVersionLength": 1
}
```

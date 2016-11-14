# Deserialize structured data

Deserialize a structured data.

Authorized and unauthorized requests can invoke this endpoint.

### Request

```
POST /structured-data/deserialise
```

#### URL

```
http://localhost:8100/structured-data/deserialise
```

#### Header

| Field | Description |
| --- | --- |
| Authorization | The [authorization token](/auth) obtained from SAFE Launcher. |

##### Example

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
```

#### Body

Binary data representing the serialized structured data.

### Response

On success, the HTTP status code in the response header is `200` (OK).

#### Body

| Property | Description |
| --- | --- |
| handleId | u64 representing the structured data handle. |
| isOwner | Whether the current user is the owner of the structured data. |
| version | The version of the structured data. |
| dataVersionLength | The number of data versions (only for type tag 501). |

##### Example

```json
{
	"handleId": 6,
	"isOwner": true,
	"version": 0,
	"dataVersionLength": 1
}
```

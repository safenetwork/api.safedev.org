# Deserialize signing key

Deserialize a signing key.

Only authorized requests can invoke this endpoint.

### Request

```
POST /sign-key/deserialise
```

#### URL

```
http://localhost:8100/sign-key/deserialise
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

Binary data representing the serialized signing key.

### Response

On success, the HTTP status code in the response header is `200` (OK).

#### Body

| Property | Description |
| --- | --- |
| handleId | u64 representing the signing key handle. |

##### Example

```json
{
	"handleId": 42
}
```

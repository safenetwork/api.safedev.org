# Drop cipher options handle

Drop a cipher options handle.

Authorized and unauthorized requests can invoke this endpoint.

### Request

```
DELETE /cipher-opts/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing the handle ID. |

##### Example

```
http://localhost:8100/cipher-opts/0
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

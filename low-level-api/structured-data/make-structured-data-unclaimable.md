# Make structured data unclaimable

Make a structured data unclaimable using a structured data handle. After this operation, the structured data will remain in the SAFE Network and its content will be empty, but it will not be claimable by anyone anymore including the original owner.

Only authorized requests can invoke this endpoint.

### Request

```
DELETE /structured-data/unclaim/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing a structured data handle. |

##### Example

```
http://localhost:8100/structured-data/unclaim/4
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

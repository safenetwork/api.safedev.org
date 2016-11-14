# Drop immutable data handle

Drop an immutable data handle.

## Drop immutable data reader handle

Authorized and unauthorized requests can invoke this endpoint.

### Request

```
DELETE /immutable-data/reader/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing an immutable data reader handle. |

##### Example

```
http://localhost:8100/immutable-data/reader/2
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

## Drop immutable data writer handle

Only authorized requests can invoke this endpoint.

### Request

```
DELETE /immutable-data/writer/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing an immutable data writer handle. |

##### Example

```
http://localhost:8100/immutable-data/writer/2
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

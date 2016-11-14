# Get immutable data handle

Obtain an immutable data handle.

## Get immutable data reader handle

Authorized and unauthorized requests can invoke this endpoint.

### Request

```
GET /immutable-data/reader/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing a data ID handle. |

##### Example

```
http://localhost:8100/immutable-data/reader/0
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
| handleId | u64 representing the immutable data reader handle. |
| size | Original (pre-encryption) size of the immutable data. |

##### Example

```json
{
	"handleId": 2,
	"size": 0
}
```

## Get immutable data writer handle

Only authorized requests can invoke this endpoint.

### Request

```
GET /immutable-data/writer
```

#### URL

```
http://localhost:8100/immutable-data/writer
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
| handleId | u64 representing the immutable data writer handle. |

##### Example

```json
{
	"handleId": 2
}
```

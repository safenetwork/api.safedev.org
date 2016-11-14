# Write immutable data

Store the content of an immutable data on the SAFE Network. Supports streaming. To generate a data map, you need to use the [Close immutable data writer](close-immutable-data-writer.md) endpoint. You need to have a data map in order to be able to retrieve an immutable data.

Only authorized requests can invoke this endpoint.

### Request

```
POST /immutable-data/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing an immutable data writer handle. |

##### Example

```
http://localhost:8100/immutable-data/2
```

#### Header

| Field | Description |
| --- | --- |
| Authorization | The [authorization token](/auth) obtained from SAFE Launcher. |
| Content-Length | Original (pre-encryption) size of the immutable data. |

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
Content-Length: 25607
```

#### Body

The binary data of the immutable data.

### Response

On success, the HTTP status code in the response header is `200` (OK).

# Close immutable data writer

Generate a data map and save it on the SAFE Network.<br>Should be invoked after using the [Write immutable data](write-immutable-data.md) endpoint.

Only authorized requests can invoke this endpoint.

### Request

```
PUT /immutable-data/:handleId/:cipherOptsHandle
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing an immutable data writer handle. |
| cipherOptsHandle | u64 representing a [cipher options](/low-level-api/cipher-options) handle. |

```
http://localhost:8100/immutable-data/2/0
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
| handleId | u64 representing a data ID handle which can be used to read the content of the immutable data. |

##### Example

```json
{
	"handleId": 7
}
```

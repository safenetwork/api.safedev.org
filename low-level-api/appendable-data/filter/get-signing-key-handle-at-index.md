# Get signing key handle at index

Obtain a signing key handle representing the nth signing key inside the filter of an appendable data.

Only authorized requests can invoke this endpoint.

### Request

```
GET /appendable-data/filter/:handleId/:index
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing an appendable data handle. |
| index | A number representing the nth signing key inside the filter of the appendable data. |

##### Example

```
http://localhost:8100/appendable-data/filter/36/0
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
| handleId | u64 representing the signing key handle. |

##### Example

```json
{
	"handleId": 37
}
```

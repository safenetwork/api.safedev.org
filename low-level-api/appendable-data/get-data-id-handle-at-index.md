# Get data ID handle at index

Obtain a data ID handle for a data item or deleted data item.

## For a data item

Authorized and unauthorized requests can invoke this endpoint.

### Request

```
GET /appendable-data/:handleId/:index
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing an appendable data handle. |
| index | A number representing the nth data item. |

##### Example

```
http://localhost:8100/appendable-data/23/0
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
| handleId | u64 representing the data ID handle. |

##### Example

```json
{
	"handleId": 26
}
```

## For a deleted data item

Authorized and unauthorized requests can invoke this endpoint.

### Request

```
GET /appendable-data/deleted-data/:handleId/:index
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing an appendable data handle. |
| index | A number representing the nth deleted data item. |

##### Example

```
http://localhost:8100/appendable-data/deleted-data/28/0
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
| handleId | u64 representing the data ID handle. |

##### Example

```json
{
	"handleId": 27
}
```

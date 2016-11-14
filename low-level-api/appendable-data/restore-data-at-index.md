# Restore data at index

Restore a deleted data item from an appendable data. You need to use the [Save appendable data](save-appendable-data.md) endpoint for this change to reflect on the SAFE Network.

Only authorized requests can invoke this endpoint.

### Request

```
PUT /appendable-data/restore/:handleId/:index
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing an appendable data handle. |
| index | A number representing the nth deleted data item. |

##### Example

```
http://localhost:8100/appendable-data/restore/32/0
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

# Clear all data

Remove all data items or deleted data items from an appendable data. You need to use the [Save appendable data](save-appendable-data.md) endpoint for this change to reflect on the SAFE Network.

## Clear all data items

This operation will move all data items to the `deleted_data` section of the appendable data.

Only authorized requests can invoke this endpoint.

### Request

```
DELETE /appendable-data/clear-data/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing an appendable data handle. |

##### Example

```
http://localhost:8100/appendable-data/clear-data/32
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

## Clear all deleted data items

This operation will remove all data items from the `deleted_data` section of the appendable data.

Only authorized requests can invoke this endpoint.

### Request

```
DELETE /appendable-data/clear-deleted-data/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing an appendable data handle. |

##### Example

```
http://localhost:8100/appendable-data/clear-deleted-data/33
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

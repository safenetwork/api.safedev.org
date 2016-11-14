# Deserialize appendable data

Deserialize an appendable data.

Authorized and unauthorized requests can invoke this endpoint.

### Request

```
POST /appendable-data/deserialise
```

#### URL

```
http://localhost:8100/appendable-data/deserialise
```

#### Header

| Field | Description |
| --- | --- |
| Authorization | The [authorization token](/auth) obtained from SAFE Launcher. |

##### Example

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
```

#### Body

Binary data representing the serialized appendable data.

### Response

On success, the HTTP status code in the response header is `200` (OK).

#### Body

| Property | Description |
| --- | --- |
| handleId | u64 representing the appendable data handle. |
| isOwner | Whether the current user is the owner of the appendable data. |
| version | The version of the appendable data. |
| filterType | The filter type of the appendable data (`WHITE_LIST` or `BLACK_LIST`). |
| dataLength | The number of data items inside the appendable data. |
| deletedDataLength | The number of deleted data items inside the appendable data. |

##### Example

```json
{
	"handleId": 20,
	"isOwner": true,
	"version": 0,
	"filterType": "BlackList",
	"dataLength": 0,
	"deletedDataLength": 0
}
```

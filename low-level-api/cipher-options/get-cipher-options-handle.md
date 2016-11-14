# Get cipher options handle

Obtain a cipher options handle.

Authorized requests can invoke this endpoint.<br>Unauthorized requests are only permitted for `PLAIN` encryption.

### Request

```
GET /cipher-opts/:encType/:keyHandle?
```

#### URL

| Parameter | Description |
| --- | --- |
| encType | Which type of encryption to use (`PLAIN`, `SYMMETRIC` or `ASYMMETRIC`). |
| keyHandle | u64 representing an encryption key handle. Must be specified for asymmetric encryption. |

##### Example

```
http://localhost:8100/cipher-opts/SYMMETRIC
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
| handleId | u64 representing the cipher options handle. |

##### Example

```json
{
	"handleId": 0
}
```

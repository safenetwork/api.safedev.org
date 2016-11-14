# Get data ID handle

Obtain a data ID handle.

## For structured data

Authorized and unauthorized requests can invoke this endpoint.

### Request

```
POST /data-id/structured-data
```

#### URL

```
http://localhost:8100/data-id/structured-data
```

#### Header

| Field | Description |
| --- | --- |
| Authorization | The [authorization token](/auth) obtained from SAFE Launcher. |
| Content-Type | The [media type](https://www.iana.org/assignments/media-types/media-types.xhtml) of the request body (`application/json`). |

##### Example

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
Content-Type: application/json
```

#### Body

| Property | Description |
| --- | --- |
| name | A 32-byte identifier (encoded as a base64 string). |
| typeTag | Unversioned (500), versioned (501) or custom (above 15000).<br>Optional. Defaults to 500. |

##### Example

```json
{
	"name": "b2E2+Rh29TsjjSWkgu47d/PyK1p6i4T3c35rdFQb/VM=",
	"typeTag": 501
}
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
	"handleId": 3
}
```

## For appendable data

Authorized and unauthorized requests can invoke this endpoint.

### Request

```
POST /data-id/appendable-data
```

#### URL

```
http://localhost:8100/data-id/appendable-data
```

#### Header

| Field | Description |
| --- | --- |
| Authorization | The [authorization token](/auth) obtained from SAFE Launcher. |
| Content-Type | The [media type](https://www.iana.org/assignments/media-types/media-types.xhtml) of the request body (`application/json`). |

##### Example

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
Content-Type: application/json
```

#### Body

| Property | Description |
| --- | --- |
| name | A 32-byte identifier (encoded as a base64 string). |
| isPrivate | Whether the appendable data is private or public (`true` or `false`).<br> Optional. Defaults to `false`. |

##### Example

```json
{
	"name": "b2E2+Rh29TsjjSWkgu47d/PyK1p6i4T3c35rdFQb/VM=",
	"isPrivate": true
}
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
	"handleId": 5
}
```

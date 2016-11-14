# Read structured data

Read the content of a structured data using a structured data handle. For versioned structured data (type tag 501), the latest version is read by default.

Authorized and unauthorized requests can invoke this endpoint.

### Request

```
GET /structured-data/:handleId/:version?
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing a structured data handle. |
| version | Number of a specific version to be read. Passed only for versioned structured data.<br>Optional. Defaults to the latest version. |

##### Example

```
http://localhost:8100/structured-data/2
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

The binary data of the structured data.

##### Example

```
test structured data
```

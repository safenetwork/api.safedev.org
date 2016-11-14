# Read immutable data

Read the content of an immutable data using an immutable reader handle. Supports streaming and partial read using the range header.

Authorized and unauthorized requests can invoke this endpoint.

### Request

```
GET /immutable-data/:handleId
```

#### URL

| Parameter | Description |
| --- | --- |
| handleId | u64 representing an immutable data reader handle. |

##### Example

```
http://localhost:8100/immutable-data/2
```

#### Header

| Field | Description |
| --- | --- |
| Authorization | The [authorization token](/auth) obtained from SAFE Launcher. |
| Range | Partial content of the immutable data can be obtained by specifying the range. The start and end offset can be passed in the range header (e.g `bytes=0-1000`).<br>This is an optional field, if not specified the entire content of the immutable data is streamed to the client. |

##### Example

```
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJpZCI6Im5RT1poRFJ2VUFLRlVZMzNiRTlnQ25VbVVJSkV0Q2lmYk4zYjE1dXZ2TlU9In0.OTKcHQ9VUKYzBXH_MqeWR4UcHFJV-xlllR68UM9l0b4
```

### Response

On success, if a `Range` header was specified in the request, then the HTTP status code in the response header is `206` (Partial Content). Otherwise, it's `200` (OK).

#### Header

| Property | Description |
| --- | --- |
| Content-Range | Range being streamed / total size. |
| Content-Length | Original (pre-encryption) size of the immutable data. |

##### Example

```
Content-Range: bytes 0-25607/25607
Content-Length: 25607
```

#### Body

The binary data of the immutable data.

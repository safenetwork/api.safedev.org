# Structured Data API

Structured data has a size restriction of 100 KiB including its internals. If the size is more than the permitted size after serialization, an error is returned.

Unversioned, versioned and custom structured data types can be created.

If the size of the data being passed is greater than 100KiB, the versioned and unversioned
structured data will ensure that the data is managed and stored successfully. For custom type tags, it becomes the responsibility of the app to handle the size restriction.

| Type | Tag | Description |
| --- | --- | --- |
| Unversioned | 500 | Only holds the latest version. |
| Versioned | 501 | Holds all the versions. Older versions can be fetched by specifying a version number. |
| Custom | >15000 | Apps are free to use any type tag value greater than 15000. |

The content of a structured data can be encrypted using a [cipher options](/low-level-api/cipher-options) handle.

The type tag and ID combination is needed in order to fetch a structured data from the SAFE Network.

The ID of a structured data is a base64 string representing a 32-byte identifier.

A structured data handle is needed in order to work with a structured data and it
must be dropped after usage.

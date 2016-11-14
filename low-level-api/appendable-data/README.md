# Appendable Data API

Appendable data has a size restriction of 100 KiB including its internals. If the size is more than the permitted size after serialization, an error is returned.

There are two types of appendable data:

| Type | Description |
| --- | --- |
| Public | Appended data can be read by anyone. |
| Private | Appended data can only be read by the owner. |

An appendable data can be fetched from SAFE Network based on its ID. The ID is a base64 string
representing 32-byte identifier.

Appendable data also provides the option to filter users by public key. Two filter types are supported:

| Type | Description |
| --- | --- |
| WHITE_LIST | Only the listed keys are allowed to append data. |
| BLACK_LIST | Everyone except the listed keys are allowed to append data. |

See [RFC 38 – Appendable Data](https://github.com/maidsafe/rfcs/blob/master/text/0038-appendable-data/0038-appendable-data.md) for more details.

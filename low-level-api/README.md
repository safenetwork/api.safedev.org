# Low-Level API

The low-level API is comprised of the following APIs:

- [Structured Data](structured-data/README.md)
- [Immutable Data](immutable-data/README.md)
- [Appendable Data](appendable-data/README.md)
- [Data ID](data-id/README.md)
- [Cipher Options](cipher-options/README.md)

### Permission

Apps must request the `LOW_LEVEL_API` permission to invoke the low-level API to store or
read encrypted data.

By providing the `LOW_LEVEL_API` permission, the user should be aware that the app can now store data outside of SAFE Launcher's sandboxing. If the app doesn't properly keep track of the data it creates, the user might be unable to retrieve and delete data stored by the app. For example, it might be possible that some of the data created by the app cannot be deleted by the user. It's the responsibility of the app to keep track of the data it creates using the low-level API.

### Unauthorized access

Unauthorized access is granted by default for reading public data using the low-level API.

### Handle

The low-level API requires the usage of a handle corresponding to the data type that is being worked with. For example, operations can be performed on a structured data using a structured data handle.

It becomes the app's responsibility to drop the handle after usage.

If the handle is not cleaned up properly, it can lead to a memory leak. `safe_core`
will purge the least recently used handles if the number of handles goes above a certain threshold.

See [RFC 41 – Low Level API](https://github.com/maidsafe/rfcs/blob/master/text/0041-low-level-api/0041-low-level-api.md) for more details.

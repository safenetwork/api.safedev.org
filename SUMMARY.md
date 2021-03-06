# Summary

* [Introduction](README.md)
* [Authorization](auth/README.md)
  * [Authorize app](auth/authorize-app.md)
  * [Validate app authorization](auth/validate-app-authorization.md)
  * [Revoke app](auth/revoke-app.md)
* [NFS](nfs/README.md)
  * [Directory](nfs/directory/README.md)
    * [Create directory](nfs/directory/create-directory.md)
    * [Get directory](nfs/directory/get-directory.md)
    * [Update directory](nfs/directory/update-directory.md)
    * [Move directory](nfs/directory/move-directory.md)
    * [Delete directory](nfs/directory/delete-directory.md)
  * [File](nfs/file/README.md)
    * [Create file](nfs/file/create-file.md)
    * [Get file metadata](nfs/file/get-file-metadata.md)
    * [Get file](nfs/file/get-file.md)
    * [Update file metadata](nfs/file/update-file-metadata.md)
    * [Move file](nfs/file/move-file.md)
    * [Delete file](nfs/file/delete-file.md)
* [DNS](dns/README.md)
  * [Create long name](dns/create-long-name.md)
  * [Create long name and service](dns/create-long-name-and-service.md)
  * [Add service](dns/add-service.md)
  * [List long names](dns/list-long-names.md)
  * [List services](dns/list-services.md)
  * [Get home directory](dns/get-home-directory.md)
  * [Get file](dns/get-file.md)
  * [Remove service](dns/remove-service.md)
  * [Delete long name](dns/delete-long-name.md)
* [Low-Level API](low-level-api/README.md)
  * [Structured Data](low-level-api/structured-data/README.md)
    * [Create structured data](low-level-api/structured-data/create-structured-data.md)
    * [Save structured data](low-level-api/structured-data/save-structured-data.md)
    * [Get structured data handle](low-level-api/structured-data/get-structured-data-handle.md)
    * [Get data ID handle](low-level-api/structured-data/get-data-id-handle.md)
    * [Get structured data metadata](low-level-api/structured-data/get-structured-data-metadata.md)
    * [Validate structured data size](low-level-api/structured-data/validate-structured-data-size.md)
    * [Read structured data](low-level-api/structured-data/read-structured-data.md)
    * [Update structured data](low-level-api/structured-data/update-structured-data.md)
    * [Delete structured data](low-level-api/structured-data/delete-structured-data.md)
    * [Make structured data unclaimable](low-level-api/structured-data/make-structured-data-unclaimable.md)
    * [Serialize structured data](low-level-api/structured-data/serialize-structured-data.md)
    * [Deserialize structured data](low-level-api/structured-data/deserialize-structured-data.md)
    * [Drop structured data handle](low-level-api/structured-data/drop-structured-data-handle.md)
  * [Immutable Data](low-level-api/immutable-data/README.md)
    * [Get immutable data handle](low-level-api/immutable-data/get-immutable-data-handle.md)
    * [Read immutable data](low-level-api/immutable-data/read-immutable-data.md)
    * [Write immutable data](low-level-api/immutable-data/write-immutable-data.md)
    * [Close immutable data writer](low-level-api/immutable-data/close-immutable-data-writer.md)
    * [Drop immutable data handle](low-level-api/immutable-data/drop-immutable-data-handle.md)
  * [Appendable Data](low-level-api/appendable-data/README.md)
    * [Create appendable data](low-level-api/appendable-data/create-appendable-data.md)
    * [Save appendable data](low-level-api/appendable-data/save-appendable-data.md)
    * [Get appendable data handle](low-level-api/appendable-data/get-appendable-data-handle.md)
    * [Get data ID handle](low-level-api/appendable-data/get-data-id-handle.md)
    * [Get appendable data metadata](low-level-api/appendable-data/get-appendable-data-metadata.md)
    * [Validate appendable data size](low-level-api/appendable-data/validate-appendable-data-size.md)
    * [Append data](low-level-api/appendable-data/append-data.md)
    * [Get data ID handle at index](low-level-api/appendable-data/get-data-id-handle-at-index.md)
    * [Get signing key handle at index](low-level-api/appendable-data/get-signing-key-handle-at-index.md)
    * [Remove data at index](low-level-api/appendable-data/remove-data-at-index.md)
    * [Restore data at index](low-level-api/appendable-data/restore-data-at-index.md)
    * [Clear all data](low-level-api/appendable-data/clear-all-data.md)
    * [Serialize appendable data](low-level-api/appendable-data/serialize-appendable-data.md)
    * [Deserialize appendable data](low-level-api/appendable-data/deserialize-appendable-data.md)
    * [Drop appendable data handle](low-level-api/appendable-data/drop-appendable-data-handle.md)
    * [Encryption Key](low-level-api/appendable-data/encryption-key/README.md)
      * [Get encryption key handle](low-level-api/appendable-data/encryption-key/get-encryption-key-handle.md)
      * [Drop encryption key handle](low-level-api/appendable-data/encryption-key/drop-encryption-key-handle.md)
    * [Filter](low-level-api/appendable-data/filter/README.md)
      * [Add signing keys](low-level-api/appendable-data/filter/add-signing-keys.md)
      * [Get signing key handle at index](low-level-api/appendable-data/filter/get-signing-key-handle-at-index.md)
      * [Remove signing keys](low-level-api/appendable-data/filter/remove-signing-keys.md)
      * [Toggle filter](low-level-api/appendable-data/filter/toggle-filter.md)
    * [Signing Key](low-level-api/appendable-data/signing-key/README.md)
      * [Get signing key handle](low-level-api/appendable-data/signing-key/get-signing-key-handle.md)
      * [Serialize signing key](low-level-api/appendable-data/signing-key/serialize-signing-key.md)
      * [Deserialize signing key](low-level-api/appendable-data/signing-key/deserialize-signing-key.md)
      * [Drop signing key handle](low-level-api/appendable-data/signing-key/drop-signing-key-handle.md)
  * [Data ID](low-level-api/data-id/README.md)
    * [Get data ID handle](low-level-api/data-id/get-data-id-handle.md)
    * [Serialize data ID](low-level-api/data-id/serialize-data-id.md)
    * [Deserialize data ID](low-level-api/data-id/deserialize-data-id.md)
    * [Drop data ID handle](low-level-api/data-id/drop-data-id-handle.md)
  * [Cipher Options](low-level-api/cipher-options/README.md)
    * [Get cipher options handle](low-level-api/cipher-options/get-cipher-options-handle.md)
    * [Drop cipher options handle](low-level-api/cipher-options/drop-cipher-options-handle.md)

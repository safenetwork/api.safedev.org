# Encryption Key API

This API provides the ability to obtain an encryption key handle representing the public encryption key of a private appendable data owner. You can use this encryption key to encrypt data (e.g. a structured data or an immutable data) using [asymmetric encryption](/low-level-api/cipher-options/). That way, when you append the data to the private appendable data, only the owner will be able to read it.

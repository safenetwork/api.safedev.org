# Cipher Options API

Data can be encrypted using a cipher options handle. There are three types of encryption:

| Encryption | Description |
| ----- | --- |
| PLAIN | Data is not encrypted. |
| SYMMETRIC | Data is encrypted using symmetric encryption. |
| ASYMMETRIC | Data is encrypted using asymmetric encryption. |

### Plain

This option is used when you want to publish data publicly. Anyone will be able to read it.

### Symmetric

This type of encryption is used when encrypting data for yourself. Only you will be able to read it.

We use a particular combination of Salsa20 and Poly1305 as specified [here](http://docs.maidsafe.net/rust_sodium/master/rust_sodium/crypto/secretbox/xsalsa20poly1305/index.html) and [here](http://nacl.cr.yp.to/valid.html).

### Asymmetric

This type of encryption is used when encrypting data for someone else to read. After encrypting data using the public [encryption key](/low-level-api/appendable-data/encryption-key/) of someone else, only that person will be able to read it.

We use a particular combination of Curve25519, Blake2B, Salsa20 and Poly1305 as specified [here](http://docs.maidsafe.net/rust_sodium/master/rust_sodium/crypto/sealedbox/curve25519blake2bxsalsa20poly1305/index.html).

Asymmetric encryption is detailed in [RFC 41 – Low Level API](https://github.com/maidsafe/rfcs/blob/master/text/0041-low-level-api/0041-low-level-api.md).

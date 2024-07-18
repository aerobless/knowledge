# Fundamentals

## Encoding

Encoding is the process of transforming data from one format into another using a publicly available scheme. For encoding no key is used. Encoding can be easily reversed. A typical use case for encoding is e.g. [UTF-8](https://en.wikipedia.org/wiki/UTF-8) character encoding. Another example is [Base64](https://en.wikipedia.org/wiki/Base64). Base64 is used to encode binary data as text characters.

## Encryption

Encryption is used for data confidentiality. It is the process of transforming data so that only specific individuals can reverse the transformation. A typical use case is encrypting a message so that only its recipient can read it.

## Hashing

Hashing is a non-reversible transformation of data. Multiple unique data strings can result in the same hash, this is a called a hash collision. Hashing is used e.g. to store passwords, typically in combination with a [[🔐 Security#Salt|salt]]. Hashing is also used in data structures, e.g. HashTable to quickly access data. Hashing is also used in [[🔐 Security#PKI (Public Key Infrastructure)|PKI (Public Key Infrastructure)]] e.g. for SSL certificates. Here a CA (Certificate Authority) signs the hash of a certificate.

### Salt

Passwords shouldn't be stored in plain text. Instead the password + some random data, aka the salt should be run through a one-way function. The result is a unique hash that can then be stored. A different salt should be used for each user. This helps mitigate damage if the passwords database is compromised. An attacker can't use a pre computed table of known hashes to find out the passwords of the users. Or at the very least they have to re-compute their dictionary against your salts. Since a different salt is used for each user this uses up a bit of computing power and slows down an attacker.

## PKI (Public Key Infrastructure)

A typical example of public key infrastructure is the SSL certificate system used for the internet. SSL certificates are set up using a [[🔐 Security#Chain of trust|chain of trust]] from the root CA (Certificate Authority) to the end user. In order for PKI to work the user needs to trust a few root CA certificates that then sign the certificates of other CAs and their customers. Typically these root CAs certificates are included in the operating system or browser. But it's also possible for a user to install additional certificates, e.g. for a companies internal network.

### Chain of trust

The chain of trust in SSL consists of a hierarchy of certificates. For example a root CA signs the hash of the certificate of an intermediary CA. This intermediary can then sign certificates of its customers. The browser of a enduser can then verify that all the signatures on the certificates in the chain are valid and compare the root certificate against its stored root certificate.


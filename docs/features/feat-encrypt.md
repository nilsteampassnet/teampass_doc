
# Data encryption in Teampass

Encryption is performed on `passwords` and `custom fields`. In other words the password strings stored by the users are encrypted in the database.
All other fields are in clear text in the database.

# Encryption type

Encryption is performed using the Defuse PHP-Encryption library ([Github project](https://github.com/defuse/php-encryption)).

## Crypto at a Glance

- Encryption type used is AES-256-CTR. Note: 256-bit keys offer 2^128 post-quantum security.
- Message Integrity	is HMAC-SHA256.
- Key-Splitting used Salted HKDF-HMAC-SHA256. Note: Each message gets its own HKDF salt in addition to its own CTR nonce.

## Cryptography Details

Here is a high-level description of how this library works. Any discrepancy between this documentation and the actual implementation will be considered a security bug.

Let's start with the following definitions:

HKDF-SHA256(k, n, info, s) is the key derivation function specified in RFC 5869 (using the SHA256 hash function). The parameters are:
k: The initial keying material.
n: The number of output bytes.
info: The info string.
s: The salt.
AES-256-CTR(m, k, iv) is AES-256 encryption in CTR mode. The parameters are:
m: An arbitrary-length (possibly zero-length) message.
k: A 32-byte key.
iv: A 16-byte initialization vector (nonce).
PBKDF2-SHA256(p, s, i, n) is the password-based key derivation function defined in RFC 2898 (using the SHA256 hash function). The parameters are:
p: The password string.
s: The salt string.
i: The iteration count.
n: The output length in bytes.
VERSION is the string "\xDE\xF5\x02\x00".
AUTHINFO is the string "DefusePHP|V2|KeyForAuthentication".
ENCRINFO is the string "DefusePHP|V2|KeyForEncryption".
To encrypt a message m using a 32-byte key k, the following steps are taken:

Generate a random 32-byte string salt.
Derive the 32-byte authentication key akey = HKDF-SHA256(k, 32, AUTHINFO, salt).
Derive the 32-byte encryption key ekey = HKDF-SHA256(k, 32, ENCRINFO, salt).
Generate a random 16-byte initialization vector iv.
Compute c = AES-256-CTR(m, ekey, iv).
Combine ctxt = VERSION || salt || iv || c.
Compute h = HMAC-SHA256(ctxt, akey).
Output ctxt || h.
Decryption is roughly the reverse process (see the code for details, since the security of the decryption routine is highly implementation-dependent).

For encryption using a password p, steps 1-3 above are replaced by:

Generate a random 32-byte string salt.
Compute k = PBKDF2-SHA256(SHA256(p), salt, 100000, 32).
Derive the 32-byte authentication key akey = HKDF-SHA256(k, 32, AUTHINFO, salt)
Derive the 32-byte encryption key ekey = HKDF-SHA256(k, 32, ENCRINFO, salt)
The remainder of the process is the same. Notice the reuse of the same salt for PBKDF2-SHA256 and HKDF-SHA256. The prehashing of the password in step 2 is done to prevent a DoS attack using long passwords.

For KeyProtectedByPassword, the serialized key is encrypted according to the password encryption defined above. However, the actual password used for encryption is the SHA256 hash of the password the user provided. This is done in order to provide domain separation between the message encryption in the user's application and the internal key encryption done by this library. It fixes a key replacement chosen-protocol attack.

# Important note

In Teampass, the main `saltkey` used for items created in public folders is stored in a text file. During the installation, it is expected to indicate the path where this file will be stored.
The advice is to store it outside the WWW domain of your server.

This advice is very important. Indeed if a hacker gets access to your database, he will not be able to decrypt the passwords as the saltkey is not accessible.

# The special case of Personal Items

It is important to know that if a User loses his personal saltkey there is no possibility to restore his own personal items. The associated passwords will be lost.

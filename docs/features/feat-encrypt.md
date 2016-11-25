
# Data encryption in Teampass

Encryption is performed on `passwords` and `custom fields`. In other words the password string stored by the users are encrypted in database and cannot be discovered.
All other fields are in clear text in the database.

# Strategy used

Encryption is performed using **Cipher AES with a 128 bits block size relying on Cipher Block Chaining** (CBC). This technic uses:

* an `Initialization Vector` (IV) which is generated for each new encryption
* a `saltkey` which is defined by the Administrator of Teampass (and asked during installation) for all public Items. Notice that if you are using `Personal Folders` then each Teampass user defines his own saltkey.

This guarantees that each cleartext string is encrypted and stored with a different message (even if the stored cleartext strings are the same). So the database never contains the same encrypted string.

A lot of very interesting webpages exist on this topic that explain how encryption works much better than I could do.

# Consequences

Based on this encryption mode, each password is stored in the database in 2 separate fields. Field `string` receives the password encrypted with the saltkey stored inside field `IV`.

As said before, the encrypted string is the result of the encryption operation made with the `saltkey` and the generated `IV`. And those 2 keys are needed to decrypt the string.

In Teampass, the main `saltkey` used for items created in public folders is stored in a text file. During the installation, it is expected to indicate the path where this file will be stored.
The advice is to store it outside the WWW domain of your server.

This advice is very important. Indeed if a hacker gets access to your database, he will not be able to decrypt the passwords as the saltkey is not accessible.

# The special case of Personal Items

It is important to know that if a User looses his personal saltkey there is no possibility to restore his own personal items. The associated passwords will be lost.


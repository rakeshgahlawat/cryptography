# Cryptography Overview.

Cipher is the system used to create an encoded or secret message. Caesar Cipher -> plain text > key > cipher text.
CIA (confidentiality integrity availability) triad - a good security plan incorporates a balance of all three.
Cryptography fits in CIA at confidentiality for file, message and link encryption | integrity for digital signatures and hashes.

Symmetric key cryptography - same key is used to encrypt and decrypt the message.
Stream cipher - implemented on each bit. | Block cipher - implemented on blocks of bits.
Modes of block cipher are ECB electronic code book mode and CBC cipher block chaining mode. Rounds - number of times the encryption or decryption process is applied to plain text.

Data Encryption Standard DES -> 64 bit key | 56 bit true key | 8 parity bits with 16 rounds of encryption. Triple DES 3DES was developed as a quick fix for DES with 168 bit key | 48 rounds and is commonly used by payment cards.

Advanced Encryption Standard AES -> 128 bit, 192 bit or 256 bit key with fewer rounds than DES, but vary by key length and block size, has been chosen to replace DES. Approved by US government to protect sensitive but unclassified data.

Ron's Code RC4 -> stream cipher used in SSL and WEP for early Wi-Fi security with variable key size. IETF published RFC 7465 prohibiting use in TLS due to weaknesses. RC5 and RC6 with block sizes of 32, 64 or 128 bits and key size up to 2048 bits, it has up to 255 rounds, RC6 was built to the same as RC5 just faster.

Blowfish and Twofish - free and available for anyone to use. 

Strengths of Symmetric key cryptography, can be used for file encryption for transmission and storage (AES 256), financial transactions (3DES) and VPN encryption (AES256).

Weaknesses of symmetric key cryptography, cannot be used for digital signatures, message security (non-repudiation), key transfer and website security. Symmetric key cryptography does not provide a complete solution due to its weaknesses.

https://www.aescrypt.com/

Asymmetric key cryptography uses 2 different keys, called public and private keys. The key pair uses either key agreement or key exchange to encrypt messages.

Diffie-Hellman invented by Whitfield Diffie and Martin Hellman. First asymmetric key agreement algorithm (public keys are exchanged by the 2 people communicating). Uses public and private key to generate symmetric key. Original algorithm was vulnerable to man-in-the-middle attack.

RSA Ron Rivest, Adi Shamir and Len Adleman. Provides authentication (is by digital signatures) and encryption. Can be used for encryption and digital signatures. Can be used to exchange keys. Wide variety of uses. Uses a one-way function.

ECC Elliptic curve cryptography/cryptosystem. Provides authentication (is by digital signatures) and encryption. Can be used for encryption and digital signatures. Can be used to exchange keys. Faster and more efficient than RSA. Used in devices (smartphones) with less resources. Can provide same protection as RSA with smaller key.

El Gamal supports digital signatures, encryption and key exchange. Extension of Diffie-Hellman algorithm. Similar level of protection as RSA and ECC. Usually the slowest.

Strengths of asymmetric key cryptography is secure key exchange and simplified key management. Support authentication as well as encryption. Supports digital signatures. Uses would be in key exchange, message encryption, part of website security and message authentication. Weakness is the slowness of it. 
Asymmetric encryption and symmetric encryption work best when used together.

Hashing -> file > one-way hash > hash value. Salting -> password + salt value > one-way hash > hash value.
MAC message authentication code -> message + symmetric encryption key > MAC function > MAC value. Hash MAC is done by adding symmetric key to the message. CBC-MAC and CMAC has message encrypted with symmetric block cipher in cipher-block-chaining CBC mode. CMAC is more secure version.

MD2 and MD4 are both one-way hash functions, both produce a 128-bit hash and have similar strength. MD2 is slower than MD4 or MD5.
MD5 is a newer version of MD4 with additional rounds of operations. It was found to be vulnerable to collision attack (find two inputs producing the same hash value, i.e. a hash collision) due to which it is no longer used in SSL or digital signatures.

SHA-1 and SHA-256 designed by NSA to be used with Digital Signature Standard DSS. 160-bit hash value for SHA-1, 256-bit for SHA-256. SHA-1 is similar operation to MD4 and MD5 but stronger.

HAVAL is a modification of MD5. Tiger not based on MD4 or MD5 with 192-bit hash, designed to be faster than SHA-1 and MD5 is also not vulnerable to collision attacks.

http://www.7-zip.org/

message through hash > hash value > encrypt hash value with private key -> which results in digital signature for the message > digital signature + message > which is now encrypted using private key and is sent.

Non-repudiation - ensuring that a person cannot deny that they were responsible for an action. Digital signatures are an example of non-repudiation.

Email encryption -> secure multipurpose Internet mail extension (S/MIME)

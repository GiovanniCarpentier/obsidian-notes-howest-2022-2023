# Encryption
## Encryption and Cryptography are not the same
#Encryption-vs-Cryptography

- Encryption is just a technique to make sure data are only readable with a given key
	- Data confidentiality
- Data integrity, authentication require other cryptography techniques

## Symmetric Key Encryption
#Symmetric-Key-Encryption
#xor-logical-operator 

- Symmetric implies that the same key is used (and needs to be available) on both sides. 
- The 2 users share an identical symmetric encryption key

### Stream Cipher
#Stream-Cipher
- Symmetric Encryption implies that encryption and decryption require the same key to be used on both sides
- Plaintext XOR gives the cipher text
- Ciphertext XOR gives the original plaintext back

- A stream cipher is one that encrypts a digital data stream one bit or one byte at a time
	- Works with an endless stream and is not block-oriented
- A one-time pad means that the cryptographic keystream is random
	- [One-time pad video]https://www.youtube.com/watch?v=FlIG3TvQCBQ
	- This cipher is unbreakable by any other means other than acquiring the keystream
- the bit-stream generator is a key-controlled (or seed-controlled) algorithm
- This stream is not random but pseudo-random

### Block Cipher
#Block-Cipher
- A block cipher treats a block of plaintext as a whole and is used to produce a ciphertext block of equal lenght
- 64 or 128 bits block size is typically used
- The vast majority of network-based symmetric cryptographic applications make use of block ciphers
	- DES (64 bit blocks, 56 bit key)
	- AES (128 bit blocks, 128 bit key or 192 bit key or 256 bit key)
- The encryption and decryption algorithms are equal (DES, general Feistel ciphers) or very similar (AES)
- We need to make sure the predictability in the plaintext cannot be found and exploited in the ciphertext when we split a big plaintext file into equal blocks and we just encrypt these blocks using a good algorithm such as AES then the encrypted blocks are predictable. This is called the ECB mode of operation. Therefore we need more sophisticated modes of operation

## CBC or CTR modes of operation
#xor-logical-operator 
#modes-of-operation
#cbc
#ctr
#gcm

### CBC
- We xor the plaintext of the second block with the cipher of the previous block

### CTR
- We encrypt fixed counters and then we XOR the plaintext with these encrypted counters so in the decryption phase the CTR mode of operation only uses the encryption algorithm

## GCM
- Galois Counter Mode, Extension of CTR used for authentication encryption

## Asymmetric Key Encryption or Public Key Cryptography
#Asymetric-Key-Encryption
#Public-Key-Cryptography

- Asymmetric implies that different keys needs to be available on both sides. Pairs of keys are matched via mathematics

- The steps are the following
1. Each user generates a pair of keys to be used for encryption and decryption
2. Each user places one of the 2 keys in a public register or other accessible file
	1. This is the public key. 
	2. The companion key is the private key.
3. If user 1 wants to send a confidential message to user 2
	1. User 1 encypts the message using the public key of user 2
	2. User 2 decrypts the message using their own private key

- Public key Cryptography is mainly a solution for 2 problems: Key Distribution and Digital Signatures
- Example is RSA that used to have a bit length of 1024 but is now often 2048 or 4096 bits
- Part A is used for Confidentiality (Encryption)
- Part B is used for Authentication (Digital Signature)

- Symmetric encryption is far more peformant (1000 times) than Asymmetric encryption

- RSA (2048) and RSA (4096) are popular bit lengths for asymmetric algorithms
- ECC (Elliptical Curve Cryptography [[Elliptical Curve Arithmetic]]) has a key length of 256 bits or 512 bits

## [[Diffie Hellman Key Exchange]]
#Diffie-Hellman-Key-Exchange

- Diffie Hellman allows two parties who have not met before and who have not agreed on some set of keys or some shared secret (or. PKI), to start a secure communication. Essentially, the protocol allows to exchange some values so that both parties shall obtain the same shared secret. A man in he middle who obtains all information exchanged is not able to create the shared secret.
- The shared secret cannot immediately be used as a key for symmetric encryption between both parties because it is not sufficiently random, but it can be input to a key derivation function to produce a usable key.
- Diffie-Hellman is based on the same theory as asymmetric crypto. Actually, the protocol boils down to each party generating a random, treating this as a temporary private key, calculating a public key based on this private key, and sending the public key to the other party. Both parties then have the other’s public key and their own private key, and can use this to calculate a shared secret. There is an RSA and an ECC version of Diffie-Hellman.
- Encrypted messaging between parties, e.g. WhatsApp or Signal, starts off with a variant of Diffie Hellman to agree on a shared secret that is then used as a basis of symmetric encryption. A major difference is that the Diffie Hellman-like protocol needs to be able to run in a non interactive way (when one party is offline). The public keys based on the randoms that are generated on the fly by each party, are pre-published.
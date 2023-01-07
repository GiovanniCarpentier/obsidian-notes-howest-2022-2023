# AES
#advanced-encryption-standard 
#Symmetric-Key-Encryption 
#finite-fields 

- AES (Advanced Encryption Standard) is a symmetric encryption algorithm
- It uses a fixed-size key to encrypt and decrypt data
- AES is widely used in various applications including file encryption, secure communication, and data storage
- It has a block size of 128 bits and supports key sizes of 128, 192, or 256 bits
- AES is considered to be a very secure encryption algorithm, with no known vulnerabilities or weaknesses.

## Finite Field Arithmetic
- A finite field is a mathematical structure that consists of a finite number of elements.
- In AES cryptography, finite field arithmetic is used to perform mathematical operations on data blocks as part of the encryption and decryption process.
- Finite field arithmetic involves operations such as addition, subtraction, multiplication, and division, but with some restrictions and modifications to the normal rules of arithmetic.
- Finite field arithmetic is used in AES cryptography because it allows for fast and efficient computation, while also providing a high level of security.
- Finite field arithmetic is an important part of the AES algorithm and plays a critical role in ensuring the security of encrypted data.

## Encryption Process
- AES encryption uses a symmetric-key algorithm, meaning the same key is used for both encryption and decryption.
- The key size can be 128, 192, or 256 bits, with larger key sizes providing stronger security.
- The plaintext message is divided into blocks, typically 128 bits each.
- Each block is processed through a series of rounds, where it is transformed and mixed with the key.
- During each round, the block undergoes several transformations, including substitution, shifting, and mixing.
- The number of rounds depends on the key size and ranges from 10 rounds for 128-bit keys to 14 rounds for 256-bit keys.
- The final round includes an additional transformation called the "key whitening" step, which mixes the block with the key one final time.
- The resulting ciphertext block is then returned to the caller.

## Data Structures
The AES (Advanced Encryption Standard) algorithm works with blocks of data that are 128 bits in size, which is depicted as a 4x4 matrix of bytes. This block of data, known as the "State", is modified at each stage of the encryption or decryption process. The key used for encryption or decryption is also depicted as a matrix of bytes, and is expanded into an array of key schedule words, which are 4 bytes each. The key schedule is 44 words for a 128-bit key. The ordering of bytes within the matrix is by column, so for example, the first four bytes of the plaintext input to the encryption cipher would occupy the first column of the "in" matrix, the second four bytes would occupy the second column, and so on. Similarly, the first four bytes of the expanded key (which form a word) would occupy the first column of the "w" matrix.

## Parameters
The AES cipher consists of N rounds, where the number of rounds depends on the key length: 10 rounds for a 16-byte key, 12 rounds for a 24-byte key, and 14 rounds for a 32-byte key. Remember that 1 word is 4 bytes and 4 words is 16 bytes = 128 bits is 1 block.

You need N+1 Subkeys for N rounds

## Encryption and Decryption


## Detailed Structure


## Byte Level Operations


## S-Box Rationale


## Shift Row Transformation


## Shift Row Rationale


## MixColumn Transformation


## Mix Columns Rationale


## AddRoundKey Transformation


## Inputs for Single AES Round


## Key Expansion


## Key Expansion Rationale


## Avalanche Effect 


## Equivalent Inverse Cipher


## Interchanging InvShiftRows and InvSubBytes


## Interchanging AddRoundKey and InvMixColumns


## Equivalent Inverse Cipher


## Implementation Aspects
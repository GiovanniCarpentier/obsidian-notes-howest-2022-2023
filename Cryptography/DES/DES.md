# DES
#symmetric-cipher
#data-encryption-standard
#feistel-block-cipher
#Stream-Cipher 
#Block-Cipher 
#timing-attacks

## DES (Data Encryption Standard)
- Most widely used symmetric cipher

- The structure of DES and most symmetric ciphers is very complex and cannot be explained as easily as RSA and other public-key algorithms
- Also referred to as the Data Encryption Algorithm (DEA)
	- Data are encrypted in 64-bit blocks using a 56-bit key
- triple DES is repeating the DES algo 3 times on the plaintext using 2 or 3 different keys to produce the ciphertext

- How the DES encryption algo works
	- The processing of the plaintext proceeds in 3 phases
		- First the 64-bit plaintext passes through an initial permutation (IP) that rearranges the bits to produce the permuted input
		- This is followed by a phase consisting of 16 rounds of the same function with both permutations and substitution functions. The output if the last round consisting of 64 bits that are a function of the input plaintext and the key the left and right halves of the input are swapped to produce the preoutput
		- Finally the preoutput is passed through a permutation that is the inverse of the initial permutation function to produce the 64-bit ciphertext
	- With the exception of the initial and final permutations DES has the exact same structure of a Feistel cipher
	- The way the 56-bit key is used is as follows
		- Initially the key is passed through a permutation function
		- Then for each of the 16 rounds a subkey is produced by the combination of a left circular shift and a permutation
	- As with any feistel cipher decryption uses the same algo as the encryption, except that the application of the subkeys is reversed

- A change in one bit of the plaintext or one bit of the key should produce a change in many bits of the ciphertext. this is referred to as the avalanche effect

- The key size of 56 bits is too small for a brute force attack according to today's hardware

- There are a number of alternatives to DES to fix the lacking security 
	- AES and Triple DES are examples of this 

## Feistel block cipher
- Many symmetric block encryption algorithms in current use are based on a structure referred to as feistel block cipher

- The encryption and decryption mappings can be defined by a tabulation. This is the most general form of block cipher and can be used to define any reversible mapping between plaintext and ciphertext Feistel refers to this as the ideal block cipher

- Feistel proposed to use a cipher that alternates between substitutions and permutations
	- Substitutions: Each plaintext element or group of elements is uniquely replaced by a corresponding ciphertext element or group of elements
	- Permutation: A sequence of plaintext elements replaced by a permutation of that sequence, no elements are added or deleted or replaced in the sequence, rather the order in which the elements appear in the sequence is changed

- Feistel is a practical application of a proposal by Claude Shannon to develop a product cipher that alternates between confusion and diffusion
	- Shannon's concern was to thwart cryptanalysis based on statistical analysis
	- Confusion and Diffusion are 2 methods to frustrate statistical cryptanalysis
		- Diffusion: The statistical structure of the plaintext is dissipated into longrange statistics of the ciphertext. This is achieved by having each ciphertext digit be affected by many plaintext digits
		- Confusion: seeks to make the relationship between the statistics of the ciphertext and the value of the encryption key as complex as possible. This is achieved by the use of a complex substitution algorithm

- Diffusion is clearly not obtained by substitution because statistical relationships in the plaintext can be found in the ciphertexts. Think of a simple Caesar substitution. So, diffusion is obtained by permutation. Confusion is obtained trough substitution

- The structure of feistel cipher is as followed
	- A substitution is peformed on the left half of the data. This is done by applying a round function F to the right half of the data.
	- And then taking the exclusive-OR of the output of that function and the left half of the data
	- The round function has the same general structure of each round but is parameterized by the round subkey
	- Following this substitution, a permutation is peformed that consists of the interchange of the 2 halves of the data.
	- This structure is a particular form of the substitution-permutation network (SPN) proposed by Shannon

- The design features of Feistel
	- Block size: larger block mean greater security but reduced encryption / decryption speed for a given algorithm 64 bits is a reasonable tradeoff and was nearly universal in block cipher design. However the new AES uses a 128-bit block size
	- Key size: Larger key size means greater security but may decrease speed. The greater security comes from geater resistance agains brute-forcing attacks and greater confusion 128 bits has become a common size
	- Number of rounds: The essence of the Feistel cipher is that a single round offers inadequate security but that multiple rounds offer increasing security a typical size is 16 rounds
	- Subkey generation algorithm or key schedule algorithm: Greater complexty in this algo should lead to greater difficulty of cryptoanalysis
	- Round function F: same as previous
	- Fast software encryption / decryption: in many cases, encryption is embedded in applications or utility functions in such a way as to preclude a hardware implementation. Accordingly, the speed of execution of the algorithm becomes a concern.
	- Ease of analysis: easier algo to analyse can be handy to develop a higher level of assurance by patching cryptoanalytic vulnerabilities. DES for example does not have an easily analyzed functionality

- Feistel decryption is essentially the same as the encryption method
	- Use the ciphertext as input to the algorithm but use the subkeys K in reverse order

- It must be difficult to "unscramble" the substitution peformed by F
	- F must be nonlinear
- We would like to have the algo to have good avalanche properties

## Stream Cipher
- A stream cipher is one that encrypts a digital data stream one bit or one byte at a time
	- if the cryptographic keystream is truly random and used only once we speak of a one time pad and then the cipher is unbreakable

- the bit-stream generator must be implemented as an algorithmic procedure
	- so that the cryptographic bit stream can be produced by both users (and is only pseudo-random)
	- In this approach the bit stream generator is a key-controlled (or seed-controlled) algorithm
	- The 2 users need to share the generating key and can each produce the keystream

- A stream cipher can have a Initialization vector (IV) so that identical plaintext will not result in the same cipher text
	- The IV is not a secret and is sent in plain

- A stream cipher has no permutation and have a general low score on diffusion

## Block Cipher
- A block cipher is one in which block of plaintext is treated as a whole and used to produce a ciphertext block of equal length
	- Block size of 64 or 128 bits
	- Symmetric encryption key using some of the modes of operation, a block cipher can be used to achieve the same effect as a stream cipher

## Timing Attacks
- Are relevant for symmetric ciphers. A timing attack is one in which information about the key or plaintext is obtained by observing how long it takes a given implementation to peform decryption
- A timing attack exploits the fact that an encryption or decryption algo often take different amounts of time on different inputs. One approach yields the hamming weight (number of bits equal to one) of the secret key
- This is a long way from knowing the actual key but it is an intriguing first step
- DES seems to be fairly resistant to a successful timing attack
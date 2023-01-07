# Basics of Cryptography
## Binary Representations
#binary-representations

[Binary explained easily]https://www.youtube.com/watch?v=zDNaUi2cjv4

- A binary number can be a 1 or a 0
- Base 2 counting system

## Hexadecimal Representations
#hexadecimal-representations

- 16 symbols - 0 to 9 and A, B, C, D, E
- A, ... are used to represent decimal values from 10 to 15 
- Base 16

## XOR Logical Operator
#xor-logical-operator

- Other logical operators are AND and OR (Most known operators)
- Bad for encryption because information is lost due to the 75% chance that there is a default answer and this makes decryption hard
- XOR is a mix of the 2 
	- 2 are different = 1
	- 2 are equal = 0
- An obvious algorithm for encryption/decryption is XOR with a known key
	- XOR twice with the same key it will cancel out

## Combinations
#combinations

- Birthday Paradox or Birthday Attack
	- A hash function is a function that calculates for each input and output number of SHA-1 with a lenght of 160 bits
	- A different input will produce a different output.
	- You could get the same hash output for different inputs
		- (Birthday) If you are just looking for a hash collision (2 inputs with the same output) you should try 2^80 inputs

## Primes, Modulo and Logarithm
#primes
#modulo 
#logarithm

A prime number is **a whole number greater than 1 with only two factors – themselves and 1**. A prime number cannot be divided by any other positive integers without leaving a remainder, decimal or fraction.

Modulo is **a math operation that finds the remainder when one integer is divided by another**. In writing, it is frequently abbreviated as mod, or represented by the symbol %.

logarithm, **the exponent or power to which a base must be raised to yield a given number**. Expressed mathematically, x is the logarithm of n to the base b if bx = n, in which case one writes x = logb n. For example, 23 = 8; therefore, 3 is the logarithm of 8 to base 2, or 3 = log2 8

## Cryptography Library and Python
#crypto-with-python

- Installing the cryptography library
	- `pip install cryptography`

### XOR, HEX, BIN
- Numbers are not HEX or BIN or DEC they are just numbers
	- If you want to start with a hex number is by doing an assigment using 0x or 0b

### GCD
- Part of the euclidean module (custom module)
	- `euclidean.gcd(300, 210)`

### PRIMES
- Custom module 

## Cisco Stream Cipher Simplified
#Cisco-Cipher
#Stream-Cipher 

- Encryption scheme by Cisco routers to encrypt passwords is a stream cipher
- It chooses a random number between 0 and 15 and that becomes the offset into the keystream
- The password is then XORed with the keystream of the same lenght

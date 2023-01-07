# Modulo and Galois
#finite-fields
#advanced-encryption-standard
#elliptic-curve-cryptography
#Euclidean-Algorithm
#extended-euclidean-algorithm
#modular-arithmetic
#modulo 
#polynomial-arithmetic 

## Finite Fields (Galois Field)
- GF = Galois Field = a finite field, a field with a finite number of elements

- Finite Fields have become increasingly important in Cryptography. A number of cryptographic algorithms rely heavily on properties of finite fieldsfor example the AES and Elliptic Curve Cryptography and the message authentication code CMAC and the authenticated encryption scheme GCM

- GF(p) or GF(p^n) with p is a prime and n is any number. p or p^n is the number of elements of the domain

## Divisibility
- if b divides a ten b is a divisor of a

## Euclidean Algorithm
- One of the basic techniques of number theory

- Simple procedure for determining  the greatest common divisor (GCD) of two positive integers

- 2 integers are relatively prime if their only common positive integer factor is 1

- The algo uses the characteristics that the GCD of a and b is the same as the GCD of b and r1 where r1 is the remainder of a/b. We can continue to do this until the remainder is 0

- Example
	- We divide 1160718174 (a) by 316258250 (b) 
		- This gives the result 3 with a remainder of 211943424 (r1)
			- next we take 316258250 (b) (now a) and divide it by 211943424 (r1) (now b)
			- the process continues until we get a remainder of 0
			- This results in 1078

## Extended Euclidean Algorithm
- This algo allows to calculate the multiplicative inverse simultaneously with the GCD

- 1 = gcd(a,b) = a * x + b * y 

## Modular Arithmetic
- Modular Arithmetic is calculating with finite numbers

- a mod n is the remainder when a is divided by n

- 2 integers a and b are said to be congruent module n if
	- (a mod n) = (b mod n) => a = b (mod n)

	**Properties of Congruences**
	- a = b (mod n) if n | (a – b)  
	- a = b (mod n) implies b = a (mod n)  
	- a = b (mod n) and b = c (mod n) imply a = c

- In ordinary arithmetic, there is a multiplicative inverse, or reciprocal, to each integer

- As in ordinary addition there is an additive inverse or negative to each integer

## Polynomial Arithmetic
- A key motivation for using polynomial arithmetic in GF(2^n) is that the polynomials can be represented as a bit string, using all possible bit values, and the calculations only use simple common machine instructions - addition is just XOR, and multiplication is shifts & XOR's 
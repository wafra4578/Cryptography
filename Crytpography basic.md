# Plaintext to Ciphertext
- **Plaintext** - is the original, readable message or data before it's enrypted. (a document, an image, a multimedia file, binary data)
- **Ciphertext** - the scrambled, unreadable version of the message after encyption. Can't get any info about plaintext other than its approx size
- **Cipher** - an algorithm to convert plaintext into ciphertext and vice versa. The used cipher is public knowlegde
- **Key** - a string of bits the cipher uses to encypt or decrypt data.
- **Encryption** - process of converting plaintext into ciphertext using a cipher and a key. The choice is cipher is disclosed, unlike the key.
- **Decryption** - reverse process of encryption using a cipher and a key. 

# Historical Ciphers
### Caesar Cipher
Shift each letter by a certain number to encrypt the message

- Plaintext: `TRYHACKME`
- Key: 3 (right shift of 3)
- Cipher: Caesar Cipher
- Ciphertext: `WUBKDFNPH`
- Decryption: shift the letter to left by 3<br>

There are only 25 possible keys.
https://cryptii.com/pipes/caesar-cipher
- ciphertext: `XRPCTCRGNEI`
- key: Shift 15 a->p
- plaintetx: `ICANENCRYPT`

#### Two categories of encryption:
1. **Symmetric Encryption**
2. **Asymmentric Encyprtion**

# Symmetric Encryption / Cryptography
![alt text](image/symmetric%20encryption.png)
uses the same key to encrypt and decrypt the data. it's called private key cryptography. Keeping the key secret is a must.
Communicating the key to the intended parties is challeneging as it requires a secure communication channel, even more when there's many recipients or a powerful adversary.
- DES (Data Encryption Standard): uses 56-bit key
- 3DES is DES applied three times: key size is 168 bits, effective security is 112 bits
- AES (Advanced Encryption Standard): key size can be 128, 192, or 256 bits

# Asymmetric Encryption / Cryptography
![alt text](image/asymmetric%20encryption.png)
uses a pair of keys, one to encrypt and the other to decrypt. It encrypts tha data using the public key, hence called public key cryptography.
- **RSA**: 2048-bit, 3072-bit, 4096-bit keys; 2048-bit is recommended minimum key size
- **Diffie-Hellman**: uses 3072-bit and 4096-bit keys for enhanced security; 2048-bit is recommended minimum key size
- **Elliptic Curve cyptography (ECC)**: achieves equivalent security with shorter keys. With a 265-bit key, ECC provides a level of security comparable to a 3072-bit RSA key
<br>
The two keys involved are public key and private key. Data encrypted with the public key can be decrypted with the private key.<br>
Asymmetric encryption tends to be slower and uses larger keys than symmtric.
It is made to be easy to compute in one direction but extremely difficult to reverse in mathematics.

# XOR operation
used in computing, cryptography, error detection<br>
**XOR** = 1 if the number of 1s is odd<br>
otherwise **XOR** = 0
 to apply XOR to the binary numbers 1010 and 1100. In this case, we perform the operation bit by bit: 1 ⊕ 1 = 0, 0 ⊕ 1 = 1, 1 ⊕ 0 = 1, and 0 ⊕ 0 = 0, resulting in 0110.

A ⊕ A = 0, and A ⊕ 0 = A for any binary value A.<br> XOR is 
- commutative: A ⊕ B = B ⊕ A. 
- associative: (A ⊕ B) ⊕ C = A ⊕ (B ⊕ C).

#### In basic symmetric encryption algorithm:
- P -> plaintext
- K -> secret key
- C -> ciphertext
- C = P ⊕ K<br>
if we know C & K, we can recover P.<br>
⇒ C ⊕ K = (P ⊕ K) ⊕ K<br>
⇒ (P ⊕ K) ⊕ K = P ⊕ (K ⊕ K) [XOR is associative]<br>
⇒ (P ⊕ K) ⊕ K = P ⊕ 0 [since, A ⊕ A = 0]<br>
⇒ (P ⊕ K) ⊕ K = P<br>
in practice, a secret key is as long as the plaintext.<br>
https://www.wolframalpha.com/

#### Modulo Operation %
the modulo operaton X%Y, is the remainder when X is divided by Y. 
- 25%5=0 i.e., 25 = 5x5+0
- 23%6=5 i.e., 23 = 3x6+5
- 23%7=2 i.e., 23 = 3x7+2
<br>
Modulo isn't reversible. For x%5=4, infinite values of x would satisfy the equation.<br>
The modolu operation alawys returns a non-negative result less than the divisor. <br>
For any integer a and positive integer n,
result of a%n is in the range (0 ~ n-1)





# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:
```
import random
def mod_exp(base, exp, mod):
 return pow(base, exp, mod)
def diffie_hellman(p, g):
 a = random.randint(1, p-1)
 A = mod_exp(g, a, p)
 b = random.randint(1, p-1)
 B = mod_exp(g, b, p)
 shared_secret_meetha = mod_exp(B, a, p)
 shared_secret_bob = mod_exp(A, b, p)
 return shared_secret_meetha, shared_secret_bob
p = 23
g = 5
shared_secret_meetha, shared_secret_bob = diffie_hellman(p, g)
print(" *****DIFFIE_HELLMAN*****")
print("\nShared secret key (Meetha's calculation):", shared_secret_meetha)
print("\nShared secret key (Bob's calculation):", shared_secret_bob)
if shared_secret_meetha == shared_secret_bob:
 print("\nKey exchange successful! Shared secret is:", shared_secret_meetha)
else:
 print("Key exchange failed!")
```



## Output:
![image](https://github.com/user-attachments/assets/3068aabb-6a59-4805-be92-a0e587a7b040)



## Result:
  The program is executed successfully


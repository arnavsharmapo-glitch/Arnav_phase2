
# Challenge 1 : Custom Encryption

Can you get sense of this code file and write the function that will decode the given encrypted file content.
Find the encrypted file here flag_info and code file might be good to analyze and get the flag.

## Solution : 
- Open the instance
- We are given both a python encryption script and an encrypted flag
- The program randomly chooses random integers for the job
- We havs the values as g=31, p=97, a=90, b=26 as given in the code
- We also know that the encrypted value has a form like this; encrypted = ord(char) * shared_key * 311
- To get back the original value, we reverse this operation as chr(encrypted // (shared_key * 311))
- Then we go to an online XOR decryption website and enter both the input and the key word to get our reversed flag
- Finally reverse the output you got from the site and type it

![Custom Encryption pt1](../pics/Screenshot%202025-10-27%20143454.png?raw=true)
![Custom Encryption pt2](../pics/Screenshot%202025-10-27%20143521.png?raw=true)

## Flag : 
```sh
picoCTF{custom_d2cr0pt6d_49fbee5b}
```

## Concepts Learnt :
- Learnt a lot about python codes
- Learnt about XOR encryption and decryption and how to operate online sites for the same

## Notes : 

No alternate tangents but had to learn and work quite a bit before being able to solve this one

### Reference : 

- https://www.infosecinstitute.com/resources/cryptography/beginners-guide-to-the-basics-of-data-encryption/
- https://www.geeksforgeeks.org/python/ord-function-python/
- https://stackoverflow.com/questions/62514856/guessing-xor-secret-key-knowing-some-part-of-it

# Challenge 2 : miniRSA

Let's decrypt this: ciphertext? Something seems a bit small.

## Solution : 
- Open instance
- Here, we kow that we are in a RSA encryption challenge, (c= m^e)
- We also know that the value of e here is 3
- Now, as c^3 is small enough that m^3<N, we effectively get that c=m^3
- We can now easily find out the value of m by taking cube root of c
- We then convert this to hexadecimal and decode them as UTF-8
- We get our flag
  
![miniRSA Problem](../pics/Screenshot%202025-10-27%20204827.png?raw=true)

## Flag : 
```sh
picoCTF{n33d_a_lArg3r_e_d0cd6eae}
```

## Concepts Learnt :

- Learnt about RSA encryption and how to decode that
- Learnt how to decode as UTF-8 using online website 

## Notes : 

No alternate tangents

### Reference : 

- https://en.wikipedia.org/wiki/RSA_cryptosystem#Operation

# Challenge 3 : rsa_oracle

Can you abuse the oracle?
An attacker was able to intercept communications between a bank and a fintech company. They managed to get the message (ciphertext) and the password that was used to encrypt the message.
After some intensive reconassainance they found out that the bank has an oracle that was used to encrypt the password and can be found here nc titan.picoctf.net 59327. Decrypt the password and use it to decrypt the message. The oracle can decrypt anything except the password.

- Hint 1 : Crytography Threat models: chosen plaintext attack.
- Hint 2 : OpenSSL can be used to decrypt the message. e.g openssl enc -aes-256-cbc -d ...
- Hint 3 : The key to getting the flag is by sending a custom message to the server by taking advantage of the RSA encryption algorithm.
- Hint 4 : Minimum requirements for a useful cryptosystem is CPA security.

## Solution : 
- We get two files from the instance, one was a password file which conatined a huge number and the other was a secret file which was encrypted using OpenSSL(as can be seen on the usage of Salted) and didn't have any understandable text
- Our password file contained a cipher for us which was basically a large number
- After connecting into the challenge on a terminal via the key, we see that it asks us to either encrypt or decrypt our input
- On entering any random number as input, we see that it is using RSA encryption for it's security and it gives a hex and a ciphertext
- Now we understand that the key to getting the flag is by sending a custom message to the server by taking advantage of the RSA encryption algorithm
- The cipher that we got was our input number raised to power e(65587 usually) mod N
- So I encrypted 2, which gives me a cipher text value of 2^e %n
- Now, we can multiply our cipher in the password file with that number which is basically (2m)^e mod n
- Now, we decrypt this value to get us an output as 2m
- This gives us a hex string, which we convert to decimal first and divide it by 2, to get out value as m, change it back to hexdecimal and then finally to ASCII value
- After researching, I found that openssl can give us a key for decryption using -k as an argument
- I finally got my flag after I entered the code snippet given to us in the hint after completing it which was as follows
```sh
openssl enc -aes-256-cbc -d -in secret.enc -k  3319c
```  

## Flag : 
```sh
picoCTF{su((3ss_(r@ck1ng_r3@_3319c817}
```

## Concepts Learnt :

- Learnt more about RSA encryption
- Learnt how to bypass RSA if it is unguarded by using a multiple of the actual password
- This method is known as Chosen PlainText Attack(CPA), which I learned by researching through the web

## Notes : 

Tried to enter inputs in many other forms like hex code, decimal code and binary code to decrypt it to get the password. Used ASCII values at last

### Reference : 
```sh
- https://ctf101.org/cryptography/what-is-rsa/
- https://www.geeksforgeeks.org/computer-networks/rsa-algorithm-cryptography/
```

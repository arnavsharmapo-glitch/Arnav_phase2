
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

# Challenge 1 : 


## Solution : 
-
![RSA Oracle](../pics/?raw=true)

## Flag : 
```sh

```

## Concepts Learnt :


## Notes : 


### Reference : 

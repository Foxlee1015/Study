---
layout: post
title: Encrypt-hashlib
categories:
- blog
---

# password 암호화
import hashlib
pass_data = form.password.data
password = hashlib.sha256(pass_data.encode()).hexdigest()



https://krksap.tistory.com/1284 (예제 참고)

> # What is SHA-256?

* SHA-256 stands for Secure Hash Algorithm – 256 bit and is a type of hash function commonly used in Blockchain. 
* A hash function is a type of mathematical function which turns data into a fingerprint of that data called a hash. 
* It’s like a formula or algorithm which takes the input data and turns it into an output of a fixed length, which represents the fingerprint of the data.

* The input data can literally be any data, whether it’s the entire Encyclopedia Britannica, or just the number ‘1’. 
* A hash function will give the same hash for the same input always no matter when, where and how you run the algorithm. 
* Equally interestingly, if even one character in the input text or data is changed, the output hash will change. Also, a hash function is a one-way function, thus it is impossible to generate back the input data from its hash. So, you can go from the input data to the hash but not from the hash to the input data.

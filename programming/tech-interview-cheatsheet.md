---
description: Basic stuff to remember at a generic tech interview
---

# 📜 Tech Interview Cheatsheet

### Security & Encryption

* How are passwords typically stored for e.g. a basic webshop? Hashed
* Difference between Encryption & Hashing? Encryption is reversible, hashing is a one-way function. So hashed data cannot be translated back to its original state.
* What common types of encryption are there?
  * Symmetric Encryption: The same password is used to encrypt and decrypt the data
  * Asymmetric Encryption: A public key is used to encrypt the data and a private key is used to decrypt it. This allows e.g. lots of ppl to send encrypted mail to a single person that only that single person can decrypt using their private key.
  * What are common algorithms used today?
    * AES (symmetric)
    * RSA, ECC, Diffie-Helman exchange method, TLS/SSL (asymmetric)

### UML

#### Class Diagram Arrows

![Source: Wikipedia ](<../.gitbook/assets/image (1) (1).png>)

### System Design

* [System Design Exercise](https://www.hiredintech.com/classrooms/system-design/lesson/52)
* [System Design Cheat Sheet](https://gist.github.com/vasanthk/485d1c25737e8e72759f)

#### Basic Workflow for a system design exercise

1. Clarify functional and non functional requirements
   1. What are the use cases (Who is using it? How are they using it?)
   2. How much traffic is there?
   3. Is the traffic/load the same all the time or does it change? Have peaks?
   4. Are there any other special system requirements?
2. Create a high level architecture design
   1. Sketch important components
      1. Load balancer, DB, caching?
   2. List services required
   3. Data storage? SQL, NOSQL? Cache?
3. Component design
   1. Design specific components of the system + their APIs

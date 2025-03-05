# **RSA Encryption: Public-Key Cryptography**

## **What is RSA?**

RSA (**Rivest-Shamir-Adleman**) is an **asymmetric encryption algorithm** that uses a **public key for encryption** and a **private key for decryption**.

---

## **Step-by-Step RSA Encryption Process**

### **Step 1: Key Generation**

- The **receiver (Bob)** generates a **public-private key pair**:
  - **Public Key 🔑** (Shared with anyone).
  - **Private Key 🔐** (Kept secret).

### **Step 2: Sender Encrypts the Message**

- **Sender (Alice)** obtains **Bob’s Public Key**.
- Alice **encrypts the message** using Bob’s **Public Key** with the RSA algorithm:

  \[
  C = M^e \mod N
  \]

  Where:
  - \( C \) = Encrypted Message (Ciphertext).
  - \( M \) = Original Message.
  - \( e \) = Public Exponent.
  - \( N \) = Modulus (Product of two large prime numbers).

### **Step 3: Sending the Encrypted Message**

- Alice sends the **encrypted message (ciphertext) to Bob**.

### **Step 4: Receiver Decrypts the Message**

- **Bob decrypts the message** using his **Private Key**:

  \[
  M = C^d \mod N
  \]

  Where:
  - \( d \) = Private Exponent (Secret Key).
  - \( C \) = Ciphertext.
  - \( N \) = Modulus.

### **Step 5: Message Successfully Decrypted**

- Bob retrieves the **original message**.

---

## **Key Properties of RSA**

1️⃣ **Asymmetric Encryption** → Uses a **public-private key pair** instead of a single key.  
2️⃣ **Strong Security** → Based on **prime factorization**, making decryption without the private key nearly impossible.  
3️⃣ **Used for Secure Key Exchange** → Often used in **TLS (HTTPS), PGP, and digital signatures**.  
4️⃣ **Slower Than Symmetric Encryption** → Used for encrypting small data (e.g., **keys** rather than entire files).  
5️⃣ **Digital Signatures** → Used to **verify authenticity** in secure communication.  

---

## **Example Use Cases of RSA**

- **HTTPS / SSL/TLS Handshake** → Secure web browsing.  
- **PGP Encryption** → Email security.  
- **Blockchain & Cryptocurrencies** → Digital signatures.  
- **Secure File Transfers** → Encrypting session keys in SSH.  

---

## **Conclusion**

RSA is a **secure and widely used encryption algorithm** that ensures **confidentiality and authentication**. It is primarily used for **secure key exchange and digital signatures** in modern cryptography. 🚀

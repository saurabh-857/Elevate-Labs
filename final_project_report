# **Rustle - A Secure Chat Application - Project Report**

**Author:** Saurabh Soni
**Date:** 24/06/2025

---

## **1. Introduction**

This report documents the development of [**`Rustle`**](https://github.com/saurabh-857/rustle.git), a secure chat application, built in `Rust`. The application provides **end-to-end encrypted messaging**, **user authentication**, and **rate limiting** to prevent abuse.

### **Key Features**

✅ **User Registration & Login** (JWT-based authentication)
✅ **End-to-End Encryption** (RSA + AES)
✅ **Real-Time Messaging** (WebSockets)
✅ **Rate Limiting** (Governor crate)
✅ **Database Storage** (SQLite)
✅ **Secure Key Management** (Argon2 password hashing)

---

## **2. Technical Stack**

|**Category**|**Technology Used**|
|---|---|
|**Backend**|Rust (Actix-web)|
|**Database**|SQLite (via `sqlx`)|
|**Authentication**|JWT (JSON Web Tokens)|
|**Encryption**|RSA (key exchange) + AES (message encryption)|
|**Rate Limiting**|`governor` crate|
|**WebSockets**|`actix-web-actors`|
|**Password Hashing**|Argon2|

---

## **3. System Architecture**

### **3.1 High-Level Overview**

The system consists of:

- **REST API** (for registration/login)
    
- **WebSocket Server** (for real-time chat)
    
- **SQLite Database** (stores users and messages)
    
- **Cryptography Layer** (handles encryption/decryption)
    

### **3.2 Data Flow**

1. **User Registration** → Stores hashed password + RSA keys
    
2. **User Login** → Returns JWT for WebSocket auth
    
3. **WebSocket Connection** → Establishes secure messaging
    
4. **Message Exchange** → Encrypted with RSA/AES
    

---

## **4. Key Components**

### **4.1 Authentication (`/register`, `/login`)**

- **Argon2** for password hashing
    
- **JWT** for session management
    
- **RSA key pairs** generated per user
    

### **4.2 Encryption (`encrypt_message`, `decrypt_message`)**

- **RSA** (2048-bit) for key exchange
    
- **AES-256-CBC** for message encryption
    
- **HMAC-SHA256** for key derivation
    

### **4.3 WebSocket Messaging (`ChatWebSocket`)**

- **Actix Actor System** for handling connections
    
- **Broadcast Channel** for real-time messaging
    
- **Message Validation** (signature checks)
    

### **4.4 Rate Limiting (`governor` Crate)**

- **60 requests/minute** per IP
    
- Prevents brute-force attacks
    

---

## **5. How to Run the Project**

### **5.1 Prerequisites**

- Rust (`cargo`)
    
- SQLite (`sqlite3`)
    
- OpenSSL (or use `vendored` feature)
    

### **5.2 Setup & Execution**

```bash
# Clone the project
git clone https://github.com/saurabh-857/rustle.git
cd secure_chat

# Create SQLite DB
sqlx database create

# Run migrations
sqlx migrate run

# Start the server
cargo run
```

### **5.3 API Endpoints**

|**Endpoint**|**Method**|**Description**|
|---|---|---|
|`/register`|POST|Register a new user|
|`/login`|POST|Login and get JWT|
|`/ws/`|GET|WebSocket connection|

---

## **6. Security Considerations**

### **6.1 Strengths**

🔒 **End-to-End Encryption** (messages never decrypted on the server)
🔒 **Secure Password Storage** (Argon2 + salts)
🔒 **Rate Limiting** (prevents DoS attacks)
🔒 **JWT Expiry** (tokens invalidate after 24h)

### **6.2 Potential Improvements**

⚠ **Use HTTPS** (for production deployment)
⚠ **Better Key Management** (HSM or KMS in production)
⚠ **Message Persistence Encryption** (encrypt DB-stored messages)

---

## **7. Testing & Validation**

### **7.1 Manual Testing**

- ✅ User registration & login
    
- ✅ WebSocket message exchange
    
- ✅ Encryption/decryption verification
    
- ✅ Rate limiting enforcement
    

### **7.2 Automated Testing (Future Work)**

- Unit tests for crypto functions
    
- Integration tests for API endpoints
    
- Load testing for WebSocket connections
    

---

## **8. Conclusion**

This project demonstrates a **secure, real-time chat system** built with Rust. It combines **strong encryption, authentication, and rate limiting** to ensure privacy and security.


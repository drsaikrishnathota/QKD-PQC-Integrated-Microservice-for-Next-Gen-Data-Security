# 🧠 Quantum-Enhanced Data Encryption Microservice  
**Java 17 + Spring Boot | Qiskit | Cassandra | Docker**

A production-ready **quantum-inspired data encryption microservice** that integrates **post-quantum cryptography (PQC)** and **quantum key distribution (QKD)** principles for next-generation secure communications.

---

## 🚀 Overview
This project demonstrates a **hybrid encryption system** combining classical and quantum-secure methods.  
It uses:
- **Java 17 (Spring Boot)** for the main microservice  
- **Python (Qiskit)** sidecar simulating BB84 Quantum Key Distribution  
- **Cassandra** for secure, scalable data storage  
- **Docker Compose** for orchestration  

Encrypted data (AES-GCM) is derived from **QKD-generated entropy** and **HKDF-derived AES-256 keys**, ensuring resistance against both classical and quantum attacks.

---

## ⚙️ Architecture
```
Client → Java API (Spring Boot)
         ↳ Python QKD Sidecar (/bb84)
         ↳ Cassandra Storage
         ↳ AES-GCM Encryption / HKDF Key Derivation
```
📂 *See `/diagrams/` for architecture and flow diagrams.*

---

## 🧩 Features
- Quantum key simulation (BB84)
- Post-quantum AES-256 GCM encryption
- Secure key derivation using HKDF
- Encrypted record persistence in Cassandra
- RESTful API endpoints for key generation, encryption, and decryption
- Containerized via Docker Compose

---

## 🧠 Run Locally
```bash
docker compose up --build
# App:        http://localhost:8082
# QKD sidecar: http://localhost:5000/bb84
```

---

## 🧾 API Examples
```bash
# Generate QKD key
curl http://localhost:8082/api/qkd/bb84

# Encrypt data
curl -X POST http://localhost:8082/api/crypto/encrypt  -H 'Content-Type: application/json'  -d '{"keyBase64":"<derivedAesKey>","plaintext":"Hello Quantum"}'

# Decrypt data
curl -X POST http://localhost:8082/api/crypto/decrypt  -H 'Content-Type: application/json'  -d '{"keyBase64":"<derivedAesKey>","ivBase64":"<iv>","ciphertextBase64":"<ct>","tagBase64":"<tag>"}'
```

---

## 📸 Screenshots
See `/screens/` for 8 dark-mode images showcasing IntelliJ setup, API calls, Docker logs, Cassandra queries, and test results.

---

## 🧪 Tech Stack
- **Java 17**, **Spring Boot 3**, **Bouncy Castle PQC**
- **Python 3.11**, **Flask**, **Qiskit**
- **Cassandra 4.x**
- **Docker**, **JUnit**, **Actuator**

---

## 🧭 Purpose
Designed for research and practical exploration of **quantum-resilient cryptography**, this project aligns with emerging **NIST PQC standards** and serves as a blueprint for building **secure, distributed, and quantum-ready microservices**.

---

## 🤝 Contributing
Contributions are welcome! Fork this repository, create a feature branch, and submit a pull request.  
Please follow conventional commit messages and include tests for any new functionality.

---

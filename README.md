# Certificate-Authority-Stores

# 🔐 Certificate Authority (CA) Stores Lab

## 📌 Overview
This lab demonstrates how HTTPS relies on trusted Certificate Authorities (CAs) to establish secure connections. Using browser certificate stores and OpenSSL, I examined trusted root certificates, retrieved a website's SSL/TLS certificate, generated its fingerprint, and verified certificate authenticity to understand how HTTPS Man-in-the-Middle (MITM) attacks can be detected.

---

## 🎯 Objectives
- View trusted Root Certificate Authorities (CAs) in a web browser.
- Understand the Certificate Authority trust chain.
- Retrieve a website's SSL/TLS certificate using OpenSSL.
- Generate and verify a certificate fingerprint.
- Detect potential HTTPS Man-in-the-Middle (MITM) attacks.

---

## 🛠️ Technologies & Tools
- OpenSSL
- Firefox / Google Chrome
- Linux Terminal
- Security Workstation Virtual Machine
- SSL/TLS
- PKI (Public Key Infrastructure)

---

## 💻 Commands Used

### Retrieve the website certificate
```bash
echo -n | openssl s_client -connect cisco.com:443 | \
sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' > cisco.pem
```

### View the certificate
```bash
cat cisco.pem
```

### Generate the SHA-1 fingerprint
```bash
openssl x509 -noout -in cisco.pem -fingerprint -sha1
```

---

## 🔍 Key Concepts Learned
- Browsers trust websites through **Root Certificate Authorities (CAs)**.
- Every SSL/TLS certificate has a unique **fingerprint (hash)**.
- OpenSSL can retrieve and verify certificate fingerprints.
- Matching fingerprints confirm certificate authenticity.
- Different fingerprints may indicate certificate renewal or an HTTPS inspection proxy.
- HTTPS proxies require their own trusted CA certificate to inspect encrypted traffic.

---

## ✅ Skills Demonstrated
- SSL/TLS Certificate Analysis
- Certificate Authority (CA) Management
- OpenSSL Command-Line Usage
- Certificate Fingerprint Verification
- Public Key Infrastructure (PKI)
- HTTPS Security Validation
- Man-in-the-Middle (MITM) Detection
- Linux System Administration

---

## 📚 Outcome
This lab strengthened my understanding of how HTTPS establishes trust through Certificate Authorities and digital certificates. I learned how to inspect browser trust stores, retrieve SSL/TLS certificates with OpenSSL, generate certificate fingerprints, and verify secure connections by comparing fingerprints. These skills are fundamental for cybersecurity professionals performing certificate validation, network security analysis, and HTTPS troubleshooting.
